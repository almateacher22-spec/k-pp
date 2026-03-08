<!DOCTYPE html>
<html>
<head>
<title>Command Prompt</title>
<style>
body{
  background:black;
  color:#00ff00;
  font-family:Consolas, monospace;
  padding:10px;
  font-size:14px;
  overflow:hidden;
}
#cursor{
  display:inline-block;
  width:10px;
  background:#00ff00;
  margin-left:4px;
  animation:blink 1s infinite;
}
@keyframes blink{
  50%{opacity:0;}
}
</style>
</head>
<body>

<div id="cmd"></div><span id="cursor"></span>

<script>
let cmd = document.getElementById("cmd");

// Függvény véletlenszerű fájlokhoz
function randomFile(){
  let names=["system","data","config","backup","photo","video","secret","temp","cache"];
  let ext=[".dat",".sys",".txt",".log",".bin",".dll"];
  return "C:\\Users\\User\\"+names[Math.floor(Math.random()*names.length)]+"\\file"+Math.floor(Math.random()*9999)+ext[Math.floor(Math.random()*ext.length)];
}

// 1. CMD kimenet szimulálása
let count = 0;
function scan(){
  if(count < 300){  // 300 sor gyors pörgés
    let line = document.createElement("div");
    line.textContent = "C:\\Users\\User> " + randomFile();
    cmd.appendChild(line);
    window.scrollTo(0,document.body.scrollHeight);
    count++;
    setTimeout(scan,10); // gyorsabb sebesség, mint a valódi CMD
  }else{
    setTimeout(uploadPhase,1000); // kis szünet a feltöltés előtt
  }
}

// 2. Feltöltés szimuláció
function uploadPhase(){
  let lines=[
    "C:\\Users\\User> Uploading data...",
    "C:\\Users\\User> ...",
    "C:\\Users\\User> ...",
    "C:\\Users\\User> Data uploaded."
  ];
  let i=0;
  function next(){
    if(i<lines.length){
      let div=document.createElement("div");
      div.textContent=lines[i];
      cmd.appendChild(div);
      window.scrollTo(0,document.body.scrollHeight);
      i++;
      setTimeout(next,400); // lassabb, mint a gyors pörgő részek
    }
  }
  next();
}

scan();
</script>

</body>
</html>
