## 1. Estrutura

### HTML

```html
<!DOCTYPE html>
<html lang="pt-br">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@100;300&display=swap" rel="stylesheet">
    <title>Document</title>
  </head>
  <body>
    <div>
      <input class="display">
      <button class="gray-button" onclick="limpaTela()">AC</button>
      <button class="gray-button" onclick="inverterNumero()">+/-</button>
      <button class="blue-button" onclick="adicionarCaracter('/')">/</button>
      <button class="blue-button" onclick="adicionarCaracter('*')">*</button>
      <button class="black-button" onclick="adicionarCaracter('7')">7</button>
      <button class="black-button" onclick="adicionarCaracter('8')">8</button>
      <button class="black-button" onclick="adicionarCaracter('9')">9</button>
      <button class="blue-button" onclick="adicionarCaracter('-')">-</button>
      <button class="black-button" onclick="adicionarCaracter('4')">4</button>
      <button class="black-button" onclick="adicionarCaracter('5')">5</button>
      <button class="black-button" onclick="adicionarCaracter('6')">6</button>
      <button class="blue-button" onclick="adicionarCaracter('+')">+</button>
      <button class="black-button" onclick="adicionarCaracter('1')">1</button>
      <button class="black-button" onclick="adicionarCaracter('2')">2</button>
      <button class="black-button" onclick="adicionarCaracter('3')">3</button>
      <button class="equal-button egual" onclick="calcular()">=</button>
      <button class="black-button zero" onclick="adicionarCaracter('0')">0</button>
      <button class="black-button" onclick="adicionarCaracter('.')">.</button>
    </div>
    <script src="script.js"></script>
  </body>
</html
```
### CSS

```css
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
  color: #fff;
}
body {
  background: #daf0ff;
  width: 100vw;
  height: 100vh;
  display: grid;
  justify-content: center;
  align-items: center;
}
div {
  background: linear-gradient(191.34deg, #17181a -4.95%, #17181a 103.74%);
  border-radius: 39px;
  width: 375px;
  height: 568px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(7, 1fr);
  padding: 20px;
}
button {
  font-size: 24px;
  border-radius: 16px;
  border: none;
  margin: 10px;
  cursor: pointer;
}

button:hover{
    opacity: 0.8;
}
button:active{
    opacity: 0.5;
}
input {
  font-size: 48px;
  grid-column: 1/5;
  grid-row: 1/3;
  background: #17181a;
  border: none;
  outline: none;
  text-align: right;
  padding-top: 50px;
}
.black-button {
  background: #303136;
}
.blue-button {
  background: #005db2;
}
.equal-button {
  background: #1991ff;
}
.gray-button {
  background: #616161;
}
.zero {
  grid-column: 1/3;
}
.egual {
  grid-row: 6/8;
  grid-column: 4/5;
}
```
### JAVASCRIPT

```js
function adicionarCaracter(caracter) {
  const valorDisplay = document.querySelector(".display").value;

  document.querySelector(".display").value = valorDisplay + caracter;
}

function limpaTela() {
  document.querySelector(".display").value = "";
}

function calcular() {
  const valorDisplay = document.querySelector(".display").value;

  document.querySelector(".display").value = eval(valorDisplay);
}

function inverterNumero() {
  const valorDisplay = document.querySelector(".display").value;

  document.querySelector(".display").value = valorDisplay * -1;
}

```
# Explicação detalhada do codigo

Este código implementa uma **calculadora funcional** com HTML, CSS e JavaScript. Vou explicar detalhadamente cada parte do código: HTML, CSS e JavaScript, incluindo os algoritmos.

---

### **HTML** - Estrutura da Página

A parte HTML define a interface da calculadora.

#### **1. `<!DOCTYPE html>`**

Declara que o documento é HTML5.

#### **2. `<html lang="pt-br">`**

Define o idioma do documento como português do Brasil.

#### **3. `<head>`**

Contém informações sobre o documento (metadados):

- `<meta charset="UTF-8">`: Define a codificação de caracteres como UTF-8 (suporta acentos e caracteres especiais).
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: Garante que a página seja responsiva em dispositivos móveis.
- `<link rel="stylesheet" href="styles.css">`: Conecta o arquivo CSS.
- Fontes (`Poppins`) são importadas de **Google Fonts**.

#### **4. `<body>`**

Aqui está o conteúdo principal da calculadora.

- **`<div>`**: Container que organiza os elementos dentro da calculadora.
- **`<input class="display">`**: Campo de entrada onde os números e operadores aparecem.
- **`<button>`**: Botões para os números, operadores e ações da calculadora. Cada botão possui:
    - `onclick`: Invoca funções JavaScript.
    - Classes (`gray-button`, `blue-button`, etc.): Para aplicar estilos específicos.

### **CSS** - Estilo da Página

Define a aparência e layout da calculadora.

#### **1. Regras Globais**

```css
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
  color: #fff;
}
```

- Remove margens e preenchimentos padrão.
- Define a fonte como "Poppins".
- Define a cor do texto como branco (`#fff`).

#### **2. Corpo da Página**

```css
body {
  background: #daf0ff;
  width: 100vw;
  height: 100vh;
  display: grid;
  justify-content: center;
  align-items: center;
}
```

- Define o fundo azul-claro (`#daf0ff`).
- Centraliza o conteúdo usando **CSS Grid**.

#### **3. Estilo da Calculadora**

```css
div {
  background: linear-gradient(191.34deg, #17181a -4.95%, #17181a 103.74%);
  border-radius: 39px;
  width: 375px;
  height: 568px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(7, 1fr);
  padding: 20px;
}
```

- Fundo com um gradiente escuro.
- Borda arredondada e tamanho fixo.
- Usa **CSS Grid** para organizar os botões em 4 colunas e 7 linhas.

#### **4. Botões**

- Botões têm diferentes cores para funções distintas:
    - Cinza (`.gray-button`): Ações especiais como "AC".
    - Azul (`.blue-button`): Operadores.
    - Preto (`.black-button`): Números.
    - Botão igual (`.equal-button`): Azul claro.

### **JavaScript** - Lógica da Calculadora

Esta é a parte mais importante. Aqui está a funcionalidade da calculadora.

#### **1. `adicionarCaracter(caracter)`**

Adiciona caracteres (números ou operadores) no campo de entrada:

```javascript
function adicionarCaracter(caracter) {
  const valorDisplay = document.querySelector(".display").value;
  document.querySelector(".display").value = valorDisplay + caracter;
}
```

- Pega o valor atual do `input` (campo de exibição).
- Adiciona o **caractere clicado** ao final do valor atual.

#### **2. `limpaTela()`**

Limpa o campo de entrada:

```javascript
function limpaTela() {
  document.querySelector(".display").value = "";
}
```

- Define o valor do campo de entrada como uma string vazia.

#### **3. `calcular()`**

Calcula a expressão no campo de entrada:

```javascript
function calcular() {
  const valorDisplay = document.querySelector(".display").value;
  document.querySelector(".display").value = eval(valorDisplay);
}
```

- `eval()`: Avalia a string como código JavaScript e retorna o resultado.
    - Exemplo: `"2+3*4"` → `eval` calcula como `14`.

#### **4. `inverterNumero()`**

Inverte o número no campo de entrada (de positivo para negativo e vice-versa):

```javascript
function inverterNumero() {
  const valorDisplay = document.querySelector(".display").value;
  document.querySelector(".display").value = valorDisplay * -1;
}
```

- Converte o valor atual em um número e multiplica por `-1`.

---

### Fluxo do Programa

1. **Página carrega**: O HTML renderiza a estrutura e o CSS aplica estilos.
2. **Botões clicados**: Cada botão chama uma função no JavaScript:
    - Números e operadores → `adicionarCaracter()`.
    - "AC" → `limpaTela()`.
    - "=" → `calcular()`.
    - "+/-" → `inverterNumero()`.
3. **Interação contínua**: Usuário interage com a calculadora, os valores são atualizados em tempo real no campo de exibição.

---

### Pontos de Destaque

- **`eval`**: Fácil de usar, mas pode ser perigoso se a entrada do usuário não for validada.
- **Flexibilidade**: O layout adapta-se bem a diferentes tamanhos de tela (graças ao `grid` e `viewport`).
- **Design Simples e Limpo**: As cores e estilos tornam a calculadora atraente e intuitiva.

