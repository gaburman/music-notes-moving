<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Floating Music Notes</title>
  <style>
    body {
      margin: 0;
      background: black;
      overflow: hidden;
    }
    .note {
      position: absolute;
      color: white;
      font-size: 24px;
      filter: drop-shadow(0 0 5px white);
      animation: float 20s linear infinite;
    }
    @keyframes float {
      0% {
        transform: translate(0, 0) rotate(0deg);
        opacity: 1;
      }
      100% {
        transform: translate(-200px, -1000px) rotate(360deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <script>
    const notes = ['\u266B', '\u266A', '\u266C', '\u2669', '\uD834\uDD1E'];
    for (let i = 0; i < 100; i++) {
      const note = document.createElement('div');
      note.className = 'note';
      note.style.left = Math.random() * window.innerWidth + 'px';
      note.style.top = Math.random() * window.innerHeight + 'px';
      note.style.fontSize = (16 + Math.random() * 32) + 'px';
      note.style.animationDuration = (10 + Math.random() * 20) + 's';
      note.textContent = notes[Math.floor(Math.random() * notes.length)];
      document.body.appendChild(note);
    }
  </script>
</body>
</html>
