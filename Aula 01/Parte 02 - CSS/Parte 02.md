# 📘 Parte 02: CSS

---

## 🔵 Introdução ao CSS 

### 🔍 O que é CSS?

CSS (Cascading Style Sheets — Folhas de Estilo em Cascata) é a linguagem usada para definir a aparência visual de páginas web.

Enquanto o **HTML** estrutura o conteúdo da página (o "o quê"), o **CSS** cuida da apresentação (o "como vai parecer").

---

### 🔍 Para que serve o CSS?

- Definir **cores** (de texto, fundo, bordas, etc.).  
- Controlar **fontes**, tamanhos de texto, espaçamento entre elementos.  
- Estilizar **bordas**, aplicar sombras e gradientes.  
- Controlar o **posicionamento e o tamanho** dos elementos na página.  
- Criar layouts **responsivos** (que se adaptam a diferentes tamanhos de tela).

---

### 🔹 Exemplo simples de CSS:

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Exemplo CSS</title>
  <style>
    p {
      color: blue;
      font-size: 18px;
    }
  </style>
</head>
<body>
  <p>Este parágrafo ficará azul com tamanho 18px.</p>
</body>
</html>
```

---

### 🔍 Por que "em cascata"?
A palavra "cascata" significa que as regras de CSS podem se sobrepor umas às outras, e as mais específicas ou as declaradas por último têm prioridade (você verá isso na parte de hierarquia de seletores).

---

## 🔵 Formas de Adicionar o CSS: Inline, Internal e External CSS

O CSS pode ser aplicado de três maneiras diferentes em uma página HTML:

---

### 1. CSS Inline (na própria tag)

- Estilo adicionado diretamente no elemento HTML usando o atributo `style`.  
- Deve ser evitado em projetos reais, pois dificulta manutenção e reaproveitamento de código.

**Exemplo:**
```html
<p style="color: red; font-size: 20px;">Este texto está vermelho.</p>
```

---


### 2. CSS Interno (Internal)
- Estilo declarado dentro da própria página HTML, na tag `<style>` no cabeçalho (`<head>`).
- Útil para páginas simples ou testes rápidos.

**Exemplo:**
```html
<head>
  <style>
    p {
      color: green;
      font-size: 18px;
    }
  </style>
</head>
```

---

### 3. CSS Externo (External)
- Estilo escrito em um arquivo .css separado, que é importado na página HTML.
- Forma recomendada para projetos reais, pois organiza o código e permite reaproveitamento de estilos em várias páginas.

**Exemplo:**
```html
<head>
  <link rel="stylesheet" href="estilo.css">
</head>
```

**Arquivo estilo.css:**
```css
p {
  color: blue;
  font-size: 16px;
}
```

---



### 🔹 Comparativo rápido
| Método     | Vantagens                       | Desvantagens                            |
|------------|---------------------------------|----------------------------------------|
| Inline     | Rápido para testes simples       | Difícil de manter e não reutilizável    |
| Interno    | Fácil para páginas pequenas      | Pouco reutilizável em projetos grandes  |
| Externo    | Organizado e reutilizável        | Requer arquivo separado                |

---

## 🔵 Seletores Básicos, Combinadores e Hierarquia

Os seletores determinam **quais elementos HTML** o CSS irá estilizar. Eles são a base para aplicar estilos corretamente.

---

### 🔹 Seletores básicos

| Seletor   | Descrição                          | Exemplo                |
|-----------|-----------------------------------|-----------------------|
| **Tag**   | Seleciona todas as tags do tipo    | `p {}` (todos os parágrafos) |
| **Classe**| Seleciona elementos com uma classe específica | `.destaque {}` |
| **ID**    | Seleciona um elemento com ID único | `#menu {}`           |
| **Universal**| Seleciona todos os elementos   | `* {}` (cuidado com o uso) |

**Exemplo:**
```css
p {
  color: blue;
}

.destaque {
  background-color: yellow;
}

#menu {
  font-weight: bold;
}
```

---

### 🔹 Combinadores (Relacionamento entre elementos)

| Combinador              | Descrição                                     | Exemplo                                      |
|------------------------|---------------------------------------------|---------------------------------------------|
| ``Espaço (descendente)`` | Seleciona todos os descendentes              | ``div p {}`` (todo ``<p>`` dentro de ``<div>``) |
| ``> (filho direto)``     | Seleciona apenas filhos diretos              | ``div > p {}``                               |
| ``+ (irmão adjacente)``  | Seleciona o elemento logo após               | ``h1 + p {}`` (primeiro ``<p>`` após um ``<h1>``) |
| ``~ (irmão geral)``      | Seleciona todos os irmãos posteriores        | ``h1 ~ p {}`` (todos os ``<p>`` após um ``<h1>``) |


---

### 🔹 Hierarquia e Especificidade
Quando há conflito de estilos, o navegador decide qual regra aplicar com base em **especificidade**:

**Ordem de prioridade (do mais fraco para o mais forte):**

1. Seletor Universal (`*`)

2. Seletor de Tag (`p`, `h1`, `div`, etc.)

3. Classe, atributo e pseudo-classes (`.classe`, `[type="text"]`, `:hover`)

4. ID (`#id`)

5. Inline (`style=""`) — Sempre vence as regras de CSS externas.

6. `!important` — Força a aplicação da regra (uso não recomendado, exceto em casos especiais).

**Exemplo de conflito de regras:**
```css
p {
  color: blue;
}

.texto {
  color: green;
}

#especial {
  color: red;
}
```

```html
<p id="especial" class="texto">Texto de exemplo</p>
```

**Resultado:** O texto será vermelho, porque o seletor de ID tem maior prioridade.

---

**📝 Resumo rápido:**
| Seletor      | Exemplo       | Prioridade |
|--------------|--------------|-----------|
| Universal    | `*`          | Baixa     |
| Tag         | `p`, `h1`    | Baixa     |
| Classe      | `.classe`    | Média     |
| ID          | `#id`        | Alta      |
| Inline      | `style=""`   | Muito alta|
| !important  | `color: red !important` | Máxima |

---

## 🔵 Propriedades

A seguir estão algumas das principais propriedades CSS usadas para estilizar textos, cores, bordas e fundos dos elementos:



### 🔹 Tabela de principais propriedades:

| Propriedade         | Descrição                              | Exemplo de uso                  |
|--------------------|---------------------------------------|---------------------------------|
| `color`            | Define a cor do texto                  | `color: red;`                  |
| `font-size`        | Define o tamanho da fonte              | `font-size: 16px;`             |
| `font-family`      | Define a família/tipo da fonte         | `font-family: Arial, sans-serif;` |
| `font-weight`      | Define o peso (espessura) da fonte     | `font-weight: bold;`           |
| `text-align`       | Alinha o texto                         | `text-align: center;`          |
| `text-decoration`  | Define decorações no texto (sublinhado, etc.) | `text-decoration: underline;` |
| `border-color`    | Cor da borda                           | `border: 2px solid blue;`      |
| `border-width`     | Largura da borda                       | `border-width: 3px;`           |
| `border-style`     | Estilo da borda (solid, dashed, etc.)  | `border-style: dashed;`        |
| `border-radius`    | Arredonda os cantos da borda           | `border-radius: 10px;`         |
| `background-color` | Define a cor de fundo                  | `background-color: lightgray;` |
| `background-image` | Define uma imagem de fundo             | `background-image: url('imagem.jpg');` |
| `background-size`  | Define o tamanho da imagem de fundo    | `background-size: cover;`      |
| `background-position` | Posiciona a imagem de fundo        | `background-position: center;` |

---

## 🔵 Box Model

O **Box Model** é um conceito fundamental do CSS que define como os elementos HTML são renderizados e ocupam espaço na página.

Cada elemento é considerado como uma "caixa" composta por 4 áreas:
- **Content**: conteúdo real do elemento (texto, imagem, etc.)
- **Padding**: espaço interno, entre o conteúdo e a borda
- **Border**: borda ao redor do padding e conteúdo
- **Margin**: espaço externo, fora da borda	

Veja a representação abaixo:

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTbZuc9-W2Aw4Ed1xTJl5r1-dVKG-uKsI2dwG8DReSO0c6g8TRTjbZvixWs&s=10)

<br>

**Importante:**
- O valor do tamanho total de um elemento normalmente é calculado assim:

```arduino
Largura Total = width + padding esquerdo + padding direito + border esquerdo + border direito + margin esquerdo + margin direito

```

- Para alterar esse comportamento, usamos:

```css
box-sizing: border-box;
```

Com isso, `padding` e `border` passam a ser incluídos dentro da largura definida (`width`).

---

## 🔵 Propriedades de Largura e Altura

As propriedades `width` e `height` definem a **largura e altura** dos elementos em CSS.


### 1. `width` (largura)

- Define a largura do elemento.

```css
width: 300px;
```

- Pode ser definida em:
  - **Pixels (px)**: valor fixo.
  - **Porcentagem (%)**: valor relativo ao elemento pai.
  - **Viewport (vw/vh)**: relativo ao tamanho da tela (1vw = 1% da largura da tela).

**Exemplos:**
```css
width: 500px;   /* Largura fixa */
width: 80%;     /* 80% da largura do elemento pai */
width: 50vw;    /* 50% da largura da janela (viewport) */
```

---

### 2. height (altura)
- Define a altura do elemento.

```css
height: 200px;
```

- Funciona com as mesmas unidades que width.

**Exemplos:**
```css
height: 300px;  /* Altura fixa */
height: 100vh;  /* 100% da altura da janela (viewport) */
```
---

### 3. max-width e min-width

- Define o tamanho máximo ou mínimo que um elemento pode ter, independentemente de seu conteúdo ou da tela:

```css
max-width: 100%;
min-width: 300px;
```

---

### 4. max-height e min-height

- Controla a altura máxima ou mínima de um elemento:

```css
max-height: 400px;
min-height: 100px;
```

---