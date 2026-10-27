<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>StreamHub.media - Short K-Dramas</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; }
    body { background-color: #0d1117; color: #f0f6fc; min-height: 100vh; display: flex; flex-direction: column; }
    
    /* Header */
    header { background-color: #161b22; padding: 1rem 2rem; display: flex; justify-content: space-between; align-items: center; border-bottom: 1px solid #30363d; sticky: top; }
    .logo { font-size: 1.5rem; font-weight: bold; color: #58a6ff; text-decoration: none; display: flex; align-items: center; gap: 8px; }
    .search-bar { flex: 0 1 400px; margin: 0 1rem; }
    .search-bar input { width: 100%; padding: 0.5rem 1rem; border-radius: 20px; border: 1px solid #30363d; background: #0d1117; color: white; outline: none; }
    .search-bar input:focus { border-color: #58a6ff; }
    
    /* Hero Banner */
    .hero { background: linear-gradient(135deg, #1f6feb, #8957e5); padding: 3rem 2rem; text-align: center; border-radius: 12rem; margin: 1.5rem 2rem; }
    .hero h1 { font-size: 2.2rem; margin-bottom: 0.5rem; }
    .hero p { color: #e6edf3; font-size: 1.1rem; }

    /* Categories */
    .categories { display: flex; gap: 0.5rem; padding: 0 2rem 1.5rem 2rem; overflow-x: auto; }
    .cat-btn { background: #21262d; border: 1px solid #30363d; color: #c9d1d9; padding: 0.5rem 1rem; border-radius: 20px; cursor: pointer; transition: 0.2s; white-space: nowrap; }
    .cat-btn:hover, .cat-btn.active { background: #388bfd; color: white; border-color: #388bfd; }

    /* Video Grid */
    .container { padding: 0 2rem 3rem 2rem; flex: 1; }
    .grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 1.5rem; }
    .card { background: #161b22; border: 1px solid #30363d; border-radius: 12px; overflow: hidden; cursor: pointer; transition: transform 0.2s, box-shadow 0.2s; }
    .card:hover { transform: translateY(-4px); box-shadow: 0 8px 24px rgba(0,0,0,0.5); }
    .card-thumb { width: 100%; height: 160px; object-fit: cover; }
    .card-info { padding: 1rem; }
    .card-title { font-size: 1rem; font-weight: 600; margin-bottom: 0.5rem; color: #f0f6fc; line-height: 1.3; }
    .card-tag { display: inline-block; background: #238636; color: white; padding: 2px 8px; border-radius: 10px; font-size: 0.75rem; margin-top: 4px; }

    /* Video Modal */
    .modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.85); justify-content: center; align-items: center; z-index: 1000; }
    .modal-content { background: #161b22; border: 1px solid #30363d; width: 90%; max-width: 800px; border-radius: 12px; overflow: hidden; position: relative; }
    .close-btn { position: absolute; top: 10px; right: 15px; color: #fff; font-size: 28px; font-weight: bold; cursor: pointer; z-index: 1001; }
    .video-wrapper { position: relative; padding-bottom: 56.25%; height: 0; }
    .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0; }
  </style>
</head>
<body>

  <header>
    <a href
