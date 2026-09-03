## Exemplo 1: Adicionando CSS

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Adicionando CSS</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Seja bem-vindo(a) ao meu site.</h1>
</body>
</html>
```

```css
h1 {
  font-family: sans-serif;
  color: darkblue;
}
```

## Exemplo  2: Seletores

```html
<!doctype html>
<html lang="pt-br">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Seletores</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <h1 id="titulo-web">Desenvolvimento Web</h1>

    <h2 class="titulo-secao-web">HTML</h2>
    <p class="paragrafo-web">
      Lorem ipsum dolor sit amet consectetur adipisicing elit.
    </p>

    <h3 class="sub-titulo-web">O que são tags ?</h3>
    <p class="paragrafo-web">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Assumenda neque
      libero suscipit consequatur soluta doloribus odio eligendi.
    </p>

    <h2 class="titulo-secao-web">CSS</h2>
    <p class="paragrafo-web">
      Lorem, ipsum dolor sit amet consectetur adipisicing elit.
    </p>

    <h3 class="sub-titulo-web">Tipos de CSS</h3>
    <p class="paragrafo-web">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quia, qui vero.
      Id rerum deleniti maiores facilis error possimus culpa quam eaque eligendi
      magnam? Doloremque voluptate a reprehenderit porro. Provident,
      consequuntur?
    </p>

    <hr />

    <h1 id="titulo-mobile">Desenvolvimento Mobile</h1>

    <h2 class="titulo-secao-mobile">Introdução ao Desenvolvimento Mobile</h2>
    <p class="paragrafo-mobile">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam
      repellat.
    </p>

    <h3 class="sub-titulo-mobile">O que é um aplicativo mobile ?</h3>
    <p class="paragrafo-mobile">
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Reiciendis,
      aspernatur necessitatibus. Ad, inventore. Quae, illo architecto. Excepturi
      voluptatibus ut quos soluta, nobis sint tenetur fuga, possimus dolorem
      illo, ex sed.
    </p>

    <h2 class="titulo-secao-mobile">Tecnologias para Mobile</h2>
    <p class="paragrafo-mobile">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum ex, iusto.
    </p>

    <h3 class="sub-titulo-mobile">Android, iOS e Híbridos</h3>
    <p class="paragrafo-mobile">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maiores ipsum,
      quia sunt placeat vitae veniam numquam corrupti repellendus reprehenderit
      magni architecto repudiandae vel ducimus corporis dolorem, cupiditate
      earum aut? Nemo?
    </p>
  </body>
</html>
```

```css
body {
  background-color: #ebebeb;
  font-family: sans-serif;
}

#titulo-web {
  text-align: center;
  color: #860000;
}

#titulo-mobile {
  text-align: center;
  color: #001374;
}

.titulo-secao-web {
  color: #b00000;
}

.sub-titulo-web {
  color: #b32020;
}

.titulo-secao-mobile {
  color: #001ca5;
}

.sub-titulo-mobile {
  color: #273ca7;
}

.paragrafo-mobile {
  color: #475192;
}

.paragrafo-web {
  color: #924747;
}

p {
  text-align: justify;
  line-height: 1.6;
}
```

## Exemplo 3: Modelo de Caixa

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Modelo de Caixa</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <p class="caixa-01">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Sapiente at libero alias accusamus iure veniam placeat repellendus, sint vero? Eaque laborum laboriosam temporibus recusandae ipsum pariatur, sapiente quod corporis sequi?
  </p>

  <p class="caixa-02">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Iusto, ea commodi. Minus necessitatibus autem accusamus iure nemo corrupti, soluta commodi debitis quam assumenda consequuntur, labore tempora reprehenderit et atque ratione.
  </p>
</body>
</html>
```

```css
.caixa-01 {
  background-color: rgb(41, 41, 215);
  color: white;
  font-family: sans-serif;
  line-height: 1.5;

  border-width: 2px;
  border-style: solid;
  border-color: darkblue;

  padding-top: 20px;
  padding-right: 40px;
  padding-bottom: 20px;
  padding-left: 40px;
}

.caixa-02 {
  background-color: rgb(208, 58, 58);
  color: white;
  font-family: sans-serif;
  line-height: 1.5;

  border: 2px solid darkred;

  padding: 20px 40px 20px 40px;
  margin-top: 100px;

  width: 400px;
  height: 300px;

  margin: 100px auto 0 auto;
}
```