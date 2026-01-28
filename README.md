# headshot-training-ff
<!DOCTYPE html>
<html>
<head>
  <title>FF Headshot Training</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body{
      margin:0;
      background:#0f172a;
      color:white;
      font-family:Arial;
      text-align:center;
    }
    h2{margin-top:20px;}
    #arena{
      position:relative;
      width:100%;
      height:70vh;
      background:#020617;
      overflow:hidden;
      border-top:2px solid red;
    }
    .target{
      width:60px;
      height:60px;
      background:#ef4444;
      border-radius:50%;
      position:absolute;
      top:50%;
      left:50%;
    }
    #panel{
      padding:10px;
      background:#020617;
    }
    button{
      padding:10px 20px;
      background:red;
      color:white;
      border:none;
      border-radius:5px;
      font-size:16px;
    }
  </style>
</head>
<body>

<h2>🎯 Free Fire Headshot Training</h2>

<div id="panel">
  Score: <span id="score">0</span>
  <br><br>
  <button onclick="start()">Start Training</button>
</div>

<div id="arena">
  <div class="target" id="target"></div>
</div>

<script>
let score = 0;
let playing = false;
const target = document.getElementById("target");

function move(){
  if(!playing) return;
  const x = Math.random() * (window.innerWidth - 60);
  const y = Math.random() * (window.innerHeight * 0.6);
  target.style.left = x + "px";
  target.style.top = y + "px";
}

target.onclick = ()=>{
  if(!playing) return;
  score++;
  document.getElementById("score").innerText = score;
  move();
}

function start(){
  score = 0;
  playing = true;
  document.getElementById("score").innerText = score;
  move();
  setInterval(move, 900);
}
</script>

</body>
</html>
