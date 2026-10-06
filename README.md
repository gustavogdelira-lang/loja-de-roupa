# Guardiãs — Ponto de Ajuda camuflado em uma loja de roupas

Projeto de tecnologia social para a segurança de mulheres em bares, restaurantes e casas de shows.
Um QR Code dentro da cabine do banheiro abre o site de uma loja de roupas. O pedido de ajuda fica dentro do
chat de atendimento da loja, e a equipe do local recebe o alerta ao vivo no celular, com o número da cabine.

## O que tem neste repositório

    index.html, css/, js/     Demonstração visual (funciona direto no GitHub Pages, sem servidor)
    projeto-completo/         Sistema real: servidor Node.js, painel da equipe e gerador de QR Codes
    render.yaml               Configuração para publicar o sistema real na Render

## 1. Ver o site no ar (GitHub Pages)

1. No repositório, abra **Settings > Pages**.
2. Em **Build and deployment**, escolha **Deploy from a branch**.
3. Selecione a branch `main` e a pasta `/ (root)`, e clique em **Save**.
4. Em cerca de um minuto, o site fica em `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

A demonstração mostra a loja e o chat de atendimento. A barra escura do topo alterna entre a **visão da cliente**
e a **visão da equipe**. Os alertas são simulados no próprio navegador.

Para testar: no chat, toque em "Estou sendo seguida", abra "Visão da equipe", toque em "Vou atender" e volte
para "Visão da cliente". O chat avisa que a atendente está a caminho.

## 2. Colocar o sistema real no ar (Render)

1. Em render.com, entre com o GitHub e escolha **New > Blueprint**, selecionando este repositório.
2. Preencha `PAINEL_SENHA` (pelo menos 8 caracteres) e `NOME_LOCAL`.
3. Aguarde o deploy. O endereço será parecido com `https://guardias-ponto-de-ajuda.onrender.com`.
4. Abra `/painel` nos celulares da gerência e da segurança.
5. Abra `/qr`, gere os adesivos e imprima um por cabine.

O plano gratuito "dorme" por inatividade e leva cerca de um minuto para acordar. Para uso real, troque
`plan: free` por `plan: starter` no `render.yaml`.

## Como funciona

- Sem `?c=` no endereço, quem abre vê só a loja.
- O QR Code de cada cabine abre `/ajuda?c=NÚMERO`. Nesse endereço o chat abre sozinho e as respostas rápidas viram o pedido.
- Fechar o chat (botão, X ou Esc) apaga a conversa do aparelho e deixa só a loja na tela.
- O sistema guarda só cabine, tipo de pedido e horário, sem dados pessoais.

## Antes de usar de verdade

Treine a equipe, teste cada QR Code e mantenha o painel aberto com som durante o expediente.
Em risco imediato, ligue 190. Para orientação e denúncia de violência contra a mulher, ligue 180.
