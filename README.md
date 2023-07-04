# Calculo_IMC
calculadora de IMC
<!DOCTYPE html>
<html>
<head>
  <title>Calculadora de IMC</title>
  <style>
    .container {
      text-align: center;
      margin-top: 50px;
    }

    h1 {
      font-size: 24px;
    }

    #resultado {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Informe seu peso e altura</h1>
    <form id="imcForm">
      <label for="peso">Peso (kg):</label>
      <input type="number" id="peso" required><br>

      <label for="altura">Altura (m):</label>
      <input type="number" id="altura" step="0.01" required><br>

      <button type="submit">Calcular</button>
    </form>

    <div id="resultado"></div>
  </div>

  <script>
    document.getElementById("imcForm").addEventListener("submit", function(event) {
      event.preventDefault();
      
      var peso = parseFloat(document.getElementById("peso").value);
      var altura = parseFloat(document.getElementById("altura").value);

      var imc = peso / (altura * altura);

      var classificacao = "";
      if (imc < 16) {
        classificacao = "Magreza Grau III";
      } else if (imc < 16.9) {
        classificacao = "Magreza Grau II";
      } else if (imc < 18.5) {
        classificacao = "Magreza Grau I";
      } else if (imc < 25) {
        classificacao = "Eutrofia";
      } else if (imc < 30) {
        classificacao = "Sobrepeso";
      } else if (imc < 35) {
        classificacao = "Obesidade Grau I";
      } else if (imc < 40) {
        classificacao = "Obesidade Grau II";
      } else {
        classificacao = "Obesidade Grau III (Grave)";
      }

      document.getElementById("resultado").textContent = "Seu IMC é: " + imc.toFixed(1) + " kg/m². Classificação: " + classificacao;
    });
  </script>
</body>
</html>
