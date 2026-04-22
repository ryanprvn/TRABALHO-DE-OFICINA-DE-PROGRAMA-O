================================================================
  LOJA BELLA — PROJETO DE E-COMMERCE EM HTML E CSS PURO
  README — Guia para iniciantes
================================================================

ÍNDICE:
  1. Como abrir o site
  2. Estrutura de pastas
  3. Como trocar imagens
  4. Como alterar textos (nome, preço, etc.)
  5. Como adicionar novos produtos
  6. Como adicionar novos links no menu
  7. Como alterar as cores do site
  8. Sobre o carrinho
  9. Dicas para trabalho em dupla

================================================================
  1. COMO ABRIR O SITE
================================================================

Não é necessário nenhum servidor ou instalação.

  Passo 1: Abra a pasta "loja-virtual" no seu computador.
  Passo 2: Entre na pasta "pages".
  Passo 3: Dê dois cliques em "index.html".
  Passo 4: O site abrirá no seu navegador padrão.

Para abrir a página de login: abra "login.html" da mesma forma.

================================================================
  2. ESTRUTURA DE PASTAS
================================================================

  loja-virtual/
  │
  ├── pages/
  │   ├── index.html     ← Página inicial (home)
  │   └── login.html     ← Página de login
  │
  ├── css/
  │   ├── style.css      ← Estilos globais (header, produtos, footer)
  │   └── login.css      ← Estilos exclusivos da página de login
  │
  ├── assets/
  │   ├── images/        ← Coloque aqui as imagens dos produtos
  │   └── icons/         ← Coloque aqui ícones personalizados
  │
  └── README.txt         ← Este arquivo

================================================================
  3. COMO TROCAR IMAGENS DOS PRODUTOS
================================================================

Atualmente, os produtos exibem um texto placeholder no lugar
das imagens. Para adicionar imagens reais:

  Passo 1: Coloque o arquivo de imagem na pasta:
           loja-virtual/assets/images/
           Exemplo: "camiseta.jpg"

  Passo 2: Abra o arquivo pages/index.html em um editor de texto.

  Passo 3: Encontre o produto que deseja atualizar.
           Procure por: <div class="product-image-placeholder">

  Passo 4: Substitua TODA a <div class="product-image-placeholder">
           pelo código de imagem abaixo:

           <img
             src="../assets/images/camiseta.jpg"
             alt="Descrição da imagem"
           />

  Exemplo antes:
  ┌──────────────────────────────────────────────────────────────┐
  │ <div class="product-image-placeholder">                      │
  │   Coloque sua imagem aqui                                    │
  │   <small>(320 × 240 px recomendado)</small>                  │
  │ </div>                                                       │
  └──────────────────────────────────────────────────────────────┘

  Exemplo depois:
  ┌──────────────────────────────────────────────────────────────┐
  │ <img                                                         │
  │   src="../assets/images/camiseta.jpg"                        │
  │   alt="Camiseta básica branca"                               │
  │ />                                                           │
  └──────────────────────────────────────────────────────────────┘

FORMATOS aceitos: .jpg, .jpeg, .png, .webp, .gif
TAMANHO recomendado: 320 × 240 px (proporção 4:3)

================================================================
  4. COMO ALTERAR TEXTOS
================================================================

--- NOME DO PRODUTO ---
No index.html, procure por:
  <h3 class="product-name">Camiseta Básica Premium</h3>
Troque o texto entre as tags pelo novo nome.

--- PREÇO DO PRODUTO ---
No index.html, procure por:
  <span class="product-price">R$ 59,90</span>
Troque o valor pelo novo preço.

--- PREÇO ORIGINAL (RISCADO) ---
No index.html, procure por:
  <span class="product-price-original">R$ 89,90</span>
Se não houver desconto, apague essa linha inteira.

--- NOME DA LOJA ---
Em TODOS os arquivos HTML, procure por:
  Loja<span>Bella</span>
Troque "Loja" e "Bella" pelo nome desejado.

--- TEXTOS DO BANNER ---
No index.html, procure por:
  <h1 class="banner-titulo">
Troque o conteúdo entre as tags.

================================================================
  5. COMO ADICIONAR NOVOS PRODUTOS
================================================================

  Passo 1: Abra pages/index.html em um editor de texto.

  Passo 2: Encontre o comentário:
           <!-- FIM PRODUTO 6 -->

  Passo 3: Cole o código abaixo LOGO APÓS esse comentário:

  ┌──────────────────────────────────────────────────────────────┐
  │ <!-- PRODUTO 7 -->                                           │
  │ <article class="product-card">                               │
  │                                                              │
  │   <div class="product-image-wrapper">                        │
  │     <div class="product-image-placeholder">                  │
  │       Coloque sua imagem aqui                                │
  │     </div>                                                   │
  │   </div>                                                     │
  │                                                              │
  │   <div class="product-info">                                 │
  │     <span class="product-category">Categoria</span>         │
  │     <h3 class="product-name">Nome do Produto</h3>           │
  │     <div class="product-price-area">                         │
  │       <span class="product-price">R$ 00,00</span>           │
  │     </div>                                                   │
  │   </div>                                                     │
  │                                                              │
  │   <div class="product-footer">                               │
  │     <a href="#" class="botao-carrinho">                      │
  │       Adicionar ao carrinho                                  │
  │     </a>                                                     │
  │   </div>                                                     │
  │                                                              │
  │ </article>                                                   │
  └──────────────────────────────────────────────────────────────┘

  Passo 4: Altere "Categoria", "Nome do Produto" e "R$ 00,00".
  Passo 5: Salve e recarregue o navegador.

================================================================
  6. COMO ADICIONAR LINKS NO MENU
================================================================

  No index.html e login.html, encontre:
    <nav class="header-nav">

  Adicione um novo link seguindo o padrão:
    <a href="pagina.html">Nome do Link</a>

================================================================
  7. COMO ALTERAR AS CORES DO SITE
================================================================

  Abra css/style.css e encontre a seção :root no início.
  Cada variável de cor está comentada com sua função.

  Exemplo — para mudar a cor de destaque (botões):
    Antes:  --cor-destaque: #e94560;
    Depois: --cor-destaque: #3498db;   ← azul

  Isso altera AUTOMATICAMENTE todas as partes que usam essa cor.

================================================================
  8. SOBRE O CARRINHO
================================================================

O carrinho é 100% visual — não há JavaScript neste projeto.
Ele exibe os itens, preços e o total apenas para fins de layout.

Para exibi-lo permanentemente na tela:
  Abra css/style.css, encontre .cart-container e troque:
    display: none;    ←  por →    display: flex;

Para funcionalidade real no futuro, será necessário JavaScript
ou uma integração com backend.

================================================================
  9. DICAS PARA TRABALHO EM DUPLA
================================================================

  → Dividam os arquivos: uma pessoa cuida do HTML,
    outra do CSS.

  → Cada produto no HTML está claramente separado por comentários
    como <!-- PRODUTO 1 -->, <!-- FIM PRODUTO 1 -->.

  → Para evitar conflitos: uma pessoa adiciona produtos,
    outra altera cores e fontes.

  → Testem sempre em pelo menos dois navegadores diferentes
    (Chrome e Firefox são ótimas opções).

  → Usem o VS Code com a extensão "Live Server" para ver
    as mudanças em tempo real ao salvar os arquivos.

================================================================
  FIM DO README
  Dúvidas? Leia os comentários dentro de cada arquivo!
================================================================
