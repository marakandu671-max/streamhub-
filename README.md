<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>StreamHub.media</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    }

    body {
      background-color: #0d1117;
      color: #f0f6fc;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    /* Header & Navigation */
    header {
      background-color: #161b22;
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid #30363d;
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .logo {
      font-size: 1.5rem;
      font-weight: 800;
      color: #58a6ff;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .logo span {
      color: #f0f6fc;
    }

    nav {
      display: flex;
      gap: 1.5rem;
    }

    nav a {
      color: #8b949e;
      text-decoration: none;
      font-weight: 500;
      transition: color 0.2s ease;
    }

    nav a:hover, nav a.active {
      color: #58a6ff;
    }

    /* Main Container */
    main {
      flex: 1;
      padding: 2rem;
      max-width: 1200px;
      margin: 0 auto;
      width: 100%;
    }

    /* Hero Banner */
    .hero {
      background: linear-gradient(135deg, #1f6beb 0%, #0d1117 100%);
      border-radius: 16px;
      padding: 3rem 2rem;
      margin-bottom: 2.5rem;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
      border: 1px solid #30363d;
    }

    .hero h1 {
      font-size: 2.5rem;
      margin-bottom: 0.75rem;
    }

    .hero p {
      color: #c9d1d9;
      font-size: 1.1rem;
      max-width: 600px;
      margin-bottom: 1.5rem;
    }

    .hero-btn {
      background-color: #238636;
      color: #ffffff;
      padding: 0.75rem 1.5rem;
      border: none;
      border-radius: 8px;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      transition: background-color 0.2s ease;
    }

    .hero-btn:hover {
      background-color: #2ea043;
    }

    /* Filter / Category Tabs */
    .categories {
      display: flex;
      gap: 1rem;
      margin-bottom: 1.5rem;
      overflow-x: auto;
      padding-bottom: 0.5rem;
    }

    .cat-btn {
      background-color: #21262d;
      color: #c9d1d9;
      border: 1px solid #30363d;
      padding: 0.5rem 1.25rem;
      border-radius: 20px;
      cursor: pointer;
      font-size: 0.9rem;
      transition: all 0.2s ease;
      white-space: nowrap;
    }

    .cat-btn.active, .cat-btn:hover {
      background-color: #30363d;
      color: #58a6ff;
      border-color: #58a6ff;
    }

    /* Video Grid */
    .video-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 1.5rem;
    }

    .card {
      background-color: #161b22;
      border: 1px solid #30363d;
      border-radius: 12px;
      overflow: hidden;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
      cursor: pointer;
    }

    .card:hover {
      transform: translateY(-4px);
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
      border-color: #8b949e;
    }

    .thumbnail {
      width: 100%;
      height: 160px;
      background-color: #21262d;
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
      background-size: cover;
      background-position: center;
    }

    .play-icon {
      width: 50px;
      height: 50px;
      background-color: rgba(0, 0, 0, 0.7);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #58a6ff;
      font-size: 1.2rem;
      transition: transform 0.2s ease;
    }

    .card:hover .play-icon {
      transform: scale(1.15);
      background-color: #58a6ff;
      color: #0d1117;
    }

    .card-content {
      padding: 1rem;
    }

    .card-title {
      font-size: 1.05rem;
      font-weight: 600;
      margin-bottom: 0.5rem;
      color: #f0f6fc;
    }

    .card-info {
      font-size: 0.85rem;
      color: #8b949e;
      display: flex;
      justify-content: space-between;
    }

    /* Footer */
    footer {
      background-color: #161b22;
      border-top: 1px solid #30363d;
      padding: 1.5rem;
      text-align: center;
      color: #8b949e;
      font-size: 0.85rem;
      margin-top: 3rem;
    }
  </style>
</head>
<body>

  <header>
    <div class="logo">
      🎬 StreamHub<span>.media</span>
    </div>
    <nav>
      <a href="#" class="active">Home</a>
      <a href="#">Trending</a>
      <a href="#">Categories</a>
      <a href="#">Saved</a>
    </nav>
  </header>

  <main>
    <section class="hero">
      <h1>Welcome to StreamHub</h1>
      <p>Your ultimate destination for discovering trending videos, live streams, and media content across all platforms.</p>
      <button class="hero-btn" onclick="alert('Feature coming soon!')">Explore Featured Streams</button>
    </section>

    <div class="categories">
      <button class="cat-btn active">All</button>
      <button class="cat-btn">Gaming</button>
      <button class="cat-btn">Music</button>
      <button class="cat-btn">Live</button>
      <button class="cat-btn">Podcasts</button>
      <button class="cat-btn">Tech</button>
    </div>

    <div class="video-grid">
      <!-- Card 1 -->
      <div class="card">
        <div class="thumbnail" style="background-image: linear-gradient(to bottom, transparent, rgba(0,0,0,0.8)), url('https://picsum.photos/400/225?random=1');">
          <div class="play-icon">▶</div>
        </div>
        <div class="card-content">
          <div class="card-title">Ultimate Gaming Setup Showcase 2026</div>
          <div class="card-info">
            <span>Tech Gaming</span>
            <span>120k views</span>
          </div>
        </div>
      </div>

      <!-- Card 2 -->
      <div class="card">
        <div class="thumbnail" style="background-image: linear-gradient(to bottom, transparent, rgba(0,0,0,0.8)), url('https://picsum.photos/400/225?random=2');">
          <div class="play-icon">▶</div>
        </div>
        <div class="card-content">
          <div class="card-title">Relaxing Lo-Fi Beats & Music Stream</div>
          <div class="card-info">
            <span>Music</span>
            <span>LIVE 🔴</span>
          </div>
        </div>
      </div>

      <!-- Card 3 -->
      <div class="card">
        <div class="thumbnail" style="background-image: linear-gradient(to bottom, transparent, rgba(0,0,0,0.8)), url('https://picsum.photos/400/225?random=3');">
          <div class="play-icon">▶</div>
        </div>
        <div class="card-content">
          <div class="card-title">Building Modern Web Applications</div>
          <div class="card-info">
            <span>Coding</span>
            <span>45k views</span>
          </div>
        </div>
      </div>

      <!-- Card 4 -->
      <div class="card">
        <div class="thumbnail" style="background-image: linear-gradient(to bottom, transparent, rgba(0,0,0,0.8)), url('https://picsum.photos/400/225?random=4');">
          <div class="play-icon">▶</div>
        </div>
        <div class="card-content">
          <div class="card-title">Top 10 Indie Games of the Month</div>
          <div class="card-info">
            <span>Gaming</span>
            <span>89k views</span>
          </div>
        </div>
      </div>
    </div>
  </main>

  <footer>
    <p>&copy; 2026 StreamHub.media - Built with HTML & CSS</p>
  </footer>

</body>
</html># streamhub-
Were to watch movies and video 
