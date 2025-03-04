<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Further Math Tutor</title>
  <link href="https://fonts.googleapis.com/css?family=Roboto:300,400,700&display=swap" rel="stylesheet">
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    body {
      background-image: url('math-background-jbcyizvw0ckuvcro.jpg');
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center;
      background-attachment: fixed;
      font-family: 'Roboto', sans-serif;
      color: #f4f4f4;
      min-height: 100vh;
    }
    header {
      width: 100%;
      text-align: center;
      padding: 20px;
      background-color: rgba(63, 63, 63, 0.8);
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
    }
    header h1 {
      font-size: 2.5em;
      letter-spacing: 1px;
      font-weight: 700;
      color: #f4f4f4;
    }
    main {
      padding: 20px;
    }
    .columns {
      display: flex;
      gap: 20px;
      max-width: 1200px;
      margin: 40px auto;
      width: 100%;
    }
    /* Left column (preview) takes up more space */
    .preview-column {
      flex: 2;
    }
    /* Right column (sidebar) is narrower */
    .sidebar-column {
      flex: 1;
    }
    .preview {
      background: rgba(66, 66, 66, 0.9);
      border: 1px solid rgba(255, 255, 255, 0.2);
      border-radius: 15px;
      overflow: hidden;
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
    }
    .preview iframe {
      width: 100%;
      height: 600px; /* Larger preview */
      border: none;
    }
    .card {
      background: rgba(66, 66, 66, 0.95);
      border-radius: 15px;
      padding: 20px;
      text-align: center;
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
    }
    .card h2 {
      font-size: 1.5em;
      margin-bottom: 10px;
    }
    .pdf-options {
      list-style: none;
      padding: 0;
      margin-bottom: 20px;
    }
    .pdf-options li {
      padding: 10px;
      margin: 5px 0;
      background: rgba(40, 40, 40, 0.8);
      border-radius: 8px;
      cursor: pointer;
      transition: background 0.3s ease;
    }
    .pdf-options li:hover {
      background: rgba(40, 40, 40, 1);
    }
    .preview-description {
      margin-bottom: 20px;
      font-size: 1.1em;
    }
    .btn {
      background: linear-gradient(45deg, #0288d1, #00acc1);
      color: #fff;
      border: none;
      padding: 15px 30px;
      font-size: 18px;
      border-radius: 50px;
      cursor: pointer;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    .btn:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 15px rgba(0, 0, 0, 0.3);
    }
    @media (max-width: 768px) {
      .columns {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>
  <header>
    <h1>Further Math Tutor</h1>
  </header>
  <main>
    <div class="columns">
      <!-- Left Column: PDF Preview -->
      <div class="column preview-column">
        <div class="preview">
          <iframe id="pdfPreview" src="0620_s24_qp_41.pdf"></iframe>
        </div>
      </div>
      <!-- Right Column: Sidebar with Options -->
      <div class="column sidebar-column">
        <div class="card">
          <h2>Select a PDF</h2>
          <ul class="pdf-options">
            <li onclick="updatePreview('0620_s24_qp_41.pdf', 'Chemistry Paper 4 Theory (Extended) May/June 2024')">
              Chemistry Paper 4 Theory
            </li>
            <li onclick="updatePreview('0625_w23_ms_22.pdf', 'Physics Mark Scheme (Extended)')">
              Physics Mark Scheme
            </li>
            <li onclick="updatePreview('0625_w23_qp_22.pdf', 'Physics Question Paper (Extended)')">
              Physics Question Paper
            </li>
          </ul>
          <div class="preview-description" id="previewDescription">
            Chemistry Paper 4 Theory (Extended) May/June 2024
          </div>
          <button class="btn" id="viewButton" onclick="window.open('0620_s24_qp_41.pdf', '_blank')">
            View Full PDF
          </button>
        </div>
      </div>
    </div>
  </main>
  <script>
    function updatePreview(file, description) {
      document.getElementById('pdfPreview').src = file;
      document.getElementById('viewButton').onclick = function() {
         window.open(file, '_blank');
      };
      document.getElementById('previewDescription').textContent = description;
    }
  </script>
</body>
</html>
