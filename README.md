# Projeto
<!DOCTYPE html>
<html lang="pt">

<head >
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Cadastro de Empresa</title>
    
</head>
<body>
    <h1>Cadastro de Empresa</h1>
    <form action="/submit" method="post">
        <label for="companyName">Nome da Empresa:</label>
        <input type="text" id="companyName" name="companyName" required>

        <label for="cnpj">CNPJ:</label>
        <input type="text" id="cnpj" name="cnpj" required oninput="mascaraCNPJ(this)">
        <script>
            function mascaraCNPJ(input) {
            let value = input.value.replace(/\D/g, '');
            value = value.replace(/^(\d{2})(\d)/, '$1.$2');
            value = value.replace(/^(\d{2})\.(\d{3})(\d)/, '$1.$2.$3');
            value = value.replace(/\.(\d{3})(\d)/, '.$1/$2');
            value = value.replace(/(\d{4})(\d)/, '$1-$2');
            input.value = value;
            }
        </script>

        <label for="address">Endereço:</label>
        <input type="text" id="address" name="address" required>

        <label for="phone">Telefone:</label>
        <input type="tel" id="phone" name="phone" required>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>

        <label for="industry">Setor:</label>
        <select id="industry" name="industry" required>
            <option value="technology">Tecnologia</option>
            <option value="finance">Finanças</option>
            <option value="healthcare">Saúde</option>
            <option value="education">Educação</option>
            <option value="other">Outro</option>
        </select>

        <button type="submit">Cadastrar</button>
    </form>
</body>
</html>
