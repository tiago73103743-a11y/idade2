# <!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Verificar Faixa Etária</title>
</head>
<body>
    <h2>Verifique sua Faixa Etária</h2>
    <label for="anoNascimento">Digite seu ano de nascimento:</label>
    <input type="number" id="anoNascimento" placeholder="Ex: 1990">
    <button onclick="verificarIdade()">Verificar</button>

    <p id="resultado"></p>

    <script>
        function verificarIdade() {
            const anoNascimento = parseInt(document.getElementById('anoNascimento').value);
            const anoAtual = new Date().getFullYear();
            const resultado = document.getElementById('resultado');

            if (isNaN(anoNascimento)) {
                resultado.textContent = "Por favor, digite um ano válido.";
                return;
            }

            const idade = anoAtual - anoNascimento;

            if (idade < 0) {
                resultado.textContent = "Ano de nascimento inválido. Você ainda não nasceu!";
            } else if (idade <= 12) {
                resultado.textContent = `Você tem ${idade} anos. Faixa etária: Criança.`;
            } else if (idade <= 17) {
                resultado.textContent = `Você tem ${idade} anos. Faixa etária: Jovem.`;
            } else if (idade <= 59) {
                resultado.textContent = `Você tem ${idade} anos. Faixa etária: Adulto.`;
            } else {
                resultado.textContent = `Você tem ${idade} anos. Faixa etária: Idoso.`;
            }
        }
    </script>
</body>
</html>
