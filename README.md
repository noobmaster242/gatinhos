<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gatinhos Fofos</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #fff0f5;
      text-align: center;
      padding: 20px;
    }
    .hidden {
      display: none;
    }
    img {
      max-width: 300px;
      border-radius: 10px;
      margin: 10px;
    }
  </style>
</head>
<body>
  <h1>Gatinhos Fofos</h1>

  <div id="formulario">
    <p>Você gosta de gatos?</p>
    <input type="radio" name="gosta" value="sim"> Sim
    <input type="radio" name="gosta" value="nao"> Não<br><br>

    <p>Você tem gatos?</p>
    <input type="radio" name="tem" value="sim"> Sim
    <input type="radio" name="tem" value="nao"> Não<br><br>

    <p>Digite seu nome:</p>
    <input type="text" id="nome"><br><br>

    <p>Selecione seu gênero:</p>
    <select id="genero">
      <option value="">Selecione</option>
      <option value="feminino">Feminino</option>
      <option value="masculino">Masculino</option>
      <option value="outro">Outro</option>
    </select><br><br>

    <button onclick="entrar()">Entrar</button>
  </div>

  <div id="gatinhos" class="hidden">
    <h2>Bem-vindo(a) ao mundo dos gatinhos fofos!</h2>
    <img id="fotoGato" src="https://i.pinimg.com/originals/10/f7/66/10f7664088c59f0d063e7df54c24403d.jpg" alt="Gatinho fofo e engraçado">
    <br>
    <button onclick="proximoGato()">Próximo</button>
  </div>

  <script>
    const imagens = [
      "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQHAHVlc8cS6C148zQHNgugSkHYJ5Goh_Fx6A&s",
      "https://wallpapers.com/images/hd/funny-dumb-pictures-ku7mvh5b7pmnh0em.jpg",
      "https://pt.quizur.com/_image?href=https://img.quizur.com/f/img655e5dfe5eb309.99908721.png?lastEdited=1700683268&w=1024&h=1024&f=webp",
      "https://http2.mlstatic.com/D_NQ_NP_926579-MLB72310197537_102023-O.webp",
      "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQOWobVYkjGy8pyEqz15pl0qgNvgR_IzSTgvQ&s"
    ];

    let indice = 0;

    function entrar() {
      const nome = document.getElementById("nome").value;
      const genero = document.getElementById("genero").value;

      if (!nome || !genero) {
        alert("Por favor, preencha seu nome e selecione o gênero.");
        return;
      }

      document.getElementById("formulario").classList.add("hidden");
      document.getElementById("gatinhos").classList.remove("hidden");
    }

    function proximoGato() {
      indice = (indice + 1) % imagens.length;
      document.getElementById("fotoGato").src = imagens[indice];
    }
  </script>
</body>
</html>
