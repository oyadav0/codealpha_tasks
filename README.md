# codealpha_tasks
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Modi Ji Image Gallery</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background: #f4f4f4;
      text-align: center;
    }

    h1 {
      background-color: #e74c3c;
      color: white;
      padding: 20px;
      margin: 0;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 15px;
      padding: 20px;
      max-width: 1000px;
      margin: auto;
    }

    .gallery img {
      width: 100%;
      cursor: pointer;
      border-radius: 10px;
      transition: 0.3s;
    }

    .gallery img:hover {
      transform: scale(1.05);
    }

    .preview {
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background-color: rgba(0,0,0,0.8);
      display: none;
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }

    .preview img {
      max-width: 90%;
      max-height: 80%;
      border-radius: 10px;
    }

    .preview span {
      position: absolute;
      top: 20px;
      right: 30px;
      font-size: 40px;
      color: white;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <h1>Modi Ji Image Gallery</h1>

  <div class="gallery">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f6/Narendra_Modi_2020.jpg/440px-Narendra_Modi_2020.jpg" alt="Modi 1">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/76/Narendra_Modi_in_2021.jpg/440px-Narendra_Modi_in_2021.jpg" alt="Modi 2">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/14/Narendra_Modi_SCO_2022.jpg/440px-Narendra_Modi_SCO_2022.jpg" alt="Modi 3">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2c/PM_Modi_Press_Conference.jpg/440px-PM_Modi_Press_Conference.jpg" alt="Modi 4">
  </div>

  <div class="preview" id="preview">
    <span onclick="closePreview()">&times;</span>
    <img id="preview-img" src="" alt="Preview">
  </div>

  <script>
    const images = document.querySelectorAll(".gallery img");
    const previewBox = document.getElementById("preview");
    const previewImg = document.getElementById("preview-img");

    images.forEach(img => {
      img.addEventListener("click", () => {
        previewImg.src = img.src;
        previewBox.style.display = "flex";
      });
    });

    function closePreview() {
      previewBox.style.display = "none";
    }
  </script>

</body>
</html>

