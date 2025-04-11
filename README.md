<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Happy Birthday Najipah!</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body, html {
      width: 100%;
      height: 100%;
      background-color: #000;
      overflow: hidden;
      font-family: 'Arial', sans-serif;
      color: white;
    }
    .slideshow-container {
      width: 100vw;
      height: 100vh;
      position: relative;
    }
    .slide {
      display: none;
      width: 100%;
      height: 100%;
      position: absolute;
      top: 0;
      left: 0;
      justify-content: center;
      align-items: center;
    }
    .slide.active {
      display: flex;
    }
    img, video {
      max-width: 100%;
      max-height: 100%;
      border-radius: 10px;
    }
    .nav {
      position: absolute;
      bottom: 30px;
      width: 100%;
      text-align: center;
    }
    .nav button {
      background: rgba(255,255,255,0.1);
      border: 1px solid #fff;
      color: white;
      padding: 10px 20px;
      margin: 0 10px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
    }
    h1 {
      position: absolute;
      top: 20px;
      width: 100%;
      text-align: center;
      font-size: 28px;
      color: #ffb3f0;
      z-index: 2;
      text-shadow: 0 0 10px #ff69b4;
    }
  </style>
</head>
<body>
  <h1>Happy Level Up Najipah!</h1>
  <div class="slideshow-container" id="slideshow">
    <!-- Slides akan diisi oleh JavaScript -->
  </div>
  <div class="nav">
    <button onclick="prevSlide()">Prev</button>
    <button onclick="nextSlide()">Next</button>
  </div>

  <script>
    const files = [
      "1732171a394fd22a3d5afb3b71535c39.jpg",
      "2b435959bd75ae82b1c0239b22b4c068.mp4",
      "400a2337594af3a582178b8dbb67d0fb.jpg",
      "4089e292ffeb301eb8b3904709d4e819_720w.mp4",
      "60e8e78980ec4621f06b9cb0e0291a73.jpg",
      "7b8921e2e0e5d6999112d85e2a9f5f29.mp4",
      "9236718622fdf8ea7c24794b6fd79fc1.jpg",
      "9c49bce0509c1c234de4076f23d0adf7.mp4",
      "GAThgnEbIAAHeCa.jpeg",
      "YouTube - YouTube (720p, h264).mp4",
      "c1619fd4f3df0f3c5022fa43cb088734.jpg",
      "d2baf82837f3e7a7f65aae2789f7670b.jpg",
      "d97141907cf3deb79092050f7a1bdca8.mp4",
      "d9eb1cb6a5fe34dbb85ae400bb86b0c4.jpg",
      "ddc809c4c6ed99767dad26df0e0f26ab.jpg"
    ];

    const slideshow = document.getElementById('slideshow');

    files.forEach((file, index) => {
      const slide = document.createElement('div');
      slide.classList.add('slide');
      if (index === 0) slide.classList.add('active');

      const ext = file.split('.').pop().toLowerCase();
      if (['mp4', 'webm', 'ogg'].includes(ext)) {
        const vid = document.createElement('video');
        vid.src = file;
        vid.controls = true;
        slide.appendChild(vid);
      } else {
        const img = document.createElement('img');
        img.src = file;
        slide.appendChild(img);
      }

      slideshow.appendChild(slide);
    });

    let current = 0;
    const slides = document.querySelectorAll('.slide');

    function showSlide(i) {
      slides[current].classList.remove('active');
      current = (i + slides.length) % slides.length;
      slides[current].classList.add('active');
    }

    function nextSlide() {
      showSlide(current + 1);
    }

    function prevSlide() {
      showSlide(current - 1);
    }
  </script>
</body>
</html>
