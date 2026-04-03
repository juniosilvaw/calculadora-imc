<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Calculadora de IMC</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .container {
      background: white;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      width: 300px;
      text-align: center;
    }

    h1 {
      margin-bottom: 20px;
    }

    input {
      width: 90%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 5px;
      border: 1px solid #ccc;
    }

    button {
      padding: 10px 20px;
      background: #007BFF;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    button:hover {
      background: #0056b3;
    }

    .resultado {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>

<body>

<div class="container">
  <h1>Calculadora IMC</h1>

  <input type="number" id="peso" placeholder="Peso (kg)">
  <input type="number" id="altura" placeholder="Altura (m)">

  <button onclick="calcularIMC()">Calcular</button>

  <div class="resultado" id="resultado"></div>
</div>

<script>
function calcularIMC() {
  let peso = parseFloat(document.getElementById("peso").value);
  let altura = parseFloat(document.getElementById("altura").value);

  if (!peso || !altura) {
    document.getElementById("resultado").innerText = "Preencha todos os campos!";
    return;
  }

  let imc = peso / (altura * altura);
  let classificacao = "";

  if (imc < 17) {
    classificacao = "Muito abaixo do peso";
  } else if (imc < 18.5) {
    classificacao = "Abaixo do peso";
  } else if (imc < 25) {
    classificacao = "Peso ideal";
  } else if (imc < 30) {
    classificacao = "Sobrepeso";
  } else if (imc < 35) {
    classificacao = "Obesidade grau I";
  } else if (imc < 40) {
    classificacao = "Obesidade grau II (severa)";
  } else {
    classificacao = "Obesidade grau III (mórbida)";
  }

  document.getElementById("resultado").innerText =
    "IMC: " + imc.toFixed(2) + " - " + classificacao;
}
</script>

</body>
</html>
