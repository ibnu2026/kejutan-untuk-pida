<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
  <!-- Mengimpor Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Roboto&display=swap" rel="stylesheet">
  <title>Kejutan Untuk Sayangku terluvvv❤️❤️❤️</title>
  <style>
    body {
      font-family: 'Roboto', sans-serif;
      text-align: center;
      background: linear-gradient(135deg, #4a90e2, #a0c4ff);
      color: white;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      transition: all 0.5s ease-in-out;
      overflow: hidden;
    }

    .container, .surprise, .video-section {
      padding: 20px;
      background: rgba(255, 255, 255, 0.2);
      border-radius: 15px;
      backdrop-filter: blur(10px);
      max-width: 600px;
      width: 90%;
    }

    /* Menggunakan Dancing Script untuk judul */
    h1, h2 {
      font-family: 'Dancing Script', cursive;
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
    }
    
    /* Style khusus untuk teks yang diketik */
    #typedText {
      font-size: 18px;
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
      margin: 20px 0;
      min-height: 80px;
    }

    button {
      padding: 10px 20px;
      margin-top: 20px;
      background-color: #007bff;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      background-color: #0056b3;
    }

    .hidden {
      display: none;
    }

    /* Ukuran video yang lebih kecil untuk kenyamanan tampilan */
    video {
      width: 100%;
      height: auto;
      max-height: 60vh;
      border-radius: 10px;
      border: 2px solid white;
      position: relative;
    }

    .video-section {
      position: relative;
    }

    /* Style untuk tombol akhir */
    #endButton {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      padding: 10px 20px;
      background-color: #007bff;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: 0.3s;
      z-index: 9999;
    }

    /* Media Query untuk HP Redmi 12C (lebar maksimum 720px) */
    @media (max-width: 720px) {
      body {
        max-width: 720px;
        margin: 0 auto;
        height: 100vh;
        padding: 0 10px;
      }
      .container, .surprise, .video-section {
        width: 100%;
        padding: 15px;
        border-radius: 10px;
      }
      h1 {
        font-size: 24px;
      }
      h2 {
        font-size: 20px;
      }
      #typedText {
        font-size: 16px;
      }
      button {
        font-size: 16px;
        padding: 8px 16px;
      }
      video {
        max-height: 50vh;
      }
    }

    /* Media Query untuk HP Infinix Hot 40i (lebar antara 721px dan 800px) */
    @media (min-width: 721px) and (max-width: 800px) {
      body {
        max-width: 800px;
        margin: 0 auto;
        height: 100vh;
        padding: 0 10px;
      }
      .container, .surprise, .video-section {
        width: 100%;
        padding: 15px;
        border-radius: 10px;
      }
      h1 {
        font-size: 26px;
      }
      h2 {
        font-size: 22px;
      }
      #typedText {
        font-size: 18px;
      }
      button {
        font-size: 17px;
        padding: 10px 18px;
      }
      video {
        max-height: 55vh;
      }
    }
  </style>
</head>
<body>

  <div class="container">
    <h1 class="fade-in">Hai Sayangku terluvvv ❤️❤️❤️</h1>
    <p class="fade-in">Aku punya sesuatu</p>
    <button id="openSurprise">Klik di sini!</button>
  </div>

  <div class="surprise hidden">
    <h2>Surat Cinta Untuk terluvvv❤️❤️❤️ 💌</h2>
    <!-- Paragraf dengan efek typewriter -->
    <p id="typedText"></p>
    <audio id="bgMusic" loop>
      <source src="lagu.mp3" type="audio/mpeg">
    </audio>
    <button id="startVideo">Lihat Video Ini 📸</button>
  </div>

  <div class="video-section hidden">
    <h2>Kenangan Indah Yang Akan Selalu Aku Ingat</h2>
    <video id="video1" autoplay muted>
      <source src="video1.mp4" type="video/mp4">
    </video>
    <video id="video2" class="hidden" autoplay muted>
      <source src="video2.mp4" type="video/mp4">
    </video>
    <video id="video3" class="hidden" autoplay muted>
      <source src="video3.mp4" type="video/mp4">
    </video>
    
    <!-- Satu tombol untuk mengubah pesan, fade out musik, dan nantinya keluar -->
    <button id="endButton" class="hidden">Satu pesan lagi...</button>
  </div>

  <script>
    let clickCount = 0;
    let exitReady = false;
    const bgMusic = document.getElementById("bgMusic");
    const endButton = document.getElementById("endButton");
    const typedTextEl = document.getElementById("typedText");
    const typeText = "Sayangku, terima kasih sudah menjadi bagian terbaik dalam hidupku. Aku bersyukur karena bisa mendapatkan wanita yang setia, yang tidak pernah aku jumpai sebelumnya. 💖";
    let typeIndex = 0;
    
    function typeWriter() {
      if (typeIndex < typeText.length) {
        typedTextEl.innerHTML += typeText.charAt(typeIndex);
        typeIndex++;
        setTimeout(typeWriter, 50);
      }
    }
    
    document.getElementById("openSurprise").addEventListener("click", function() {
      document.querySelector(".container").classList.add("hidden");
      document.querySelector(".surprise").classList.remove("hidden");
      // Kosongkan konten typedText dan mulai efek pengetikan
      typedTextEl.innerHTML = "";
      typeIndex = 0;
      typeWriter();
      bgMusic.play();
    });

    document.getElementById("startVideo").addEventListener("click", function() {
      document.querySelector(".surprise").classList.add("hidden");
      document.querySelector(".video-section").classList.remove("hidden");
    });

    document.getElementById("video1").addEventListener("ended", function() {
      document.getElementById("video1").classList.add("hidden");
      document.getElementById("video2").classList.remove("hidden");
    });

    document.getElementById("video2").addEventListener("ended", function() {
      document.getElementById("video2").classList.add("hidden");
      document.getElementById("video3").classList.remove("hidden");
    });

    document.getElementById("video3").addEventListener("ended", function() {
      // Setelah video 3 selesai, tampilkan tombol
      endButton.classList.remove("hidden");
    });

    endButton.addEventListener("click", function() {
      if (exitReady) {
        // Jika sudah exitReady, eksekusi perintah keluar
        window.open('', '_self').close();
        window.location.href = "about:blank";
      } else {
        clickCount++;
        if (clickCount === 1) {
          endButton.innerText = "Klik lagi...";
          endButton.style.top = "60%";
        } else if (clickCount === 2) {
          endButton.innerText = "Sekali lagi...";
          endButton.style.top = "30%";
        } else if (clickCount === 3) {
          endButton.innerText = "Aku sayang terluvvv ❤️";
          endButton.style.top = "70%";
          // Mulai proses fade out musik
          let fadeOut = setInterval(function() {
            if (bgMusic.volume > 0.1) {
              bgMusic.volume = Math.max(0, bgMusic.volume - 0.1);
            } else {
              bgMusic.pause();
              clearInterval(fadeOut);
              // Setelah musik mati, ubah tombol untuk keluar tanpa berpindah posisi
              endButton.innerText = "Keluar dari Website ❌";
              endButton.style.top = "20%";
              exitReady = true;
            }
          }, 500);
        }
      }
    });
  </script>

</body>
</html>
