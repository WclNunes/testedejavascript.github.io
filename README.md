<!DOCTYPE html>
<html>
<head>
  <title>Exemplo de Funções JavaScript</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }

    h1 {
      margin-bottom: 10px;
    }

    label {
      display: block;
      margin-top: 10px;
    }

    button {
      margin-top: 10px;
    }

    .result {
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>Exemplo de Funções JavaScript</h1>

  <h2>1. Encontrar o maior e o menor valor</h2>
  <label for="numbers">Digite cinco números separados por vírgula:</label>
  <input type="text" id="numbers">
  <button onclick="maiorMenor()">Encontrar</button>
  <div id="maiorMenorResult" class="result"></div>

  <h2>2. Verificar se um caractere é vogal</h2>
  <label for="character">Digite um caractere:</label>
  <input type="text" id="character">
  <button onclick="vogal()">Verificar</button>
  <div id="vogalResult" class="result"></div>

  <h2>3. Imprimir números pares em um intervalo e calcular o somatório</h2>
  <label for="lower">Limite inferior:</label>
  <input type="text" id="lower">
  <label for="upper">Limite superior:</label>
  <input type="text" id="upper">
  <button onclick="limites()">Calcular</button>
  <div id="limitesResult" class="result"></div>

  <h2>4. Ordenar três valores inteiros em ordem crescente</h2>
  <label for="value1">Valor 1:</label>
  <input type="text" id="value1">
  <label for="value2">Valor 2:</label>
  <input type="text" id="value2">
  <label for="value3">Valor 3:</label>
  <input type="text" id="value3">
  <button onclick="ordem()">Ordenar</button>
  <div id="ordemResult" class="result"></div>

  <h2>5. Verificar se um valor é positivo ou negativo</h2>
  <label for="number">Digite um número:</label>
  <input type="text" id="number">
  <button onclick="positivoNegativo()">Verificar</button>
  <div id="positivoNegativoResult" class="result"></div>

  <h2>6. Verificar se um valor é par ou ímpar</h2>
  <label for="integer">Digite um número inteiro:</label>
  <input type="text" id="integer">
  <button onclick="parImpar()">Verificar</button>
  <div id="parImparResult" class="result"></div>

  <script>
    function maiorMenor() {
      var numbersInput = document.getElementById("numbers");
      var numbers = numbersInput.value.split(",").map(Number);
      var maior = Math.max(...numbers);
      var menor = Math.min(...numbers);
      var resultDiv = document.getElementById("maiorMenorResult");
      resultDiv.innerHTML = "Maior valor: " + maior + "<br>Menor valor: " + menor;
    }

    function vogal() {
      var characterInput = document.getElementById("character");
      var character = characterInput.value.toLowerCase();
      var vogais = ['a', 'e', 'i', 'o', 'u'];
      var resultDiv = document.getElementById("vogalResult");
      if (vogais.includes(character)) {
        resultDiv.innerHTML = "O caractere é uma vogal.";
      } else {
        resultDiv.innerHTML = "O caractere não é uma vogal.";
      }
    }

    function limites() {
      var lowerInput = document.getElementById("lower");
      var upperInput = document.getElementById("upper");
      var lower = parseInt(lowerInput.value);
      var upper = parseInt(upperInput.value);
      var somatorio = 0;
      var resultDiv = document.getElementById("limitesResult");
      resultDiv.innerHTML = "";

      for (var i = lower + 1; i < upper; i++) {
        if (i % 2 === 0) {
          resultDiv.innerHTML += i + "<br>";
          somatorio += i;
        }
      }
      resultDiv.innerHTML += "Somatório dos números pares: " + somatorio;
    }

    function ordem() {
      var value1Input = document.getElementById("value1");
      var value2Input = document.getElementById("value2");
      var value3Input = document.getElementById("value3");
      var value1 = parseInt(value1Input.value);
      var value2 = parseInt(value2Input.value);
      var value3 = parseInt(value3Input.value);
      var resultDiv = document.getElementById("ordemResult");
      var valores = [value1, value2, value3];
      valores.sort(function(a, b) {
        return a - b;
      });
      resultDiv.innerHTML = "Valores ordenados em ordem crescente: " + valores.join(", ");
    }

    function positivoNegativo() {
      var numberInput = document.getElementById("number");
      var number = parseInt(numberInput.value);
      var resultDiv = document.getElementById("positivoNegativoResult");
      if (number >= 0) {
        resultDiv.innerHTML = "O número é positivo.";
      } else {
        resultDiv.innerHTML = "O número é negativo.";
      }
    }

    function parImpar() {
      var integerInput = document.getElementById("integer");
      var integer = parseInt(integerInput.value);
      var resultDiv = document.getElementById("parImparResult");
      if (integer % 2 === 0) {
        resultDiv.innerHTML = "O número é par.";
      } else {
        resultDiv.innerHTML = "O número é ímpar.";
      }
    }
  </script>
</body>
</html>
