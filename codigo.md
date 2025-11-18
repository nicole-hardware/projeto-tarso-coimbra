## Código HTML


```
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Desafios Educativos</title>
  <style>
    
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap');

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: linear-gradient(135deg, #076d9c 0%, #a78bfa 100%);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 40px 20px;
    }

    .container {
      text-align: center;
      backdrop-filter: blur(16px);
      background: rgba(255, 255, 255, 0.15);
      border: 1px solid rgba(255, 255, 255, 0.3);
      border-radius: 30px;
      padding: 50px 30px;
      box-shadow: 0 8px 40px rgba(0, 0, 0, 0.1);
      max-width: 1000px;
      width: 100%;
      min-height: 80vh;
      position: relative;
    }

    h1 {
      color: #000000;
      font-size: 2.4rem;
      margin-bottom: 50px;
      letter-spacing: 0.5px;
    }

    .menu {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 40px;
    }

    .card {
      background: rgba(255, 255, 255, 0.25);
      border: 1px solid rgba(255, 255, 255, 0.35);
      border-radius: 20px;
      width: 260px;
      padding: 30px 25px;
      transition: all 0.3s ease;
      cursor: pointer;
      backdrop-filter: blur(10px);
      color: #df9494; 
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }

    .card:hover {
      transform: translateY(-8px) scale(1.04);
      background: rgba(255, 255, 255, 0.4);
    }

    .card img {
      width: 160px;
      height: 100px;
      margin-bottom: 20px;
      filter: drop-shadow(0 3px 6px rgba(0,0,0,0.2));
      object-fit: contain; 
    }

    .card h2 {
      font-size: 1.4rem;
      margin-bottom: 10px;
      color: #000000;
    }

    .card p {
      font-size: 0.95rem;
      color: #333; 
    }

    
    .menu-image-container {
        width: 100%;
        display: flex;
        justify-content: center;
        margin-bottom: 30px; 
        border-radius: 20px; 
        overflow: hidden; 
        box-shadow: 0 8px 30px rgba(0, 0, 0, 0.1);
    }

    .menu-image {
        width: 100%; 
        height: auto;
        max-height: 250px; 
        object-fit: cover; 
    }


    @media (max-width: 700px) {
      .menu {
        flex-direction: column;
        align-items: center;
      }
      .container {
        padding: 40px 15px;
      }
      h1 {
        font-size: 2rem;
      }
      .menu-image {
          max-height: 180px; /* Ajusta a altura do banner para telas menores */
      }
    }


    
    
    /* Sistema de Telas */
    .tela {
      display: none;
      width: 100%;
      animation: fadeIn 0.5s ease;
    }

    .tela.ativa {
      display: block;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* Botão Voltar */
    .btn-voltar {
      position: absolute;
      top: 30px;
      left: 30px;
      background: rgba(255, 255, 255, 0.3);
      border: 1px solid rgba(255, 255, 255, 0.4);
      color: #000;
      font-size: 1.5rem;
      width: 45px;
      height: 45px;
      border-radius: 50%;
      cursor: pointer;
      display: flex;
      justify-content: center;
      align-items: center;
      transition: all 0.3s ease;
      z-index: 10; /* Para garantir que fique acima de outros elementos */
    }
    .btn-voltar:hover {
      background: rgba(255, 255, 255, 0.6);
      transform: scale(1.1);
    }

 
    .header-jogo {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 20px; /* Ajuste de margem */
      flex-wrap: wrap; /* Para telas menores */
      gap: 20px;
      padding-top: 15px; /* Espaço para o botão voltar não sobrepor */
    }
    .header-jogo > div:first-child {
      text-align: left; 
    }
    #pontuacao-container {
      background: rgba(255, 255, 255, 0.25);
      border: 1px solid rgba(255, 255, 255, 0.35);
      border-radius: 15px;
      padding: 15px 25px;
      font-size: 1.2rem;
      font-weight: 600;
      color: #000;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      flex-shrink: 0; 
    }
    #pontuacao-valor {
      font-size: 1.3rem;
      color: #000; 
      font-weight: bold;
    }
    

    /* Tela do Jogo */
    #titulo-jogo {
      font-size: 2rem;
      color: #000;
      margin-bottom: 5px; /* Ajuste de margem */
      text-align: left; /* Alinhado à esquerda */
    }
    #descricao-jogo {
      font-size: 1rem;
      color: #333;
      margin-bottom: 0; /* Ajuste de margem */
      text-align: left; /* Alinhado à esquerda */
    }

    .jogo-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 40px;
      margin-bottom: 30px;
    }

    /* Grade da Cruzadinha */
    #grade {
      display: grid;
      border: 3px solid rgba(0, 0, 0, 0.1);
      border-radius: 10px;
      overflow: hidden;
      background: rgba(255, 255, 255, 0.2);
    }

    #grade input {
      width: 48px;
      height: 48px;
      text-align: center;
      font-size: 1.5rem;
      font-weight: 600;
      text-transform: uppercase;
      border: 1px solid rgba(0, 0, 0, 0.1);
      background: #fff;
      color: #333;
      padding: 0;
    }

    #grade input:focus {
      outline: 2px solid #a78bfa;
    }

    #grade input.filled {
      background: #aaa;
      border-color: #888;
    }

    #grade input.correct {
      background: #d4edda;
      color: #155724;
    }

    #grade input.incorrect {
      background: #f8d7da;
      color: #721c24;
    }

    
    #dicas {
      text-align: left;
      background: rgba(255, 255, 255, 0.2);
      padding: 20px;
      border-radius: 15px;
      max-width: 400px;
    }
    #dicas h3 {
      color: #000;
      margin-bottom: 15px;
      border-bottom: 2px solid rgba(0,0,0,0.1);
      padding-bottom: 10px;
    }
    #lista-dicas {
      list-style-position: inside;
      color: #333;
    }
    #lista-dicas li {
      margin-bottom: 10px;
      line-height: 1.4;
    }

    
    .btn-container {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
    }

    .btn-jogo {
      background: linear-gradient(135deg, #a78bfa 0%, #7dd3fc 100%);
      color: #fff;
      border: none;
      padding: 15px 30px;
      border-radius: 15px;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    }
    .btn-jogo:hover {
      transform: translateY(-3px);
      box-shadow: 0 6px 20px rgba(0,0,0,0.15);
    }

    
    .modal-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      display: none; 
      justify-content: center;
      align-items: center;
      z-index: 1000;
      backdrop-filter: blur(5px);
    }
    .modal-content {
      background: #fff;
      padding: 40px;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 8px 40px rgba(0, 0, 0, 0.1);
      max-width: 400px;
      width: 90%;
    }
    .modal-content h2 {
      color: #000;
      margin-bottom: 20px;
    }
    .modal-content p {
      color: #333;
      margin-bottom: 30px;
      font-size: 1.1rem;
    }
    .modal-content button {
      background: #a78bfa;
      color: #fff;
      border: none;
      padding: 12px 25px;
      border-radius: 10px;
      font-size: 1rem;
      cursor: pointer;
      transition: background 0.3s;
    }
    .modal-content button:hover {
      background: #8b5cf6;
    }

  </style>
</head>
<body>

  
  <div id="modal-aviso" class="modal-overlay">
    <div class="modal-content">
      <h2 id="modal-titulo">Aviso</h2>
      <p id="modal-mensagem"></p>
      <button onclick="closeModal()">OK</button>
    </div>
  </div>

  <main class="container">

   
    <div id="menu-principal" class="tela ativa">
      
     
      <div class="menu-image-container">
            <img src="https://i.ibb.co/1GqsD1vH/image-removebg-preview-1.png" alt="Banner de Estudo" class="menu-image">
      </div>

      <h1>Escolha um desafio</h1> 

      <div class="menu">
        <!-- Português -->
        <div class="card" onclick="selectSubject('portugues')">
          <img src="https://i.ibb.co/fGVVdfr7/image-removebg-preview-2.png" alt="Português">
          <h2>Português</h2>
          <p>Desafios de palavras e animais.</p>
        </div>
        <!-- Matemática -->
        <div class="card" onclick="selectSubject('matematica')">
          <img src="https://i.ibb.co/wF6fx3k3/image-removebg-preview-3.png" alt="Matemática">
          <h2>Matemática</h2>
          <p>Complete os nomes dos números.</p>
        </div>

       

      </div>
    </div>

  
    <div id="menu-nivel" class="tela">
      <button class="btn-voltar" onclick="goBackToMain()">↩</button>
      <h1 id="titulo-materia">...</h1>
      <div class="menu">
        <div class="card" onclick="startLevel('facil')">
          <img src="https://placehold.co/90x90/86efac/000000?text=①" alt="Fácil">
          <h2>Fácil</h2>
          <p>Para começar a aquecer!</p>
        </div>
        <div class="card" onclick="startLevel('medio')">
          <img src="https://placehold.co/90x90/fde047/000000?text=②" alt="Médio">
          <h2>Médio</h2>
          <p>Um pouco mais desafiador.</p>
        </div>
        <div class="card" onclick="startLevel('dificil')">
          <img src="https://placehold.co/90x90/f87171/000000?text=③" alt="Difícil">
          <h2>Difícil</h2>
          <p>Para os mestres!</p>
        </div>
      </div>
    </div>

   
    <div id="jogo" class="tela">
      <button class="btn-voltar" onclick="goBackToLevel()">↩</button>
      
      <!-- Cabeçalho do Jogo com Título e Pontuação -->
      <div class="header-jogo">
        <div>
            <h2 id="titulo-jogo">...</h2>
            <p id="descricao-jogo">...</p>
        </div>
        <div id="pontuacao-container">
            Pontos: <span id="pontuacao-valor">0</span>
        </div>
      </div>


      <div class="jogo-container">
        <div id="grade"></div>
        <div id="dicas">
          <h3>Dicas</h3>
          <ul id="lista-dicas"></ul>
        </div>
      </div>

      <div class="btn-container">
        <button class="btn-jogo" onclick="checkAnswers()">Verificar</button>
        <button class="btn-jogo" onclick="resetGame()">Limpar</button>
        <button class="btn-jogo" onclick="nextCrossword()">Próxima</button>
      </div>
    </div>

  </main>

  <script>
    
    const mockData = {
      "matematica": {
        "facil": [
          {
            "titulo": "Cruzadinha 1 – Adição e Subtração",
            "descricao": "Resolva as somas e subtrações e escreva os resultados por extenso.",
            "tamanho": 10,
            "grade": [
              ["#", "D", "#", "#", "#", "#" , "#", "#", "#", "#"],
              ["D", "O", "Z", "E", "#", "#",  "#", "#", "#", "#"],
              ["#", "I", "#", "#", "#", "#" , "#", "#", "#", "#"],
              ["#", "S", "E", "T", "E", "N" , "T", "A", "#", "#"],
              ["#", "#", "#", "R", "#", "#" , "#", "#", "#", "#"],
              ["N", "O", "V", "E", "#", "C" , "#", "#", "#", "#"],
              ["#", "#", "#", "S", "E", "I" , "S", "#", "#", "#"],
              ["#", "#", "#", "#", "#", "N" , "#", "#", "#", "#"],
              ["#", "#", "#", "#", "#", "C" , "E", "M", "#", "#"],
              ["#", "#", "O", "I", "T", "O" , "#", "#", "#", "#"]
            ],
            "dicas": ["1️⃣ 5 - 3 ", "2️⃣ 4 + 8 ", "3️⃣ 80 - 10 ","4️⃣ 8 - 5 ","5️⃣ 6 + 3", "6️⃣ 3 + 3", "7️⃣ 9 - 4","8️⃣ 115 - 15", "9️⃣ 10 - 2" ]
          },
          {
            "titulo": "Cruzadinha 2 – Adição e Subtração",
            "descricao": "Resolva as somas e subtrações e escreva os resultados por extenso.",
            "tamanho": 14,
            "grade": [
              ["#", "#", "#", "#", "#", "C" , "#", "#", "T", "#", "#", "#", "#", "#"],
              ["D", "E", "Z", "#", "#", "I" , "#", "#", "R", "#", "#", "#", "#", "#"],
              ["O", "#", "E", "#", "#", "N",  "O", "V", "E", "#", "#", "#", "#", "#"],
              ["I", "#", "R", "#", "#", "C" , "#", "#", "Z", "#", "#", "V", "#", "D"],
              ["S", "#", "O", "I", "T", "O" , "#", "D", "E", "Z", "O", "I", "T", "O"],
              ["#", "#", "#", "#", "R", "#" , "#", "#", "#", "#", "#", "N", "#", "Z"],
              ["#", "#", "#", "#", "E", "#" , "#", "#", "#", "#", "#", "T", "#", "E"],
              ["#", "#", "#", "#", "S", "E" , "I", "S", "#", "#", "#", "E", "#", "#"],
              ["#", "#", "#", "#", "#", "#" , "#", "E", "#", "#", "#", "#", "#", "#"],
              ["#", "#", "#", "#", "Q", "U" , "A", "T", "R", "O", "#", "#", "#", "#"],
              ["#", "#", "#", "#", "#", "M" , "#", "E", "#", "N", "#", "#", "#", "#"],
              ["#", "#", "#", "#", "#", "#" , "#", "#", "#", "Z", "#", "#", "#", "#"],
              ["#", "#", "#", "C", "A", "T" , "O", "R", "Z", "E", "#", "#", "#", "#"],
              ["#", "#", "#", "#", "#", "#" , "#", "#", "#", "#", "#", "#", "#", "#"]
               
            ],
            "dicas": ["1️⃣ 30 - 20 ", "2️⃣ 4 - 2 ", "3️⃣ 10 - 10 ","4️⃣ 10 - 2 ","5️⃣ 1 + 2", "6️⃣ 3 + 3", "7️⃣ 9 - 2","8️⃣ 10 - 6", "9️⃣ 1 - 0", "1️⃣0️⃣ 20 - 9","1️⃣1️⃣ 7 + 7","1️⃣2️⃣ 3 + 2","1️⃣3️⃣ 40 - 31","1️⃣4️⃣ 6 + 7","1️⃣5️⃣ 9 + 9","1️⃣6️⃣ 40 - 20","1️⃣7️⃣ 8 + 4"]
          }
        ],
        "medio": [
        {
            "titulo": "Cruzadinha 1 – Multiplicação e divisão",
            "descricao": "Resolva as multiplicações e divisões e escreva os resultados por extenso.",
            "tamanho": 12,
            "grade": [
              ["#", "#", "#", "#", "V", "#" , "#", "#", "#", "#", "#", "#"],
              ["#", "#", "#", "O", "I", "T",  "O", "#", "Q", "#", "#", "#"],
              ["#", "#", "#", "#", "N", "#" , "#", "#", "U", "M", "#", "#"],
              ["#", "#", "O", "I", "T", "E" , "N", "T", "A", "#", "#", "#"],
              ["#", "#", "N", "#", "E", "#" , "O", "#", "T", "R", "E", "S"],
              ["#", "#", "Z", "#", "#", "#" , "V", "#", "R", "#", "#", "E"],
              ["#", "C", "E", "M", "#", "Z" , "E", "R", "O", "#", "#", "T"],
              ["#", "I", "#", "#", "S", "#" , "#", "#", "#", "#", "#", "E"],
              ["#", "N", "O", "V", "E", "N" , "T", "A", "#", "#", "#", "#"],
              ["#", "C", "#", "#", "I", "#" , "#", "#", "#", "#", "#", "#"],
              ["#", "O", "#", "#", "S", "#" , "#", "#", "#", "#", "#", "#"],
              ["#", "#", "#", "#", "#", "#" , "#", "#", "#", "#", "#", "#"]
            ],

            "dicas": ["1️⃣ 24 ÷ 3 ", "2️⃣ 40 ÷ 2 ", "3️⃣ 160 ÷ 2","4️⃣ 4 × 1 ","5️⃣ 3 × 1", "6️⃣ 49 ÷ 7", "7️⃣ 22 ÷ 2","8️⃣ 10 × 10", "9️⃣ 50 ÷ 10", "1️⃣0️⃣ 9 × 10", "1️⃣1️⃣ 2 × 3", "1️⃣2️⃣ 526 × 0", "1️⃣3️⃣ 3 × 3", "1️⃣4️⃣ 350 ÷ 350" ]
        },
        {
            "titulo": "Cruzadinha 2 – Multiplicação e divisão",
            "descricao": "Resolva as multiplicações e divisões e escreva os resultados por extenso.",
            "tamanho": 12,
            "grade": [
              ["#", "#", "#", "#", "#", "#" , "#", "#", "#", "#", "#", "#"],
              ["#", "#", "#", "D", "#", "#",  "#", "#", "#", "#", "#", "#"],
              ["#", "#", "S", "E", "I", "S" , "#", "#", "#", "#", "S", "#"],
              ["#", "D", "#", "Z", "#", "#" , "#", "#", "C", "#", "E", "#"],
              ["N", "O", "V", "E", "#", "#" , "T", "R", "I", "N", "T", "A"],
              ["#", "I", "#", "S", "#", "#" , "R", "#", "N", "#", "E", "#"],
              ["#", "S", "#", "S", "E", "T" , "E", "#", "C", "#", "N", "#"],
              ["#", "#", "#", "E", "#", "#" , "S", "#", "O", "#", "T", "#"],
              ["#", "#", "O", "I", "T", "O" , "#", "#", "#", "#", "A", "#"],
              ["#", "#", "#", "S", "#", "N" , "#", "#", "#", "#", "#", "#"],
              ["#", "#", "#", "#", "#", "Z" , "#", "#", "#", "#", "#", "#"],
              ["#", "#", "#", "#", "D", "E" , "Z", "O", "I", "T", "O", "#"]      
            ],

            "dicas": ["1️⃣ 2 × 8 ", "2️⃣ 12 ÷ 2 ", "3️⃣ 2 × 1","4️⃣ 27 ÷ 3 ","5️⃣ 49 ÷ 7", "6️⃣ 4 × 2", "7️⃣ 22 ÷ 2","8️⃣ 54 ÷ 3", "9️⃣ 3 × 1", "1️⃣0️⃣ 60 ÷ 2", "1️⃣1️⃣ 50 ÷ 10", "1️⃣2️⃣ 7 × 10" ]
        }

        ], 
        "dificil": [
        {
            "titulo": "Cruzadinha 1 – Multiplicação, Divisão, Soma e Subtração",
            "descricao": "Resolva as equações e escreva os resultados por extenso.",
            "tamanho": 12,
            "grade": [
              ["#", "#", "#", "#", "#", "#" , "#", "#", "#", "#", "#", "#"],
              ["#", "#", "#", "D", "#", "#",  "#", "#", "#", "#", "#", "#"],
              ["#", "#", "S", "E", "I", "S" , "#", "#", "#", "#", "S", "#"],
              ["#", "D", "#", "Z", "#", "#" , "#", "#", "C", "#", "E", "#"],
              ["N", "O", "V", "E", "#", "#" , "T", "R", "I", "N", "T", "A"],
              ["#", "I", "#", "S", "#", "#" , "R", "#", "N", "#", "E", "#"],
              ["#", "S", "#", "S", "E", "T" , "E", "#", "C", "#", "N", "#"],
              ["#", "#", "#", "E", "#", "#" , "S", "#", "O", "#", "T", "#"],
              ["#", "#", "O", "I", "T", "O" , "#", "#", "#", "#", "A", "#"],
              ["#", "#", "#", "S", "#", "N" , "#", "#", "#", "#", "#", "#"],
              ["#", "#", "#", "#", "#", "Z" , "#", "#", "#", "#", "#", "#"],
              ["#", "#", "#", "#", "D", "E" , "Z", "O", "I", "T", "O", "#"]      
            ],

            "dicas": ["1️⃣ 1 × 8 × 2 ", "2️⃣ (6 × 2) ÷ 2 ", "3️⃣ 2 × 1","4️⃣ (9 × 9) ÷ 9 ","5️⃣ 49 ÷ 7", "6️⃣ (17 - 1) ÷ 2", "7️⃣ 22 ÷ 2","8️⃣ (2 × 6) + 6", "9️⃣ 4 - 1", "1️⃣0️⃣ (120 ÷ 3) - 10", "1️⃣1️⃣ 31 + 19", "1️⃣2️⃣ 7 × 10" ]
        },
                {
            "titulo": "Cruzadinha 2 – Multiplicação, Divisão, Soma e Subtração",
            "descricao": "Resolva as equações e escreva os resultados por extenso.",
            "tamanho": 12,
            "grade": [
              ["#", "#", "#", "#", "V", "#" , "#", "#", "#", "#", "#", "#"],
              ["#", "#", "#", "O", "I", "T",  "O", "#", "Q", "#", "#", "#"],
              ["#", "#", "#", "#", "N", "#" , "#", "#", "U", "M", "#", "#"],
              ["#", "#", "O", "I", "T", "E" , "N", "T", "A", "#", "#", "#"],
              ["#", "#", "N", "#", "E", "#" , "O", "#", "T", "R", "E", "S"],
              ["#", "#", "Z", "#", "#", "#" , "V", "#", "R", "#", "#", "E"],
              ["#", "C", "E", "M", "#", "Z" , "E", "R", "O", "#", "#", "T"],
              ["#", "I", "#", "#", "S", "#" , "#", "#", "#", "#", "#", "E"],
              ["#", "N", "O", "V", "E", "N" , "T", "A", "#", "#", "#", "#"],
              ["#", "C", "#", "#", "I", "#" , "#", "#", "#", "#", "#", "#"],
              ["#", "O", "#", "#", "S", "#" , "#", "#", "#", "#", "#", "#"],
              ["#", "#", "#", "#", "#", "#" , "#", "#", "#", "#", "#", "#"]
            ],

            "dicas": ["1️⃣ (2 × 5) - 2 ", "2️⃣ (5 × 5) - 5", "3️⃣ (10 × 10) - 20","4️⃣ (6 ÷ 2) + 1 ","5️⃣ 1 + (4 ÷ 2)", "6️⃣ (3 × 3) - 2", "7️⃣ (3 × 3) + 2","8️⃣ 10 × 10", "9️⃣ (2 × 2) + 1", "1️⃣0️⃣ 100 - (2 × 5)", "1️⃣1️⃣ (2 × 4) - 2", "1️⃣2️⃣ 10 - (2 × 5)", "1️⃣3️⃣ (4 × 2) + 1", "1️⃣4️⃣ 10 - (3 × 3)" ]
        }
        ]
      },
      "portugues": {
        "facil": [
          {
            "titulo": "Cruzadinha 1 ",
            "descricao": "Que palavra é essa?",
            "tamanho": 9,
            "grade": [
              ["#", "#", "#", "M", "#", "#", "S", "#", "#"],
              ["#", "#", "V", "E", "R", "B", "O", "#", "#"],
              ["#", "#", "#", "N", "#", "#", "M", "#", "#"],
              ["#", "P", "#", "O", "#", "R", "A", "I", "Z"],
              ["M", "A", "I", "S", "#", "A", "#", "#", "E"],
              ["#", "R", "#", "#", "#", "T", "#", "#", "B"],
              ["#", "#", "#", "#", "#", "O", "#", "#", "R"],
              ["#", "#", "#", "#", "#", "#", "#", "#", "A"],
              ["#", "#", "#", "#", "#", "#", "#", "#", "#"]

            ],
            "dicas":["1️⃣ Palavra de ação (ex: pular, comer). ", "2️⃣ A parte da árvore que fica embaixo da terra. ", "3️⃣ Nome do sinal de adicionar (+). ", "4️⃣ Número 2 é...", "5️⃣Nome do sinal de tirar (-).","6️⃣ A conta de juntar coisas." , "7️⃣Animal que foge do gato.", "8️⃣Animal todo listrado." ]
          },
          {
            "titulo": "Cruzadinha 2 ",
            "descricao": "Que palavra é essa?",
            "tamanho": 9,
            "grade": [
              ["#", "#", "#", "B", "A", "R", "C", "O", "#"],
              ["#", "#", "#", "I", "#", "#", "#", "#", "#"],
              ["#", "#", "#", "C", "A", "R", "R", "O", "#"],
              ["#", "#", "#", "I", "#", "#", "#", "N", "#"],
              ["#", "#", "#", "C", "#", "#", "#", "I", "#"],
              ["#", "#", "#", "L", "#", "#", "#", "B", "#"],
              ["#", "T", "R", "E", "M", "#", "#", "U", "#"],
              ["#", "#", "#", "T", "#", "#", "#", "S", "#"],
              ["A", "V", "I", "A", "O", "#", "#", "#", "#"]

            ],
            "dicas":["1️⃣ 🚲", "2️⃣ ✈️", "3️⃣ 🚆", "4️⃣ 🛥️", "5️⃣ 🚗","6️⃣ 🚌" ]
          }

        ],
        "medio": [],
        "dificil": []
      }
    };


    
    let materia = "";
    let nivel = "";
    let cruzadinhas = [];
    let indiceAtual = 0;
    let pontuacao = 0; // Variável de pontuação
    
    // Funções do Modal
    const modal = document.getElementById("modal-aviso");
    const modalTitulo = document.getElementById("modal-titulo");
    const modalMensagem = document.getElementById("modal-mensagem");
    
    function showModal(titulo, mensagem) {
      modalTitulo.textContent = titulo;
      modalMensagem.textContent = mensagem;
      modal.style.display = "flex";
    }
    
    function closeModal() {
      modal.style.display = "none";
    }

    
    function atualizarPontuacao(pontos) {
        pontuacao += pontos;
        if (pontuacao < 0) pontuacao = 0; // Não deixa a pontuação ficar negativa
        document.getElementById("pontuacao-valor").textContent = pontuacao;
    }

    function trocarTela(id) {
      document.querySelectorAll(".tela").forEach(el => el.classList.remove("ativa"));
      document.getElementById(id).classList.add("ativa");
    }

    function selectSubject(subj) {
      materia = subj;
      document.getElementById("titulo-materia").textContent =
        subj === "matematica" ? "🧮 Matemática" : "📚 Português";
      trocarTela("menu-nivel");
    }

    function goBackToMain() { trocarTela("menu-principal"); }
    function goBackToLevel() { trocarTela("menu-nivel"); }

    // Função 'startLevel' modificada para usar 'mockData'
    function startLevel(level) {
      nivel = level;
      indiceAtual = 0;
      pontuacao = 0; // Zera a pontuação ao iniciar o nível
      atualizarPontuacao(0); // Atualiza o display

      // Verifica se existem dados para essa matéria e nível
      if (!mockData[materia] || !mockData[materia][level] || mockData[materia][level].length === 0) {
        showModal("Ops!", "Ainda não temos cruzadinhas para este nível. Tente outro!");
        return;
      }

      cruzadinhas = mockData[materia][level];
      carregarCruzadinha(indiceAtual);
      trocarTela("jogo");
    }

    function carregarCruzadinha(i) {
      const puzzle = cruzadinhas[i];
      const grid = document.getElementById("grade");
      const clues = document.getElementById("lista-dicas");
      document.getElementById("titulo-jogo").textContent = puzzle.titulo;
      document.getElementById("descricao-jogo").textContent = puzzle.descricao;

      grid.innerHTML = "";
      clues.innerHTML = "";
      grid.style.gridTemplateColumns = `repeat(${puzzle.tamanho}, 48px)`;

      for (let r = 0; r < puzzle.tamanho; r++) {
        for (let c = 0; c < puzzle.tamanho; c++) {
          const val = puzzle.grade[r][c];
          const cell = document.createElement("input");
          cell.type = "text";
          cell.maxLength = 1;
          cell.dataset.row = r;
          cell.dataset.col = c;

          if (val === "#") {
            cell.classList.add("filled");
            cell.disabled = true;
          } else {
            cell.classList.add("cell");
            cell.dataset.correct = val.toUpperCase();
            cell.addEventListener("input", e => {
              e.target.value = e.target.value.toUpperCase();
              // Mover para a próxima célula (lógica simples)
              const nextInput = findNextInput(e.target);
              if (nextInput) {
                nextInput.focus();
              }
            });
          }
          grid.appendChild(cell);
        }
      }

      puzzle.dicas.forEach((d, idx) => {
        const li = document.createElement("li");
        li.textContent = `${d}`; 
        clues.appendChild(li);
      });
    }

    function findNextInput(currentInput) {
      let next = currentInput.nextElementSibling;
      while(next) {
        if (next.tagName === "INPUT" && !next.disabled) {
          return next;
        }
        next = next.nextElementSibling;
      }
      return null;
    }

    function checkAnswers() {
      let allCorrect = true;
      let erros = 0;
      document.querySelectorAll(".cell").forEach(cell => {
        if (cell.disabled) return;
        if (cell.value === cell.dataset.correct) {
          cell.classList.add("correct");
          cell.classList.remove("incorrect");
        } else {
          cell.classList.add("incorrect");
          cell.classList.remove("correct");
          if(cell.value !== "") {
            allCorrect = false;
            erros++; // Conta um erro
          } else {
            allCorrect = false; // Célula vazia também não está correta
          }
        }
      });
      
      if(allCorrect) {
        atualizarPontuacao(100); // Adiciona 100 pontos por acertar
        showModal("Parabéns!", `Você acertou tudo e ganhou 100 pontos! Pontuação total: ${pontuacao}`);
      } else {
         let penalidade = erros * 5;
         atualizarPontuacao(-penalidade); // Tira 5 pontos por erro
         showModal("Quase lá!", `Você errou ${erros} ${erros > 1 ? 'respostas' : 'resposta'} e perdeu ${penalidade} pontos. Tente novamente!`);
      }
    }

    function resetGame() {
      document.querySelectorAll(".cell").forEach(cell => {
        if (!cell.disabled) {
          cell.value = "";
          cell.classList.remove("correct", "incorrect");
        }
      });
    }

    function nextCrossword() {
      indiceAtual++;
      if (indiceAtual < cruzadinhas.length) {
        carregarCruzadinha(indiceAtual);
      } else {
        showModal("🎉 Fim de Jogo!", `Você completou todas as cruzadinhas deste nível! Sua pontuação final foi: ${pontuacao} pontos!`);
        trocarTela("menu-nivel");
      }
    }
  </script>
</body>
</html>
```
