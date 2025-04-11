<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Happy Birthday Najipah!</title>
  <style>
    body {
      background-color: #E4F2F1;
      color: black;
      text-align: center;
      font-family: sans-serif;
      margin: 0;
      padding: 0;
    }
    .container {
      position: relative;
      max-width: 90%;
      margin: auto;
      padding-top: 50px;
    }
    .slide {
      display: none;
    }
    .active {
      display: block;
    }
    button {
      margin: 20px 10px;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      background-color: #444;
      color: white;
      border: none;
      border-radius: 5px;
    }
    img, video {
      max-width: 100%;
      height: auto;
      border-radius: 10px;
    }
  </style>
</head>
<body>

  <h1>Happy Level Up Najipah!</h1>
  <div class="container">
    <!-- Slides will be inserted here -->
  </div>

  <button onclick="prevSlide()">Prev</button>
  <button onclick="nextSlide()">Next</button>

  <script>
    const files = [
      "GAThgnEbIAAHeCa.jpeg",
      "1732171a394fd22a3d5afb3b71535c39.jpg",
      "9236718622fdf8ea7c24794b6fd79fc1.jpg",
      "9c49bce0509c1c234de4076f23d0adf7.mp4",
      "f5f644cce8d930568ab45257ffad9ae1.mp4",
      "e647586ecd982b7947f2e1fd2be01a5f.jpg",
      "d9eb1cb6a5fe34dbb85ae400bb86b0c4.jpg",
      "ddc809c4c6ed99767dad26df0e0f26ab.jpg",
      "c1619fd4f3df0f3c5022fa43cb088734.jpg",
      "d2baf82837f3e7a7f65aae2789f7670b.jpg",
      "2b435959bd75ae82b1c0239b22b4c068.mp4",
      "7b8921e2e0e5d6999112d85e2a9f5f29.mp4",
      "4089e292ffeb301eb8b3904709d4e819_720w.mp4",
      "d97141907cf3deb79092050f7a1bdca8.mp4",
      "60e8e78980ec4621f06b9cb0e0291a73.jpg",
      "400a2337594af3a582178b8dbb67d0fb.jpg",
      "YouTube - YouTube (720p, h264).mp4"
    ];

    const container = document.querySelector('.container');

    files.forEach((file, index) => {
      const slide = document.createElement('div');
      slide.classList.add('slide');
      if (index === 0) slide.classList.add('active');

      const extension = file.split('.').pop().toLowerCase();
      if (['mp4', 'webm', 'ogg'].includes(extension)) {
        const video = document.createElement('video');
        video.controls = true;
        video.src = file;
        slide.appendChild(video);
      } else if (['jpg', 'jpeg', 'png', 'gif'].includes(extension)) {
        const img = document.createElement('img');
        img.src = file;
        slide.appendChild(img);
      }

      container.appendChild(slide);
    });

    let current = 0;
    const slides = document.querySelectorAll('.slide');

    function showSlide(index) {
      slides.forEach((slide, i) => {
        slide.classList.remove('active');
        if (i === index) slide.classList.add('active');
      });
    }

    function nextSlide() {
      current = (current + 1) % slides.length;
      showSlide(current);
    }

    function prevSlide() {
      current = (current - 1 + slides.length) % slides.length;
      showSlide(current);
    }
  </script>

</body>
</html>
