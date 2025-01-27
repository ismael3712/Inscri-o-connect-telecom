<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Checklist Connect Telecom</title>
</head>
<body>
    <h1>CHECKLIST CONNECT TELECOM</h1>
    <form action="#" method="POST">
        <label for="nome">Nome Completo:</label><br>
        <input type="text" id="nome" name="nome" required><br><br>
        <label for="cpf">CPF:</label><br>
        <input type="text" id="cpf" name="cpf" required><br><br>
        <label for="rg">RG:</label><br>
        <input type="text" id="rg" name="rg" required><br><br>
        <label for="data_nascimento">Data de Nascimento:</label><br>
        <input type="date" id="data_nascimento" name="data_nascimento" required><br><br>
        <label for="email">E-mail:</label><br>
        <input type="email" id="email" name="email" required><br><br>
        <label for="endereco">Endereço Completo:</label><br>
        <input type="text" id="endereco" name="endereco" required><br><br>
        <label for="cep">CEP:</label><br>
        <input type="text" id="cep" name="cep" required><br><br>
        <label for="referencia">Ponto de Referência:</label><br>
        <input type="text" id="referencia" name="referencia"><br><br>
        <label for="contato1">Contato Pessoal 1:</label><br>
        <input type="text" id="contato1" name="contato1" required><br><br>
        <label for="contato2">Contato Pessoal 2:</label><br>
        <input type="text" id="contato2" name="contato2"><br><br>
        <label for="recado">Contato para Recado:</label><br>
        <input type="text" id="recado" name="recado"><br><br>
        <label for="plano">Plano Contratado:</label><br>
        <select id="plano" name="plano" required>
            <option value="150">150 Mb - R$ 89,90</option>
            <option value="350">350 Mb - R$ 99,90</option>
            <option value="450">450 Mb - R$ 130,00</option>
            <option value="600">600 Mb - R$ 160,00</option>
            <option value="350_camera">350 Mb com câmera de segurança - R$ 140,00</option>
        </select><br><br>
        <label for="vencimento">Vencimento:</label><br>
        <input type="radio" id="venc05" name="vencimento" value="05"> <label for="venc05">05</label><br>
        <input type="radio" id="venc10" name="vencimento" value="10"> <label for="venc10">10</label><br>
        <input type="radio" id="venc15" name="vencimento" value="15"> <label for="venc15">15</label><br>
        <input type="radio" id="venc20" name="vencimento" value="20"> <label for="venc20">20</label><br>
        <input type="radio" id="venc30" name="vencimento" value="30"> <label for="venc30">30</label><br><br>
        <label for="localizacao">Localização:</label><br>
        <button type="button" onclick="getLocation()">Obter Localização</button><br><br>
        <input type="text" id="localizacao" name="localizacao" placeholder="Latitude, Longitude" readonly><br><br>
        <button type="submit">Enviar</button>
    </form>
    <script>
        function getLocation() {
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(showPosition, showError);
            } else {
                alert("Geolocalização não é suportada pelo navegador.");
            }
        }
        function showPosition(position) {
            document.getElementById("localizacao").value = 
                position.coords.latitude + ", " + position.coords.longitude;
        }
        function showError(error) {
            switch (error.code) {
                case error.PERMISSION_DENIED:
                    alert("Usuário negou a solicitação de Geolocalização.");
                    break;
                case error.POSITION_UNAVAILABLE:
                    alert("Informação de localização indisponível.");
                    break;
                case error.TIMEOUT:
                    alert("A solicitação expirou.");
                    break;
                case error.UNKNOWN_ERROR:
                    alert("Ocorreu um erro desconhecido.");
                    break;
            }
        }
    </script>
</body>
</html>
