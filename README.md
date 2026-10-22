<!DOCTYPE html>
<html lang="el">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Petro59 | Dark World</title>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100vh;
  background: #080808;
  color: white;
  font-family: Arial, sans-serif;
}

header {
  text-align: center;
  padding: 25px;
  background: #111;
  border-bottom: 1px solid #333;
}

header h1 {
  margin: 0;
  letter-spacing: 5px;
  color: #d60000;
}

header p {
  color: #999;
}

main {
  width: 90%;
  max-width: 1000px;
  margin: 30px auto;
}

.controls {
  background: #151515;
  padding: 20px;
  border-radius: 12px;
  margin-bottom: 25px;
}

input, textarea, button {
  width: 100%;
  margin: 8px 0;
  padding: 12px;
  border-radius: 7px;
  border: 1px solid #444;
  background: #222;
  color: white;
}

button {
  background: #b00000;
  border: none;
  cursor: pointer;
  font-weight: bold;
}

button:hover {
  background: #e00000;
}

.preview {
  background: #101010;
  padding: 15px;
  border-radius: 12px;
  text-align: center;
}

#photo {
  display: none;
  width: 100%;
  max-height: 600px;
  object-fit: contain;
  border-radius: 8px;
  margin-top: 10px;
}

video {
  display: none;
  width: 100%;
  max-height: 600px;
  margin-top: 15px;
  border-radius: 8px;
}

#caption {
  white-space: pre-wrap;
  overflow-wrap: anywhere;
  font-size: 22px;
  padding: 20px;
  color: #eee;
}

footer {
  text-align: center;
  color: #666;
  padding: 25px;
}
</style>
</head>

<body>

<header>
  <h1>PETRO59</h1>
  <p>WELCOME TO MY DARK WORLD 🖤</p>
</header>

<main>
  <section class="controls">
    <h2>Δημιούργησε το δικό σου design</h2>

    <label>📸 Βάλε φωτογραφία</label>
    <input type="file" id="photoInput" accept="image/*">

    <label>🎬 Βάλε βίντεο</label>
    <input type="file" id="videoInput" accept="video/*">

    <label>✍️ Γράψε το κείμενό σου</label>
    <textarea id="textInput" rows="4"
      placeholder="Γράψε εδώ ό,τι θέλεις..."></textarea>

    <button id="updateBtn">ΔΕΙΞΕ ΤΟ DESIGN</button>
  </section>

  <section class="preview">
    <h2 id="previewTitle">PETRO59 🖤</h2>

    <img id="photo" alt="Η φωτογραφία μου">

    <video id="video" controls loop playsinline></video>

    <p id="caption">ALONE BUT NEVER WEAK.</p>
  </section>
</main>

<footer>
  PETRO59 © MY WORLD
</footer>

<script>
const photoInput = document.getElementById("photoInput");
const videoInput = document.getElementById("videoInput");
const photo = document.getElementById("photo");
const video = document.getElementById("video");

let photoURL = "";
let videoURL = "";

photoInput.addEventListener("change", () => {
  if (photoURL) URL.revokeObjectURL(photoURL);
  const file = photoInput.files[0];
  if (!file) return;

  photoURL = URL.createObjectURL(file);
  photo.src = photoURL;
  photo.style.display = "block";
});

videoInput.addEventListener("change", () => {
  if (videoURL) URL.revokeObjectURL(videoURL);
  const file = videoInput.files[0];
  if (!file) return;

  videoURL = URL.createObjectURL(file);
  video.src = videoURL;
  video.style.display = "block";
  video.load();
});

document.getElementById("updateBtn")
  .addEventListener("click", () => {
    document.getElementById("caption").textContent =
      document.getElementById("textInput").value;
  });
</script>

</body>
</html>
