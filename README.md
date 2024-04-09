<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>Bu site daha iyi bir deneyim için çerezleri kullanır</title>
<style>
  .trollface {
    position: fixed;
    bottom: 10px;
    right: 10px;
    width: 100px;
    height: auto;
    z-index: 9999;
  }
  .sikismaButon {
    position: absolute;
  }
</style>
</head>
<body>
<h1 style="text-align: center;">Bu site daha iyi bir deneyim için çerezleri kullanır</h1>
<div style="text-align: center;">
<div id="secenekler" style="margin-top: 100px;">
    <a href="#" onclick="kabulEt()">[İzin veriyorum]</a> | <a href="#" onclick="izinVerme()">[İzin vermiyorum]</a>
</div>
</div>
<div id="sonuc" style="text-align: center;"></div>
<img src="https://i.kym-cdn.com/entries/icons/original/000/000/091/TrollFace.jpg" alt="Trollface" class="trollface">
<script>
var secenekler = document.getElementById("secenekler");
var sonuc = document.getElementById("sonuc");
var counter = 0;

function kabulEt() {
    secenekler.innerHTML = "";
    sonuc.innerHTML = "ANLAŞMAYI KABUL ETTİNİZ<br>(abi ...... yiyim abi)";
    var button = document.createElement("button");
    button.innerHTML = "Şişeye oturtturulmaktan kurtul";
    button.classList.add("sikismaButon");
    button.onclick = function() {
        counter++;
        if (counter < 20) {
            var left = Math.floor(Math.random() * (window.innerWidth - button.offsetWidth));
            var top = Math.floor(Math.random() * (window.innerHeight - button.offsetHeight));
            button.style.left = left + "px";
            button.style.top = top + "px";
        } else {
            button.innerHTML = "SONSUZA KADAR SIKIŞMA SONU";
            button.onclick = function() {
                alert("Buradan çıkış yok");
            };
        }
    };
    sonuc.appendChild(button);
}

function izinVerme() {
    secenekler.innerHTML = "";
    sonuc.innerHTML = "SEN KAZANDIN";
}
</script>
</body>
</html>
