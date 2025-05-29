<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Sousa Filmes - Disney</title>
  <style>
    /* Reset básico */
    * {
      margin: 0; padding: 0; box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    body {
      background: linear-gradient(135deg, #001f4d, #000000);
      color: #d0e6ff;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 20px;
    }
    header {
      margin-bottom: 30px;
      text-align: center;
      text-shadow: 0 0 10px #3f88ff;
    }
    header h1 {
      font-size: 3rem;
      background: linear-gradient(90deg, #3f88ff, #1a1a1a);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      font-weight: 900;
    }
    .container {
      max-width: 1200px;
      width: 100%;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 20px;
    }
    .movie-card {
      background: linear-gradient(145deg, #0f1a40, #001a2d);
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.5);
      overflow: hidden;
      transition: transform 0.3s ease;
      cursor: pointer;
    }
    .movie-card:hover {
      transform: scale(1.05);
      box-shadow: 0 6px 15px #3f88ff;
    }
    .movie-poster {
      width: 100%;
      height: 270px;
      object-fit: cover;
      display: block;
    }
    .movie-title {
      padding: 10px 15px;
      font-weight: 700;
      font-size: 1.1rem;
      color: #a9caff;
      text-align: center;
    }
    footer {
      margin-top: 40px;
      font-size: 0.9rem;
      color: #6f8ab7;
    }
  </style>
</head>
<body>
  <header>
    <h1>Sousa Filmes</h1>
    <p>Todos os filmes da Disney</p>
  </header>
  <main class="container" id="movie-list">
    <!-- Filmes vão ser inseridos aqui via JS -->
  </main>
  <footer>
    &copy; 2025 Sousa Filmes - Criado por Você
  </footer>

  <script>
    // Lista simplificada dos filmes Disney com título e imagem
    const movies = [
      {
        title: "O Rei Leão (1994)",
        poster: "https://upload.wikimedia.org/wikipedia/pt/9/9d/O_Rei_Le%C3%A3o_1994.jpg"
      },
      {
        title: "Frozen: Uma Aventura Congelante (2013)",
        poster: "https://upload.wikimedia.org/wikipedia/pt/f/f7/Frozen_capa.png"
      },
      {
        title: "Aladdin (1992)",
        poster: "https://upload.wikimedia.org/wikipedia/pt/8/8e/Aladdin_movie_poster.jpg"
      },
      {
        title: "Moana: Um Mar de Aventuras (2016)",
        poster: "https://upload.wikimedia.org/wikipedia/pt/2/2e/Moana_capa.png"
      },
      {
        title: "A Bela e a Fera (1991)",
        poster: "https://upload.wikimedia.org/wikipedia/pt/d/d6/Beauty_and_the_Beast_1991.jpg"
      },
      {
        title: "Mulan (1998)",
        poster: "https://upload.wikimedia.org/wikipedia/pt/0/0c/Mulan_1998.jpg"
      },
      {
        title: "Piratas do Caribe: A Maldição do Pérola Negra (2003)",
        poster: "https://upload.wikimedia.org/wikipedia/pt/d/dd/Piratas_do_Caribe_A_Maldição_do_Pérola_Negra.jpg"
      },
      {
        title: "Toy Story (1995)",
        poster: "https://upload.wikimedia.org/wikipedia/pt/1/1a/Toy_Story_-_poster.jpg"
      },
      {
        title: "Branca de Neve e os Sete Anões (1937)",
        poster: "https://upload.wikimedia.org/wikipedia/pt/f/fd/Branca_de_Neve_e_os_Sete_Anões.jpg"
      },
      {
        title: "Coco (2017)",
        poster: "https://upload.wikimedia.org/wikipedia/pt/9/95/Coco_poster.jpg"
      }
    ];

    const container = document.getElementById('movie-list');

    function loadMovies() {
      movies.forEach(movie => {
        const card = document.createElement('div');
        card.className = 'movie-card';

        const img = document.createElement('img');
        img.src = movie.poster;
        img.alt = movie.title;
        img.className = 'movie-poster';

        const title = document.createElement('div');
        title.className = 'movie-title';
        title.textContent = movie.title;

        card.appendChild(img);
        card.appendChild(title);

        container.appendChild(card);
      });
    }

    loadMovies();
  </script>
</body>
</html>
