# Atividade 5 - O cliente pediu!

## Para entregar

- **Quadro do projeto:** https://github.com/users/m3la4aujo/projects/1 (3 cards em Done)
- **Site com a última versão publicada:** https://m3la4aujo.github.io/meu-site/

## Respostas

1. **Qual pedido vocês fizeram primeiro e por quê?**

Fizemos primeiro o pedido "Troque o emoji do foguete por outro", por ser o mais simples e rápido de implementar — bom para testar o fluxo completo do quadro (Todo → In Progress → Done) antes de partir para pedidos que mexiam em CSS (cor) e em conteúdo (mensagem de boas-vindas).

2. **Como o quadro ajudou a saber o andamento dos pedidos?**

O quadro deixou visível, a qualquer momento, quais pedidos ainda não tinham sido iniciados (Todo), qual estava sendo feito naquele instante (In Progress) e quais já haviam sido entregues (Done) — sem precisar abrir cada issue individualmente para saber a situação.

3. **O que o Closes #N automatizou?**

Ao colocar `Closes #1`, `Closes #2` e `Closes #3` nas mensagens de commit, o GitHub fechou automaticamente cada issue assim que o commit chegou na branch `main`, e o card correspondente no quadro pulou sozinho de "In Progress" para "Done" — sem nenhuma ação manual extra do time.

4. **Que métricas a aba Actions mostrou sobre o site?**

Mostrou quantas execuções passaram e quantas falharam, quanto tempo cada etapa (Verificar e Publicar) levou, e quem fez o commit que disparou cada execução e quando.

5. **Dê um exemplo de feedback que gerou um novo pedido.**

Neste ciclo todos os 3 pedidos foram aprovados de primeira nos comentários das issues. Mas o fluxo previa isso: se o cliente comentasse algo como "a mensagem de boas-vindas ficou boa, mas eu queria ela em outra cor", isso viraria uma nova issue (um novo pedido), entrando de novo pelo Todo do quadro até ser atendida e fechada.

## Verdadeiro ou falso?

1. Fluxo de valor é o processo que transforma uma hipótese de negócio em um produto que entrega valor ao cliente. — **Verdadeiro**
2. O monitoramento contínuo só serve para o ambiente de produção. — **Falso** (serve para todas as etapas: desenvolvimento, QA, operações e negócio, não só produção)
3. Controle visual deixa o andamento do trabalho visível para toda a equipe. — **Verdadeiro**
4. No teste contínuo, os testes são feitos só no final do projeto. — **Falso** (são feitos continuamente, a cada mudança, não só no final)
5. O teste A/B depende de mecanismos automatizados, como os que o DevOps facilita. — **Verdadeiro**
