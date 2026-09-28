# Respostas - Lab CI/CD

## 1. Quais são as 3 regras que o robô confere?

- Regra 1: o arquivo `index.html` existe no repositório.
- Regra 2: o site tem um título (existe uma tag `<title>`).
- Regra 3: o arquivo está completo, ou seja, termina com `</html>`.

## 2. No Passo 2, por que o site continuou na Versão 1?

Porque o job "1 - Verificar arquivo" falhou: o `index.html` da Versão 2 foi enviado pela metade e não terminava com `</html>` (Regra 3). No workflow, o job "2 - Publicar site" tem `needs: verificar`, ou seja, só roda se a verificação passar. Como a verificação falhou, o deploy foi pulado e o site publicado anteriormente (Versão 1) continuou no ar.

## 3. Se não existisse o robô, o que teria acontecido com o site no Passo 2?

O arquivo quebrado teria sido publicado direto no ar, sem nenhuma checagem. Os visitantes veriam uma página incompleta/quebrada até que alguém percebesse o problema manualmente e corrigisse, o que poderia levar minutos, horas ou até dias dependendo de quem estivesse de olho no site.

## 4. Na aba Actions, quantas execuções deram certo e quantas falharam?

Considerando os passos do laboratório (Passos 1 a 3), tivemos 4 execuções do workflow "Publicar site":
- ✅ 3 deram certo: commit inicial do template, Versão 1 e Versão 3 - corrigida.
- ❌ 1 falhou: Versão 2 (arquivo incompleto).

## 5. O quadro cinza do site publicado: quem enviou, quando e qual o commit? Por que essa informação é útil numa empresa?

O quadro mostra quem enviou (usuário do GitHub), quando foi publicado (data e hora) e o hash curto do commit. Essa informação é útil numa empresa porque permite rastrear a origem de qualquer mudança em produção: se algo quebrar, dá para saber exatamente quem fez a alteração, quando ela foi feita e qual código exato (commit) está no ar. Isso facilita auditoria, rollback (voltar para uma versão anterior) e a responsabilização de cada mudança.

## 6. Cite um processo do dia a dia que poderia ter um "robô conferindo antes de liberar".

Na faculdade: antes de aceitar a entrega de um trabalho de programação no portal, um "robô" poderia rodar os testes automaticamente e só liberar a nota/confirmação se o código compilar e passar nos testes, em vez de o professor descobrir manualmente que o código não funciona depois de já ter avaliado.

## Desafio (opcional): lendo o publicar-site.yml

- **Quando o robô começa a trabalhar:** no bloco `on:`, com `push: branches: [main]` (roda a cada envio na branch `main`) e também `workflow_dispatch:` (permite rodar manualmente pelo botão "Run workflow").
- **Onde estão as 3 regras:** dentro do job `verificar` ("1 - Verificar arquivo"), nos steps "Regra 1 - O arquivo index.html existe?", "Regra 2 - O site tem título?" e "Regra 3 - O arquivo está completo?".
- **A linha que só libera a publicação se a verificação passar:** no job `publicar` ("2 - Publicar site"), a linha `needs: verificar`.
