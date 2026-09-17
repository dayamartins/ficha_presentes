# 🎁 Ficha de presentes da turma

Um formulário de página única para grupos de amigos preencherem os próprios dados de presente: número do sapato, tamanho de camiseta com medidas, cores que gostam e que evitam, personagens e fandoms, hobbies e lista de desejos.

Cada pessoa preenche, toca em **Gerar mensagem** e recebe um texto pronto, já formatado para o WhatsApp, para colar no grupo. Assim ninguém mais erra o tamanho da camiseta em aniversário.

## Link

👉 https://dayamartins.github.io/ficha_presentes/

(Troque `SEUUSUARIO` pelo seu nome de usuário do GitHub depois de ativar o GitHub Pages.)

## Como funciona

- É um arquivo único, `index.html`, com todo o HTML, CSS e JavaScript dentro. Não usa servidor, banco de dados nem cadastro.
- As respostas ficam salvas no navegador de quem preenche (`localStorage`), então dá para parar no meio e voltar depois no mesmo aparelho.
- Nada é enviado para lugar nenhum. Quem organiza as fichas é o próprio grupo, onde cada um cola a sua.
- Funciona em celular e computador, tem modo escuro automático e todos os campos são opcionais, menos o nome.

## Seções do formulário

| Seção | O que pergunta |
| --- | --- |
| Sobre você | Nome e aniversário (só dia e mês) |
| Calçados | Número, comprimento do pé em cm e observações |
| Camisetas e blusas | Tamanho em letra, busto, comprimento, caimento e modelagens |
| Calças, shorts e saias | Número, cintura e modelos preferidos |
| Acessórios | Aro do anel, furos na orelha, prata ou dourado |
| Cores | Paleta para marcar as que ama e as que evita |
| Personagens e fandoms | Filmes, desenhos, séries, animes, games e música |
| Hobbies | De cerâmica a crochê, mais os tipos de livro favoritos |
| Gostos do dia a dia | Comidas, bebidas, cheiros e estilo |
| Na hora do presente | Lista de desejos, o que não quer ganhar, alergias e restrições |

## Como publicar (GitHub Pages)

1. Crie um repositório público e envie o `index.html` nele.
2. Vá em **Settings → Pages**.
3. Em **Source**, escolha **Deploy from a branch**; em **Branch**, `main` e a pasta `/ (root)`. Salve.
4. Em um a três minutos o endereço aparece nessa mesma tela. Mande esse link no grupo.

## Como personalizar

As perguntas ficam todas na constante `SECTIONS`, dentro do `<script>` no final do `index.html`. Cada campo é um objeto:

```js
{ id: "sapato_num", label: "Número", placeholder: "ex: 37", half: true }
```

- `type`: `"text"` (padrão), `"textarea"`, `"chips"`, `"colors"` ou `"daymonth"`
- `options`: as opções, quando o tipo é `chips`
- `single: true`: permite marcar só uma opção
- `half: true`: o campo ocupa meia largura
- `unit`: sufixo dentro do campo, como `cm`
- `hint`: textinho de ajuda embaixo

Para mudar as cores do visual, edite as variáveis em `:root`, no começo do CSS. Lembre de ajustar também o bloco de modo escuro logo abaixo.

## Privacidade

O repositório é público, então o código fica visível para qualquer pessoa. As respostas, não: elas nunca saem do aparelho de quem preencheu. Quem quiser apagar as próprias respostas é só usar o botão **Apagar tudo e começar de novo**, na tela final.
