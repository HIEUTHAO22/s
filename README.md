<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Wedding Invitation | Nguyễn Văn A & Trần Thị B</title>
  <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Roboto:wght@400;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://unpkg.com/swiper/swiper-bundle.min.css" />
  <link rel="stylesheet" href="https://unpkg.com/aos@2.3.1/dist/aos.css"/>
  <style>
    html, body {
      margin: 0;
      padding: 0;
      font-family: 'Roboto', sans-serif;
      color: #fff;
      overflow-x: hidden;
    }
    body {
      background: #000;
    }
    .video-bg {
      position: fixed;
      top: 0; left: 0;
      min-width: 100%;
      min-height: 100%;
      z-index: -2;
      object-fit: cover;
    }
    .overlay {
      background: rgba(0,0,0,0.6);
      position: relative;
      z-index: 1;
      padding: 20px;
    }
    h1 {
      font-family: 'Great Vibes', cursive;
      font-size: 4em;
      margin: 20px 0;
    }
    h2 {
      font-size: 2em;
      margin-bottom: 10px;
    }
    .countdown {
      font-size: 2em;
      margin: 20px 0;
    }
    .swiper-container {
      width: 100%;
      padding: 20px 0;
    }
    .swiper-slide img {
      width: 90%;
      border-radius: 10px;
    }
    .timeline {
      text-align: left;
      max-width: 800px;
      margin: 0 auto;
    }
    .timeline-event {
      margin: 20px 0;
      padding: 10px;
      background: rgba(255,255,255,0.1);
      border-radius: 8px;
    }
    form {
      max-width: 600px;
      margin: 20px auto;
      background: rgba(255,255,255,0.1);
      padding: 20px;
      border-radius: 10px;
    }
    input, textarea {
      width: 100%;
      padding: 10px;
      margin: 5px 0 15px;
      border: none;
      border-radius: 5px;
    }
    button {
      background: #e67e22;
      border: none;
      padding: 10px 20px;
      color: #fff;
      border-radius: 5px;
      font-size: 1em;
    }
    iframe {
      width: 100%;
      height: 300px;
      border: 0;
      border-radius: 10px;
    }
  </style>
</head>
<body>

<video class="video-bg" autoplay muted loop>
  <source src="https://cdn.coverr.co/videos/coverr-couple-walking-on-railway-6332/1080p.mp4" type="video/mp4">
</video>

<audio autoplay loop>
  <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mpeg">
</audio>

<div class="overlay">
  <h1 data-aos="fade-down">Nguyễn Văn A & Trần Thị B</h1>
  <h2 data-aos="fade-up">Trân trọng kính mời</h2>
  <div class="countdown" id="countdown" data-aos="zoom-in"></div>

  <div class="swiper-container" data-aos="fade-up">
    <div class="swiper-wrapper">
      <div class="swiper-slide"><img src="https://i.imgur.com/5tj6S7O.jpg" alt="Ảnh cưới 1"></div>
      <div class="swiper-slide"><img src="https://i.imgur.com/2D4I7xR.jpg" alt="Ảnh cưới 2"></div>
      <div class="swiper-slide"><img src="https://i.imgur.com/1Jm8yCs.jpg" alt="Ảnh cưới 3"></div>
    </div>
  </div>

  <div class="timeline" data-aos="fade-up">
    <div class="timeline-event"><strong>16:00</strong> | Lễ cưới tại nhà thờ</div>
    <div class="timeline-event"><strong>18:00</strong> | Tiệc chính tại Nhà hàng Hạnh Phúc</div>
    <div class="timeline-event"><strong>21:00</strong> | Tiệc đêm, giao lưu văn nghệ</div>
  </div>

  <form data-aos="fade-up">
    <h2>Xác nhận tham dự</h2>
    <input type="text" placeholder="Tên của bạn" required>
    <input type="tel" placeholder="Số điện thoại" required>
    <textarea placeholder="Lời chúc"></textarea>
    <button type="submit">Gửi</button>
  </form>

  <h2 data-aos="fade-up">Bản đồ</h2>
  <iframe src="https://www.google.com/maps/embed/v1/place?key=AIzaSyDUMMY_KEY&q=Nhà+hàng+Hạnh+Phúc+123+Đường+Hoa+TP.HCM" allowfullscreen></iframe>
</div>

<script src="https://unpkg.com/swiper/swiper-bundle.min.js"></script>
<script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
<script>
  AOS.init();

  new Swiper('.swiper-container', {
    loop: true,
    autoplay: {
      delay: 3000,
    },
  });

  const targetDate = new Date("2026-01-01T18:00:00").getTime();
  const countdownEl = document.getElementById("countdown");
  setInterval(() => {
    const now = new Date().getTime();
    const dist = targetDate - now;
    if (dist < 0) {
      countdownEl.innerHTML = "Đã đến giờ hạnh phúc!";
      return;
    }
    const d = Math.floor(dist / (1000 * 60 * 60 * 24));
    const h = Math.floor((dist % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const m = Math.floor((dist % (1000 * 60 * 60)) / (1000 * 60));
    const s = Math.floor((dist % (1000 * 60)) / 1000);
    countdownEl.innerHTML = `${d} ngày ${h} giờ ${m} phút ${s} giây`;
  }, 1000);
</script>

</body>
</html>
