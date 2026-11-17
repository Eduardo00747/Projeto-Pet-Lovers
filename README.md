# PetLovers

Site institucional de uma página para a PetLovers, com apresentação dos serviços, informações sobre a empresa, adoção, equipe, depoimentos e formas de contato.

**Site publicado:** [https://eduardo00747.github.io/Projeto-Pet-Lovers/](https://eduardo00747.github.io/Projeto-Pet-Lovers/)

## Visão geral

O projeto é um site estático e responsivo. O conteúdo e a estrutura ficam em `index.html`; não há aplicação de servidor, banco de dados ou API conectada. Os links do menu e do rodapé navegam para seções da própria página usando identificadores HTML.

## Seções do site

| Seção | Destino | Conteúdo |
| --- | --- | --- |
| Início | `#top` | Cabeçalho, apresentação principal e chamada para contato. |
| Serviços | `#servicos` | Cards de Banho e Tosa, Pet Saúde e Pet Spa. |
| Sobre | `#sobre` | Texto institucional e link para conhecer a equipe. |
| Adoção | `#adocao` | Chamada para adoção e indicadores numéricos. |
| Depoimentos | `#depoimentos` | Carrossel com três exemplos de depoimentos, identificados como fictícios. |
| Equipe | `#equipe` | Apresentação dos membros da equipe. |
| Contato | `#contato` | Telefone, WhatsApp, e-mail, endereço e links rápidos. |

## Funcionalidades e lógica

- **Navegação por âncoras:** o menu do topo e os links rápidos do rodapé apontam para as seções da página. O CSS aplica rolagem suave e um deslocamento superior para considerar o cabeçalho fixo.
- **Menu responsivo:** em telas menores, o SlickNav transforma a lista principal em um menu compacto.
- **Cabeçalho fixo:** `js/main.js` adiciona a classe `sticky` depois que a página passa de 400 px de rolagem.
- **Carrossel de depoimentos:** Owl Carousel exibe um card por vez, em loop e com reprodução automática; as setas ficam disponíveis em telas maiores. As fotos usam recorte circular uniforme. Os textos atuais são fictícios e estão marcados como exemplos.
- **Indicadores animados:** os números da seção de adoção são valores estáticos no HTML; o CounterUp anima sua contagem quando eles entram na área visível.
- **Contatos:** o telefone do topo usa um link `tel:`; o telefone no rodapé abre uma conversa pelo WhatsApp; o e-mail usa `mailto:`. O endereço é apresentado como texto.
- **Ano do rodapé:** um pequeno script JavaScript imprime automaticamente o ano atual.
- **Chamadas para ação:** botões como “Entre em contato” e “Contato” levam à seção de contato.

### Itens que ainda são modelos

- Os números de adoções, consultas e serviços mensais estão fixos no HTML; não vêm de um sistema de dados.
- A chamada “Mais de 40 anos de experiência” também é conteúdo fixo. Confirme os números e as informações institucionais antes de usá-los como dados atuais.
- Os depoimentos estão marcados como fictícios. Substitua textos, nomes e fotos por conteúdo autorizado antes de apresentá-los como avaliações reais.
- A seção da equipe repete o nome “Rala Emaia”. Confirme os nomes e cargos corretos antes da publicação final.
- Os ícones de redes sociais usam `href="#"` e ainda não apontam para perfis reais.
- O site não possui formulário de contato ativo. `contact_process.php` e alguns scripts de formulário são arquivos herdados do template e não estão ligados a um formulário da página. Além disso, o GitHub Pages publica arquivos estáticos e não executa PHP.

## Design e identidade visual

O visual combina elementos de cuidado animal com uma interface leve e acolhedora. O turquesa comunica saúde e confiança; o laranja acrescenta calor e energia; fundos claros, cartões arredondados e fotos de pets mantêm a página amigável e legível.

As cores principais estão definidas como variáveis CSS em `scss/_brand_theme.scss`:

| Variável | Cor | Uso principal |
| --- | --- | --- |
| `--brand-teal` | `#28c6c4` | Destaques e elementos interativos. |
| `--brand-teal-dark` | `#087f83` | Links, cabeçalho superior e estados de foco. |
| `--brand-teal-deep` | `#06676c` | Estados ativos de botões. |
| `--brand-orange` | `#f2a13a` | Acentos e detalhes. |
| `--brand-ink` | `#15363e` | Títulos e texto de alto contraste. |
| `--brand-soft` | `#eefafa` | Fundos suaves. |
| `--brand-border` | `#b9e8e7` | Bordas de cartões. |

Poppins é usada principalmente em títulos e navegação, e Open Sans no texto corrido. As fontes são carregadas do Google Fonts; sem conexão externa, o navegador usa fontes alternativas. O logo principal é um SVG vetorial em `img/logo.svg`, e o favicon é a pata branca em `img/paw-solid-full.svg`.

## Arquitetura e tecnologias

### Estrutura

- **HTML:** `index.html` concentra o conteúdo e as seções da página.
- **SCSS:** `scss/style.scss` importa os módulos de estilo. Arquivos como `_header.scss`, `_testmonial.scss`, `_footer.scss` e `_brand_theme.scss` organizam as regras por área.
- **CSS servido:** `css/style.css` é a folha final carregada pelo HTML, junto com os arquivos de estilo das bibliotecas.
- **JavaScript:** `js/main.js` inicializa o menu móvel, o cabeçalho fixo, o carrossel e as animações usadas na página.
- **Assets:** imagens, ilustrações, logo e favicon ficam em `img/`; fontes de ícones ficam em `fonts/`.
- **Bibliotecas:** Bootstrap e jQuery, além de Owl Carousel, SlickNav, CounterUp, WOW.js e outros plugins são fornecidos localmente em `css/` e `js/`.

### Arquivos principais

```text
index.html                 Página e conteúdo do site
css/style.css              Estilos finais servidos ao navegador
scss/style.scss            Arquivo de entrada dos estilos SCSS
scss/_brand_theme.scss     Cores e personalizações da marca
scss/_header.scss          Cabeçalho e navegação
scss/_testmonial.scss      Depoimentos e cartões
scss/_footer.scss          Rodapé
js/main.js                 Inicialização de interações
img/logo.svg               Logo vetorial
img/paw-solid-full.svg     Favicon branco
img/testmonial/            Fotos dos depoimentos
contact_process.php        Script PHP herdado, não conectado à página atual
readme.txt                 Aviso de licença do template original
```

Não há etapa de build configurada no repositório. Ao alterar estilos, mantenha o SCSS e `css/style.css` sincronizados, pois é o CSS que o site publicado carrega.

## Executar localmente

Como o site é estático, basta servir a pasta do projeto com um servidor local. No Windows, abra o terminal na pasta do repositório e execute:

```powershell
py -m http.server 8000
```

Depois, acesse [http://localhost:8000](http://localhost:8000). Também é possível abrir `index.html` diretamente, mas um servidor local representa melhor a publicação e evita limitações do navegador com alguns recursos.

## Publicação

O endereço público informado para o site é o GitHub Pages:

[https://eduardo00747.github.io/Projeto-Pet-Lovers/](https://eduardo00747.github.io/Projeto-Pet-Lovers/)

O conteúdo é publicado como arquivos estáticos. Alterações devem ser enviadas ao repositório e publicadas pelo fluxo configurado no GitHub Pages.
