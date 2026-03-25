<html>
<head>
  <title>Surprise 🎁</title>
  <style>
    body {
      margin: 0;
      text-align: center;
      font-family: Arial;
      background: black;
      color: white;
      overflow: hidden;
    }

    #startBtn {
      margin-top: 20%;
      padding: 15px 30px;
      font-size: 20px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      background: gold;
    }

    #content {
      display: none;
    }

    h1 {
      margin-top: 15%;
      font-size: 30px;
      animation: glow 2s infinite alternate;
    }

    p {
      font-size: 22px;
      margin-top: 20px;
    }

    @keyframes glow {
      from { text-shadow: 0 0 10px #ff69b4; }
      to { text-shadow: 0 0 30px #ff1493; }
    }

    .flower {
      position: absolute;
      animation: fall linear infinite;
    }

    @keyframes fall {
      0% {top: -10%;}
      100% {top: 110%;}
    }

    @media (max-width: 600px){
      h1 { font-size: 35px; }
      p { font-size: 18px; }
    }
  </style>
</head>
<body>

<button id="startBtn" onclick="startSurprise()">🎁 Click for Surprise</button>

<div id="content">
  <h1>🎉 Happy Birthday Samra 🎉</h1>
  <p id="msg"></p>
</div>

<!-- Background music -->
<audio id="bgMusic" loop>
  <source src="https://www.bensound.com/bensound-music/bensound-love.mp3" type="audio/mpeg">
</audio>

<!-- Click sound -->
<audio id="clickSound" src="https://www.soundjay.com/buttons/sounds/button-3.mp3"></audio>

<script>
function startSurprise(){
  document.getElementById("clickSound").play();
  document.getElementById("bgMusic").play();

  document.body.style.background = "linear-gradient(to right, #ff9a9e, #fad0c4)";
  document.getElementById("startBtn").style.display = "none";
  document.getElementById("content").style.display = "block";

  // Typing effect
  let text = "May Allah keep you happy and bless you with a long, peaceful life. Happy Birthday, dear sister! 💖";
  let i = 0;
  function typing(){
    if(i < text.length){
      document.getElementById("msg").innerHTML += text.charAt(i);
      i++;
      setTimeout(typing, 40);
    }
  }
  typing();

  // Flowers + hearts
  const items = ["🌸","🤍","💖","💗"];

  for(let i=0; i<60; i++){
    let flower = document.createElement("div");
    flower.innerHTML = items[Math.floor(Math.random()*items.length)];
    flower.className = "flower";
    flower.style.left = Math.random()*100 + "vw";
    flower.style.fontSize = (20 + Math.random()*25) + "px";
    flower.style.animationDuration = (Math.random()*3+3)+"s";
    document.body.appendChild(flower);
  }
}
</script>

</body>
</html>
