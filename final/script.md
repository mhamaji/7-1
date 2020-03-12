# DAY 1 BLOCK 7 - RESPONSIVE CSS

---

O objetivo dessa aula é demonstrar para os alunos como transformar uma página que foi criada sem pensar em como ela seria em diferentes tamanhos de telas, em uma página com design responsivo.

Os arquivos `index.html` e `styles.css` possuem as versões finais do projeto e o diretório `images` contém as imagens utilizadas.

---

## Aula ao vivo

Para começar vamos pegar o código inicial que vamos usar do GitHub. Essa página foi criada pelo nosso monitor Jean como um template do projeto de _HTML_ e _CSS_ da segunda semana do curso.

* Clone o [repositório](https://betrybe.github.io/) e crie uma branch para desenvolver o código:

  * `git clone https://github.com/betrybe/betrybe.github.io.git` _(baixa os arquivos do repositório remoto para a sua máquina)_;

  * `cd betrybe.github.io` _(entre na pasta do projeto)_;

  * `git branch` _(verifique que você está na branch `master`)_;

  * `git checkout -b live-lecture/7.2` _(cria uma branch separada para desenvolver o projeto)_;

* Abra o arquivo `index.html` no seu browser localmente. Vamos analisar a estrutura da página:

  * A primeira coisa que vemos é que temos um _header_ fixo (em azul na tela). Role a página para mostrar que ele fica fixado no topo da página.

  * Agora mude para o código _HTML_ da página e mostre o código referente ao _header_. Nas linhas **9** até **11** identifique a `div` com a classe `top-bar`;

  * Mude de volta para o browser e mostre que a segunda parte destacada da página é onde estão a foto do filme e a sua descrição (em verde claro na tela).

  * De volta para o código _HTML_, mostre o código referente à descrição do filme e a imagem. Nas linhas **13** até **29** identifique o `h2`com a classe `movie-title`, a `div` com a classe `media-content` e a `div` com a classe `movie-description`.

  * De volta ao browser, a próxima parte a se destacar são os detalhes sobre o filme (em verde escuro na tela).

  * No código _HTML_ mostre o código referente ao elenco do filme e os prêmios. Nas linhas **30** a **94** identifique a `div` com a classe `movie-details` que se divide em uma `div` com a classe `movie-cast` e outra `div` com a classe `movie-awards`.

  * De volta ao browser, a úlima parte da página que temos é o _footer_ (em vermelho na tela). Nas linhas **96** a **104** identifique a `div` com a classe `footer`.


* Agora, vamos ver como fica a visualização da página em um dispositivo móvel:

  * No browser, use o _inspect_ para alterar a visualização da página para o modo _responsivo_;

  * Fique redimensionando a largura da tela para demonstrar que a disposição dos elementos não muda independente da largura da tela;

* O que seria legal alterar nessa página quando estivermos vendo ela em uma tela pequena? Vamos colocar alguns objetivos agora:

  * Vamos considerar uma tela pequena quando tivermos uma largura menor que `360px`. Quando a largura da tela for essa, queremos as seguintes mudanças na página:

    * Queremos que o _header_ não fique fixo na tela, _(ela já tem pouco espaço disponível e o header só vai ocupar mais ainda desse espaço)_;

    * Queremos que a imagem não apareça na tela _(geralmente a conexão com a internet é pior em dispositivos móveis, então queremos que a página carregue somente texto)_;

    * Queremos que o espaçamento entre as linhas seja maior _(isso vai facilitar a leitura)_;

    * A tabela com o elenco do filme e a lista de prêmios devem ficar um abaixo do outro;

    * O _footer_ deveria ocupar menos espaço na tela. Que tal o mesmo espaço ocupado pelo _header_ ?


* Agora vamos colocar a mão na massa. Crie uma media query com o breakpoint `screen and max-width: 360px` que é onde vamos colocar as modificações no _CSS_;

  * `screen` quer dizer que queremos que o estilo seja aplicado quando a página estiver sendo mostrada em uma tela. Um outro tipo seria o `print` por exemplo, que é quando a página estiver sendo mostrada para impressão;

  * `max-width: 360px` quer dizer que o estilo vai ser aplicado quando a largura da tela for de até `360px`, ou seja, para telas maiores que essa o estilo não vai ser aplicado;

* Vamos apenas mudar a cor do _header_ por enquanto para verificar que a media query está funcionando:

```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar {
  background-color: #506693;
  position: fixed;
  top: 0px;
  left: 0px;
  width: 100%;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
  margin-top: 80px;
}

.main-content .movie-title {
  width: 100%;
  text-align: center;
  padding-top: 20px;
}

.main-content .media-content {
  width: 100%;
  margin-bottom: 50px;
}

.main-content .media-content img {
  height: 360px;
  width: auto;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-description {
  margin: 0px 30px 0 30px;
}

.main-content .movie-description small {
  display: block;
  text-align: right;
}

.main-content .movie-details {
  width: 100%;
  background-color: #669B65;
}

.main-content .movie-details .movie-cast {
  float: left;
  width: 50%;
  background-color: inherit;
}

.main-content .movie-details .movie-cast h3 {
  text-align: center;
}

.main-content .movie-details .movie-cast table {
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-details .movie-cast table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}

.main-content .movie-details .movie-cast th, td {
  padding: 15px;
}

.main-content .movie-details .movie-awards {
  float: right;
  width: 50%;
  background-color: inherit;
}

.clear {
  clear: both
}

.footer {
  background-color: #B75952;
  margin-top: 0px;
  padding-bottom: 30px;
}

.footer .movie-external-content {
  margin-top: 0px;
  margin-left: auto;
  margin-right: auto;
  padding-top: 30px;
  padding-left: 30px;
} */

@media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
  }
}
```

Ué, a _media query_ já está lá, mas não funciona! 😱 O que está faltando? 🤔

* Mostre o código _HTML_. No `head` da página está faltando uma _meta tag_:

```html
<!-- <head>
  <meta charset="UTF-8"> -->
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <!-- <title>Projeto Final de HTML e CSS</title>
  <link rel="stylesheet" href="styles.css" type="text/css" charset="utf-8">
</head> -->
```

* Explique o que essa _tag_ faz:

  * A _meta tag_ de viewport dá instruções ao navegador de como controlar as dimensões e a escala (zoom) da página;

  * A parte que fala `width=device-width` diz que a largura da página deve ser a largura do dipositivo que está exibindo ela _(o que pode variar se for uma tela de PC ou de celular, por exemplo)_.

  * A parte que fala `initial-scale=1` diz que o nível de zoom da página quando ela é carregada é 1.

  * Link do [W3Schools](https://www.w3schools.com/css/css_rwd_viewport.asp) sobre a tag;

* Adicione essa meta tag ao código _HTML_ e recarregue a página. Agora quando a largura estiver menor que `360px` a cor de fundo do header vai mudar!

---

### Fazendo small commits

Estamos usando Git para desenvolver essa página, não é? Agora que já conseguimos o que precisamos para fazer uma _media query_ que tal fazermos um belo `commit` com as nossas alterações?


* Vá para o terminal e faça: `git status` _(mostre que você está na `branch` certa)_;

* `git diff` _(mostre as diferenças no código)_;

* `git add .`;

* `git status` _(mostre os arquivos adicionados ao stage do Git)_;

* `git commit -m "Adicionando a meta tag viewport. Criando o primeiro media query. "`

* `git status` _(mostre que o commit foi feito localmente: "nothing to commit")_;

* `git log` _(mostr que o commit está no log do Git local)_;

* `git push -u origin live-lecture/7.2` _(mostre que foi criada uma nova branch no repositório remoto)_;

* Vá para a [página do GitHub do repositório](https://github.com/betrybe/betrybe.github.io) e mostre a nova branch com o novo `commit`;

* `git status` _(agora está tudo "commitado", vamos continuar o desenvolvimento!)_

Vamos criar um pull request para ficar mais fácil visualizar as mudanças que estamos fazendo:

* Na página do repositório, crie um novo _Pull Request_ com a branch que estamos usando para a aula;

* Coloque seu usuário como "Assignee";

* Coloque a label "in-progress";

* Na descrição do PR, coloque as alterações que vamos fazer na página:

```
Este Pull Request tem o objetivo de alterar o estilo da página para ser responsivo e com uma abordagem mobile first!

Estamos considerando uma tela pequena quando tivermos uma largura menor que `360px`. Quando a largura da tela for essa, queremos as seguintes mudanças na página:

- [ ] Queremos que o _header_ não fique fixo na tela, _(ela já tem pouco espaço disponível e o _header_ só vai ocupar mais ainda desse espaço)_;

- [ ] Queremos que a imagem não apareça na tela _(geralmente a conexão com a internet é pior em dispositivos móveis, então queremos que a página carregue somente texto)_;

- [ ] Queremos que o espaçamento entre as linhas seja maior _(isso vai facilitar a leitura)_;

- [ ] A tabela com o elenco do filme e a lista de prêmios devem ficar um abaixo do outro;

- [ ] O _footer_ deveria ocupar menos espaço na tela. Que tal o mesmo espaço ocupado pelo _header_ ?

```

* Abra o Pull Request. Mostre a aba "Files changed" com as alterações.


---

### Vamos aos objetivos

1. Nosso primeiro objetivo é que o _header_ não fique fixo na tela. Vamos alterar isso!

```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar {
  background-color: #506693;
  position: fixed;
  top: 0px;
  left: 0px;
  width: 100%;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
  margin-top: 80px;
}

.main-content .movie-title {
  width: 100%;
  text-align: center;
  padding-top: 20px;
}

.main-content .media-content {
  width: 100%;
  margin-bottom: 50px;
}

.main-content .media-content img {
  height: 360px;
  width: auto;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-description {
  margin: 0px 30px 0 30px;
}

.main-content .movie-description small {
  display: block;
  text-align: right;
}

.main-content .movie-details {
  width: 100%;
  background-color: #669B65;
}

.main-content .movie-details .movie-cast {
  float: left;
  width: 50%;
  background-color: inherit;
}

.main-content .movie-details .movie-cast h3 {
  text-align: center;
}

.main-content .movie-details .movie-cast table {
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-details .movie-cast table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}

.main-content .movie-details .movie-cast th, td {
  padding: 15px;
}

.main-content .movie-details .movie-awards {
  float: right;
  width: 50%;
  background-color: inherit;
}

.clear {
  clear: both
}

.footer {
  background-color: #B75952;
  margin-top: 0px;
  padding-bottom: 30px;
}

.footer .movie-external-content {
  margin-top: 0px;
  margin-left: auto;
  margin-right: auto;
  padding-top: 30px;
  padding-left: 30px;
} */

/*@media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b; */
    position: static;
  /* } */
/* } */
```

* Vá para o browser e mostre que quando a tela é redimensionada, o _header_ não está mais fixo;

* Faça um novo commit:

  * `git status`

  * `git add projects/html-css/styles.css`

  * `git diff --cached` _(mostre que dá pra ver as diferenças após o `git add` com a opção `--cached`)_

  * `git status`

  * `git commit -m "Tirando a posicao fixa do header em telas pequenas."`

  * `git status`

  * `git push origin live-lecture/7.2`

  * `git status`

* Vá até o PR e marque o primeiro _checkbox_!

2. O segundo objetivo é que a imagem não apareça na tela:

```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar {
  background-color: #506693;
  position: fixed;
  top: 0px;
  left: 0px;
  width: 100%;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
  margin-top: 80px;
}

.main-content .movie-title {
  width: 100%;
  text-align: center;
  padding-top: 20px;
}

.main-content .media-content {
  width: 100%;
  margin-bottom: 50px;
}

.main-content .media-content img {
  height: 360px;
  width: auto;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-description {
  margin: 0px 30px 0 30px;
}

.main-content .movie-description small {
  display: block;
  text-align: right;
}

.main-content .movie-details {
  width: 100%;
  background-color: #669B65;
}

.main-content .movie-details .movie-cast {
  float: left;
  width: 50%;
  background-color: inherit;
}

.main-content .movie-details .movie-cast h3 {
  text-align: center;
}

.main-content .movie-details .movie-cast table {
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-details .movie-cast table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}

.main-content .movie-details .movie-cast th, td {
  padding: 15px;
}

.main-content .movie-details .movie-awards {
  float: right;
  width: 50%;
  background-color: inherit;
}

.clear {
  clear: both
}

.footer {
  background-color: #B75952;
  margin-top: 0px;
  padding-bottom: 30px;
}

.footer .movie-external-content {
  margin-top: 0px;
  margin-left: auto;
  margin-right: auto;
  padding-top: 30px;
  padding-left: 30px;
}

@media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  } */

  .media-content {
    display: none;
  }
/* } */

```

* Vá para o browser e mostre que quando a tela é redimensionada, a imagem desaparece;

* Faça um novo commit:

  * `git status`

  * `git add projects/html-css/styles.css`

  * `git status`

  * `git commit -m "Escondendo a imagem quando a tela é pequena"`

  * `git status`

  * `git push origin live-lecture/7.2`

  * `git status`

* Vá até o PR e marque o segundo _checkbox_!

3. Agora queremos que o espaçamento entre as linhas seja maior, para facilitar a leitura:

```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar {
  background-color: #506693;
  position: fixed;
  top: 0px;
  left: 0px;
  width: 100%;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
  margin-top: 80px;
}

.main-content .movie-title {
  width: 100%;
  text-align: center;
  padding-top: 20px;
}

.main-content .media-content {
  width: 100%;
  margin-bottom: 50px;
}

.main-content .media-content img {
  height: 360px;
  width: auto;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-description {
  margin: 0px 30px 0 30px;
}

.main-content .movie-description small {
  display: block;
  text-align: right;
}

.main-content .movie-details {
  width: 100%;
  background-color: #669B65;
}

.main-content .movie-details .movie-cast {
  float: left;
  width: 50%;
  background-color: inherit;
}

.main-content .movie-details .movie-cast h3 {
  text-align: center;
}

.main-content .movie-details .movie-cast table {
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-details .movie-cast table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}

.main-content .movie-details .movie-cast th, td {
  padding: 15px;
}

.main-content .movie-details .movie-awards {
  float: right;
  width: 50%;
  background-color: inherit;
}

.clear {
  clear: both
}

.footer {
  background-color: #B75952;
  margin-top: 0px;
  padding-bottom: 30px;
}

.footer .movie-external-content {
  margin-top: 0px;
  margin-left: auto;
  margin-right: auto;
  padding-top: 30px;
  padding-left: 30px;
}

@media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  }

  .media-content {
    display: none;
  } */

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }
/* } */

```

* Vá para o browser e mostre que quando a tela é redimensionada, o tipo da fonte muda e o espaçamento aumenta;

* Faça um novo commit:

  * `git status`

  * `git add .`

  * `git status`

  * `git commit -m "Aumentando o espaçamento das linhas quando a tela é menor"`

  * `git status`

  * `git push origin live-lecture/7.2`

  * `git status`

* Vá até o PR e marque o terceiro _checkbox_!

4. Nosso quarto objetivo é fazer com que a tabela e os prêmios do filme sejam dispostos um abaixo do outro:

```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar {
  background-color: #506693;
  position: fixed;
  top: 0px;
  left: 0px;
  width: 100%;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
  margin-top: 80px;
}

.main-content .movie-title {
  width: 100%;
  text-align: center;
  padding-top: 20px;
}

.main-content .media-content {
  width: 100%;
  margin-bottom: 50px;
}

.main-content .media-content img {
  height: 360px;
  width: auto;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-description {
  margin: 0px 30px 0 30px;
}

.main-content .movie-description small {
  display: block;
  text-align: right;
}

.main-content .movie-details {
  width: 100%;
  background-color: #669B65;
}

.main-content .movie-details .movie-cast {
  float: left;
  width: 50%;
  background-color: inherit;
}

.main-content .movie-details .movie-cast h3 {
  text-align: center;
}

.main-content .movie-details .movie-cast table {
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-details .movie-cast table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}

.main-content .movie-details .movie-cast th, td {
  padding: 15px;
}

.main-content .movie-details .movie-awards {
  float: right;
  width: 50%;
  background-color: inherit;
}

.clear {
  clear: both
}

.footer {
  background-color: #B75952;
  margin-top: 0px;
  padding-bottom: 30px;
}

.footer .movie-external-content {
  margin-top: 0px;
  margin-left: auto;
  margin-right: auto;
  padding-top: 30px;
  padding-left: 30px;
}

@media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  }

  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  } */

  .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }

/* } */
```

* Vá para o browser e mostre que quando a tela é redimensionada, a tabela com o elenco e a lista de premiações são mostradas uma abaixo da outra;

* Faça um novo commit:

  * `git status`

  * `git add .`

  * `git status`

  * `git commit -m "Alterando a disposição do layout do elenco e premiações"`

  * `git status`

  * `git push origin live-lecture/7.2`

  * `git status`

* Vá até o PR e marque o quarto _checkbox_!

5. Nosso último objetivo é fazer com que o _footer_ ocupe menos espaço na tela:

```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar {
  background-color: #506693;
  position: fixed;
  top: 0px;
  left: 0px;
  width: 100%;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
  margin-top: 80px;
}

.main-content .movie-title {
  width: 100%;
  text-align: center;
  padding-top: 20px;
}

.main-content .media-content {
  width: 100%;
  margin-bottom: 50px;
}

.main-content .media-content img {
  height: 360px;
  width: auto;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-description {
  margin: 0px 30px 0 30px;
}

.main-content .movie-description small {
  display: block;
  text-align: right;
}

.main-content .movie-details {
  width: 100%;
  background-color: #669B65;
}

.main-content .movie-details .movie-cast {
  float: left;
  width: 50%;
  background-color: inherit;
}

.main-content .movie-details .movie-cast h3 {
  text-align: center;
}

.main-content .movie-details .movie-cast table {
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-details .movie-cast table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}

.main-content .movie-details .movie-cast th, td {
  padding: 15px;
}

.main-content .movie-details .movie-awards {
  float: right;
  width: 50%;
  background-color: inherit;
}

.clear {
  clear: both
}

.footer {
  background-color: #B75952;
  margin-top: 0px;
  padding-bottom: 30px;
}

.footer .movie-external-content {
  margin-top: 0px;
  margin-left: auto;
  margin-right: auto;
  padding-top: 30px;
  padding-left: 30px;
}

@media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  }

  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }

    .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }
 */

  .footer {
    padding: 0px;
  }

  .footer .movie-external-content {
    padding: 0px;
    margin: 0px;
  }
/* } */
```

* Vá para o browser e mostre que quando a tela é redimensionada, o footer fica menor, sem `padding` e sem `margin`;

* Faça um novo commit:

  * `git status`

  * `git add .`

  * `git status`

  * `git commit -m "Diminuindo o tamanho do footer "`

  * `git status`

  * `git push origin live-lecture/7.2`

  * `git status`

* Vá até o PR e marque o último _checkbox_!

---

## Pensando no mobile primeiro


Pergunte aos alunos:

> "Vocês repararam que coloquei o _CSS_ com a media query no final do arquivo? O que vocês acham que aconteceria se eu adicionasse ela no início do arquivo?"

* Coloque a _media query_ no início do arquivo _CSS_ e recarregue a página:

```css
@media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  }

  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }

  .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }

  .footer {
    padding: 0px;
  }

  .footer .movie-external-content {
    padding: 0px;
    margin: 0px;
  }
}
/*
body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar {
  background-color: #506693;
  position: fixed;
  top: 0px;
  left: 0px;
  width: 100%;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
  margin-top: 80px;
}

.main-content .movie-title {
  width: 100%;
  text-align: center;
  padding-top: 20px;
}

.main-content .media-content {
  width: 100%;
  margin-bottom: 50px;
}

.main-content .media-content img {
  height: 360px;
  width: auto;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-description {
  margin: 0px 30px 0 30px;
}

.main-content .movie-description small {
  display: block;
  text-align: right;
}

.main-content .movie-details {
  width: 100%;
  background-color: #669B65;
}

.main-content .movie-details .movie-cast {
  float: left;
  width: 50%;
  background-color: inherit;
}

.main-content .movie-details .movie-cast h3 {
  text-align: center;
}

.main-content .movie-details .movie-cast table {
  margin-left: auto;
  margin-right: auto;
}

.main-content .movie-details .movie-cast table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}

.main-content .movie-details .movie-cast th, td {
  padding: 15px;
}

.main-content .movie-details .movie-awards {
  float: right;
  width: 50%;
  background-color: inherit;
}

.clear {
  clear: both
}

.footer {
  background-color: #B75952;
  margin-top: 0px;
  padding-bottom: 30px;
}

.footer .movie-external-content {
  margin-top: 0px;
  margin-left: auto;
  margin-right: auto;
  padding-top: 30px;
  padding-left: 30px;
} */

```

Vejam que a _media query_ foi sobrescrita pelas outras regras de _CSS_ da página! Isso porque o _CSS_ é interpretado **de cima pra baixo**, ou seja, as regras que aparecem mais no final do arquivo podem substituir as regras que foram definidas mais acima.

É importante ficar sempre atento para isso para evitar confusões com seus estilos! 😉

E então, como podemos resolver isso? Já ficou claro que o _CSS_ dessa página não foi pensado com a abordagem _mobile first_, não é?!

Vamos alterar isso!

* Primeiro, vamos criar uma outra media query e colocar os estilos existentes dentro dela:

```css
/* @media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  }

  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }

  .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }


  .footer {
    padding: 0px;
  }

  .footer .movie-external-content {
    padding: 0px;
    margin: 0px;
  }
} */

@media screen and (min-width: 360px) {

  /* body {
    font-family: "Times New Roman", Times, serif;
    margin: 0px;
  }

  .top-bar {
    background-color: #506693;
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
  }

  .top-bar .title {
    font-style: italic;
    color: white;
    text-align: center;
  }

  .main-content {
    background-color: #A6BD66;
    margin-top: 80px;
  }

  .main-content .movie-title {
    width: 100%;
    text-align: center;
    padding-top: 20px;
  }

  .main-content .media-content {
    width: 100%;
    margin-bottom: 50px;
  }

  .main-content .media-content img {
    height: 360px;
    width: auto;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-description {
    margin: 0px 30px 0 30px;
  }

  .main-content .movie-description small {
    display: block;
    text-align: right;
  }

  .main-content .movie-details {
    width: 100%;
    background-color: #669B65;
  }

  .main-content .movie-details .movie-cast {
    float: left;
    width: 50%;
    background-color: inherit;
  }

  .main-content .movie-details .movie-cast h3 {
    text-align: center;
  }

  .main-content .movie-details .movie-cast table {
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-details .movie-cast table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
  }

  .main-content .movie-details .movie-cast th, td {
    padding: 15px;
  }

  .main-content .movie-details .movie-awards {
    float: right;
    width: 50%;
    background-color: inherit;
  }

  .clear {
    clear: both
  }

  .footer {
    background-color: #B75952;
    margin-top: 0px;
    padding-bottom: 30px;
  }

  .footer .movie-external-content {
    margin-top: 0px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 30px;
    padding-left: 30px;
  } */
}
```

* Vamos extrair o estilo da tag `body`:

```css
 body {
    font-family: "Times New Roman", Times, serif;
    margin: 0px;
  }

/* @media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  }

  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }

  .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }

  .footer {
    padding: 0px;
  }

  .footer .movie-external-content {
    padding: 0px;
    margin: 0px;
  }
} */

/* @media screen and (min-width: 360px) {

  body {
    font-family: "Times New Roman", Times, serif;
    margin: 0px;
  }

  .top-bar {
    background-color: #506693;
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
  }

  .top-bar .title {
    font-style: italic;
    color: white;
    text-align: center;
  }

  .main-content {
    background-color: #A6BD66;
    margin-top: 80px;
  }

  .main-content .movie-title {
    width: 100%;
    text-align: center;
    padding-top: 20px;
  }

  .main-content .media-content {
    width: 100%;
    margin-bottom: 50px;
  }

  .main-content .media-content img {
    height: 360px;
    width: auto;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-description {
    margin: 0px 30px 0 30px;
  }

  .main-content .movie-description small {
    display: block;
    text-align: right;
  }

  .main-content .movie-details {
    width: 100%;
    background-color: #669B65;
  }

  .main-content .movie-details .movie-cast {
    float: left;
    width: 50%;
    background-color: inherit;
  }

  .main-content .movie-details .movie-cast h3 {
    text-align: center;
  }

  .main-content .movie-details .movie-cast table {
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-details .movie-cast table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
  }

  .main-content .movie-details .movie-cast th, td {
    padding: 15px;
  }

  .main-content .movie-details .movie-awards {
    float: right;
    width: 50%;
    background-color: inherit;
  }

  .clear {
    clear: both
  }

  .footer {
    background-color: #B75952;
    margin-top: 0px;
    padding-bottom: 30px;
  }

  .footer .movie-external-content {
    margin-top: 0px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 30px;
    padding-left: 30px;
  }
} */
```

* Agora vamos extrair os estilos do tíulo:


```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
} */

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}


/* @media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  }

  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }

  .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }

  .footer {
    padding: 0px;
  }

  .footer .movie-external-content {
    padding: 0px;
    margin: 0px;
  }
}

@media screen and (min-width: 360px) {

  .top-bar {
    background-color: #506693;
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
  }

  .main-content {
    background-color: #A6BD66;
    margin-top: 80px;
  }

  .main-content .movie-title {
    width: 100%;
    text-align: center;
    padding-top: 20px;
  }

  .main-content .media-content {
    width: 100%;
    margin-bottom: 50px;
  }

  .main-content .media-content img {
    height: 360px;
    width: auto;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-description {
    margin: 0px 30px 0 30px;
  }

  .main-content .movie-description small {
    display: block;
    text-align: right;
  }

  .main-content .movie-details {
    width: 100%;
    background-color: #669B65;
  }

  .main-content .movie-details .movie-cast {
    float: left;
    width: 50%;
    background-color: inherit;
  }

  .main-content .movie-details .movie-cast h3 {
    text-align: center;
  }

  .main-content .movie-details .movie-cast table {
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-details .movie-cast table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
  }

  .main-content .movie-details .movie-cast th, td {
    padding: 15px;
  }

  .main-content .movie-details .movie-awards {
    float: right;
    width: 50%;
    background-color: inherit;
  }

  .clear {
    clear: both
  }

  .footer {
    background-color: #B75952;
    margin-top: 0px;
    padding-bottom: 30px;
  }

  .footer .movie-external-content {
    margin-top: 0px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 30px;
    padding-left: 30px;
  }
} */
```

* Agora vamos colocar o estilo da classe `main-content` em dois lugares. Queremos que a cor se mantenha nos dois tamanhos, mas a margem seja aplicada somente quando a tela for grande:


```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
} */

.main-content {
  background-color: #A6BD66;
}

/* @media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  }

  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }

  .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }

  .footer {
    padding: 0px;
  }

  .footer .movie-external-content {
    padding: 0px;
    margin: 0px;
  }
}

@media screen and (min-width: 360px) {

  .top-bar {
    background-color: #506693;
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
  }
 */
  .main-content {
    margin-top: 80px;
  }

  /* .main-content .movie-title {
    width: 100%;
    text-align: center;
    padding-top: 20px;
  }

  .main-content .media-content {
    width: 100%;
    margin-bottom: 50px;
  }

  .main-content .media-content img {
    height: 360px;
    width: auto;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-description {
    margin: 0px 30px 0 30px;
  }

  .main-content .movie-description small {
    display: block;
    text-align: right;
  }

  .main-content .movie-details {
    width: 100%;
    background-color: #669B65;
  }

  .main-content .movie-details .movie-cast {
    float: left;
    width: 50%;
    background-color: inherit;
  }

  .main-content .movie-details .movie-cast h3 {
    text-align: center;
  }

  .main-content .movie-details .movie-cast table {
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-details .movie-cast table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
  }

  .main-content .movie-details .movie-cast th, td {
    padding: 15px;
  }

  .main-content .movie-details .movie-awards {
    float: right;
    width: 50%;
    background-color: inherit;
  }

  .clear {
    clear: both
  }

  .footer {
    background-color: #B75952;
    margin-top: 0px;
    padding-bottom: 30px;
  }

  .footer .movie-external-content {
    margin-top: 0px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 30px;
    padding-left: 30px;
  }
} */

```

* Agora vamos tirar a margem do título quando a página estiver sendo exibida em tela pequena:

```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
}

@media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  } */

  .top-bar h1 {
    margin: 0px;
  }
/*
  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }

  .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }

  .footer {
    padding: 0px;
  }

  .footer .movie-external-content {
    padding: 0px;
    margin: 0px;
  }
}

@media screen and (min-width: 360px) {

  .top-bar {
    background-color: #506693;
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
  }

  .main-content {
    background-color: #A6BD66;
    margin-top: 80px;
  }

  .main-content .movie-title {
    width: 100%;
    text-align: center;
    padding-top: 20px;
  }

  .main-content .media-content {
    width: 100%;
    margin-bottom: 50px;
  }

  .main-content .media-content img {
    height: 360px;
    width: auto;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-description {
    margin: 0px 30px 0 30px;
  }

  .main-content .movie-description small {
    display: block;
    text-align: right;
  }

  .main-content .movie-details {
    width: 100%;
    background-color: #669B65;
  }

  .main-content .movie-details .movie-cast {
    float: left;
    width: 50%;
    background-color: inherit;
  }

  .main-content .movie-details .movie-cast h3 {
    text-align: center;
  }

  .main-content .movie-details .movie-cast table {
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-details .movie-cast table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
  }

  .main-content .movie-details .movie-cast th, td {
    padding: 15px;
  }

  .main-content .movie-details .movie-awards {
    float: right;
    width: 50%;
    background-color: inherit;
  }

  .clear {
    clear: both
  }

  .footer {
    background-color: #B75952;
    margin-top: 0px;
    padding-bottom: 30px;
  }

  .footer .movie-external-content {
    margin-top: 0px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 30px;
    padding-left: 30px;
  }
} */

```

* Vamos separar o estilo do título, queremos que a largura e o alinhamento sejam aplicados sempre, mas o `padding` somente em telas grandes:

```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
} */

.main-content .movie-title {
  width: 100%;
  text-align: center;
}

/* @media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  }

  .top-bar h1 {
    margin: 0px;
  }

  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }

  .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }

  .footer {
    padding: 0px;
  }

  .footer .movie-external-content {
    padding: 0px;
    margin: 0px;
  }
}

@media screen and (min-width: 360px) {

  .top-bar {
    background-color: #506693;
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
  }

  .main-content {
    background-color: #A6BD66;
    margin-top: 80px;
  } */

  .main-content .movie-title {
    padding-top: 20px;
  }
/*
  .main-content .media-content {
    width: 100%;
    margin-bottom: 50px;
  }

  .main-content .media-content img {
    height: 360px;
    width: auto;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-description {
    margin: 0px 30px 0 30px;
  }

  .main-content .movie-description small {
    display: block;
    text-align: right;
  }

  .main-content .movie-details {
    width: 100%;
    background-color: #669B65;
  }

  .main-content .movie-details .movie-cast {
    float: left;
    width: 50%;
    background-color: inherit;
  }

  .main-content .movie-details .movie-cast h3 {
    text-align: center;
  }

  .main-content .movie-details .movie-cast table {
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-details .movie-cast table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
  }

  .main-content .movie-details .movie-cast th, td {
    padding: 15px;
  }

  .main-content .movie-details .movie-awards {
    float: right;
    width: 50%;
    background-color: inherit;
  }

  .clear {
    clear: both
  }

  .footer {
    background-color: #B75952;
    margin-top: 0px;
    padding-bottom: 30px;
  }

  .footer .movie-external-content {
    margin-top: 0px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 30px;
    padding-left: 30px;
  }
} */

```

* Agora vamos adicionar um pouco de `padding` e `margin` ao título quando estivermos na tela pequena:

```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
}

.main-content .movie-title {
  width: 100%;
  text-align: center;
}

@media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  } */

  .top-bar h1 {
    margin: 0px;
    padding: 0.5em;
  }

  .movie-title {
    margin: 0px;
    padding: 0.5em 0;
  }
/*
  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }

  .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }

  .footer {
    padding: 0px;
  }

  .footer .movie-external-content {
    padding: 0px;
    margin: 0px;
  }
}

@media screen and (min-width: 360px) {

  .top-bar {
    background-color: #506693;
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
  }

  .main-content {
    background-color: #A6BD66;
    margin-top: 80px;
  }

  .main-content .movie-title {
    padding-top: 20px;
  }

  .main-content .media-content {
    width: 100%;
    margin-bottom: 50px;
  }

  .main-content .media-content img {
    height: 360px;
    width: auto;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-description {
    margin: 0px 30px 0 30px;
  }

  .main-content .movie-description small {
    display: block;
    text-align: right;
  }

  .main-content .movie-details {
    width: 100%;
    background-color: #669B65;
  }

  .main-content .movie-details .movie-cast {
    float: left;
    width: 50%;
    background-color: inherit;
  }

  .main-content .movie-details .movie-cast h3 {
    text-align: center;
  }

  .main-content .movie-details .movie-cast table {
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-details .movie-cast table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
  }

  .main-content .movie-details .movie-cast th, td {
    padding: 15px;
  }

  .main-content .movie-details .movie-awards {
    float: right;
    width: 50%;
    background-color: inherit;
  }

  .clear {
    clear: both
  }

  .footer {
    background-color: #B75952;
    margin-top: 0px;
    padding-bottom: 30px;
  }

  .footer .movie-external-content {
    margin-top: 0px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 30px;
    padding-left: 30px;
  }
} */

```

* Agora vamos extrair o estilo do elemento `small`:

```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
}

.main-content .movie-title {
  width: 100%;
  text-align: center;
} */

.main-content .movie-description small {
  display: block;
  text-align: right;
}

/* @media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  }

  .top-bar h1 {
    margin: 0px;
    padding: 0.5em;
  }

  .movie-title {
    margin: 0px;
    padding: 0.5em 0;
  }

  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }

  .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }

  .footer {
    padding: 0px;
  }

  .footer .movie-external-content {
    padding: 0px;
    margin: 0px;
  }
}

@media screen and (min-width: 360px) {

  .top-bar {
    background-color: #506693;
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
  }

  .main-content {
    margin-top: 80px;
  }

  .main-content .movie-title {
    padding-top: 20px;
  }

  .main-content .media-content {
    width: 100%;
    margin-bottom: 50px;
  }

  .main-content .media-content img {
    height: 360px;
    width: auto;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-description {
    margin: 0px 30px 0 30px;
  }

  .main-content .movie-details {
    width: 100%;
    background-color: #669B65;
  }

  .main-content .movie-details .movie-cast {
    float: left;
    width: 50%;
    background-color: inherit;
  }

  .main-content .movie-details .movie-cast h3 {
    text-align: center;
  }

  .main-content .movie-details .movie-cast table {
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-details .movie-cast table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
  }

  .main-content .movie-details .movie-cast th, td {
    padding: 15px;
  }

  .main-content .movie-details .movie-awards {
    float: right;
    width: 50%;
    background-color: inherit;
  }

  .clear {
    clear: both
  }

  .footer {
    background-color: #B75952;
    margin-top: 0px;
    padding-bottom: 30px;
  }

  .footer .movie-external-content {
    margin-top: 0px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 30px;
    padding-left: 30px;
  }
} */
```

* Agora vamos extrair o estilo da tabela:

```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
}

.main-content .movie-title {
  width: 100%;
  text-align: center;
}

.main-content .movie-description small {
  display: block;
  text-align: right;
} */

.main-content .movie-details .movie-cast table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}

/* @media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  }

  .top-bar h1 {
    margin: 0px;
    padding: 0.5em;
  }

  .movie-title {
    margin: 0px;
    padding: 0.5em 0;
  }

  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }

  .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }

  .footer {
    padding: 0px;
  }

  .footer .movie-external-content {
    padding: 0px;
    margin: 0px;
  }
}

@media screen and (min-width: 360px) {

  .top-bar {
    background-color: #506693;
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
  }

  .main-content {
    margin-top: 80px;
  }

  .main-content .movie-title {
    padding-top: 20px;
  }

  .main-content .media-content {
    width: 100%;
    margin-bottom: 50px;
  }

  .main-content .media-content img {
    height: 360px;
    width: auto;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-description {
    margin: 0px 30px 0 30px;
  }

  .main-content .movie-details {
    width: 100%;
    background-color: #669B65;
  }

  .main-content .movie-details .movie-cast {
    float: left;
    width: 50%;
    background-color: inherit;
  }

  .main-content .movie-details .movie-cast h3 {
    text-align: center;
  }

  .main-content .movie-details .movie-cast table {
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-details .movie-cast th, td {
    padding: 15px;
  }

  .main-content .movie-details .movie-awards {
    float: right;
    width: 50%;
    background-color: inherit;
  }

  .clear {
    clear: both
  }

  .footer {
    background-color: #B75952;
    margin-top: 0px;
    padding-bottom: 30px;
  }

  .footer .movie-external-content {
    margin-top: 0px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 30px;
    padding-left: 30px;
  }
} */
```

* Agora vamos extrair o estilo do `footer`:

```css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
}

.main-content .movie-title {
  width: 100%;
  text-align: center;
}

.main-content .movie-description small {
  display: block;
  text-align: right;
}

.main-content .movie-details .movie-cast table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
} */

.footer {
  background-color: #B75952;
}

/* @media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  }

  .top-bar h1 {
    margin: 0px;
    padding: 0.5em;
  }

  .movie-title {
    margin: 0px;
    padding: 0.5em 0;
  }

  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }

  .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }

  .footer {
    padding: 0px;
  }

  .footer .movie-external-content {
    padding: 0px;
    margin: 0px;
  }
}

@media screen and (min-width: 360px) {

  .top-bar {
    background-color: #506693;
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
  }

  .main-content {
    margin-top: 80px;
  }

  .main-content .movie-title {
    padding-top: 20px;
  }

  .main-content .media-content {
    width: 100%;
    margin-bottom: 50px;
  }

  .main-content .media-content img {
    height: 360px;
    width: auto;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-description {
    margin: 0px 30px 0 30px;
  }

  .main-content .movie-details {
    width: 100%;
    background-color: #669B65;
  }

  .main-content .movie-details .movie-cast {
    float: left;
    width: 50%;
    background-color: inherit;
  }

  .main-content .movie-details .movie-cast h3 {
    text-align: center;
  }

  .main-content .movie-details .movie-cast table {
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-details .movie-cast th, td {
    padding: 15px;
  }

  .main-content .movie-details .movie-awards {
    float: right;
    width: 50%;
    background-color: inherit;
  }

  .clear {
    clear: both
  } */

  .footer {
    margin-top: 0px;
    padding-bottom: 30px;
  }
/*
  .footer .movie-external-content {
    margin-top: 0px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 30px;
    padding-left: 30px;
  }
} */
```

* Agora vamos ajustar o espaçamento dos elementos do `footer`:

``` css
/* body {
  font-family: "Times New Roman", Times, serif;
  margin: 0px;
}

.top-bar .title {
  font-style: italic;
  color: white;
  text-align: center;
}

.main-content {
  background-color: #A6BD66;
}

.main-content .movie-title {
  width: 100%;
  text-align: center;
}

.main-content .movie-description small {
  display: block;
  text-align: right;
}

.main-content .movie-details .movie-cast table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}

.footer {
  background-color: #B75952;
}

@media screen and (max-width: 360px) {
  .top-bar {
    background-color: #0fa36b;
    position: static;
  }

  .top-bar h1 {
    margin: 0px;
    padding: 0.5em;
  }

  .movie-title {
    margin: 0px;
    padding: 0.5em 0;
  }

  .media-content {
    display: none;
  }

  .main-content {
    line-height: 1.5em;
    font-family: sans-serif;
  }

  .main-content .movie-details .movie-cast, .main-content .movie-details .movie-awards {
    float: none;
    width: 100%;
  }

  .footer {
    padding: 0px;
  } */

  .footer .movie-external-content {
    padding: 0.3em;
    margin: 0px;
  }

  .movie-awards > ul:last-child {
    margin-bottom: 0px;
  }

  .movie-external-content h4 {
    margin: 0px;
  }

  .movie-external-content ol {
    margin: 0px;
  }

}
/*
@media screen and (min-width: 360px) {

  .top-bar {
    background-color: #506693;
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
  }

  .main-content {
    margin-top: 80px;
  }

  .main-content .movie-title {
    padding-top: 20px;
  }

  .main-content .media-content {
    width: 100%;
    margin-bottom: 50px;
  }

  .main-content .media-content img {
    height: 360px;
    width: auto;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-description {
    margin: 0px 30px 0 30px;
  }

  .main-content .movie-details {
    width: 100%;
    background-color: #669B65;
  }

  .main-content .movie-details .movie-cast {
    float: left;
    width: 50%;
    background-color: inherit;
  }

  .main-content .movie-details .movie-cast h3 {
    text-align: center;
  }

  .main-content .movie-details .movie-cast table {
    margin-left: auto;
    margin-right: auto;
  }

  .main-content .movie-details .movie-cast th, td {
    padding: 15px;
  }

  .main-content .movie-details .movie-awards {
    float: right;
    width: 50%;
    background-color: inherit;
  }

  .clear {
    clear: both
  }

  .footer {
    margin-top: 0px;
    padding-bottom: 30px;
  }

  .footer .movie-external-content {
    margin-top: 0px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 30px;
    padding-left: 30px;
  }
} */
```

* Faça um novo commit:

  * `git status`

  * `git add projects/html-css/styles.css`

  * `git status`

  * `git commit -m "ajustando o CSS para ser mobile first"`

  * `git status`

  * `git push origin live-lecture/7.2`

  * `git status`

* Agora mostre como o _CSS_ está organizado:

  1. Primeiro temos as regras de estilo gerais, que são aplicadas independentemente do tamanho da tela;

  2. Depois temos a _media query_ com o estilo específico de telas pequenas (até `360px`);

  3. E por fim a _media query_ com o estilo de telas grandes (maior que `360px`);

  * Comente a primeira _media query_ e mostre como fica a página no browser quando está com uma tela pequena;

  * Desfaça o comentário e agora comente a segunda _media query_. Mostre como fica a página em tela grande.

---

### Finalizando

* Volte no PR que você abriu, e mostre como ficaram as modificações. _(lembre-se de não mergeá-lo!)_

---

### Depois que acabar a aula:

* Feche o PR!
  * Vá até a [página do Pull Request](https://github.com/betrybe/betrybe.github.io/pulls), e feche-o clicando no botão **"Close pull request"**;

* Delete a branch que você criou localmente;
  * `git branch -d live-lecture/7.2`

* Delete a branch no repositório remoto:
  * `git push origin :live-lecture/7.2`
