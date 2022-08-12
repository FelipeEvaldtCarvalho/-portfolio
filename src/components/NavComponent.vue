<template>
    <nav id="navbar">
        <a href="#"><ion-icon name="rocket-outline"></ion-icon></a>
        <ul>
            <li><a href="#about">Sobre</a></li>
            <li><a href="#work">Trabalhos</a></li>
            <li><a href="#contact">Contato</a></li>
            <li><button class="btn">Resumo</button></li>
        </ul>
    </nav>
</template>
<script>
export default {
    name: "NavComponent"
}

var prevScrollpos = window.pageYOffset;
window.onscroll = function() {
var currentScrollPos = window.pageYOffset;
  if (prevScrollpos > currentScrollPos) {
    document.getElementById("navbar").style.top = "0";
  } else {
    document.getElementById("navbar").style.top = "-100px";
  }
  prevScrollpos = currentScrollPos;
}

</script>
<style scoped>
ul{
    list-style-type: none;
    display: flex;
    align-items: center;
}
li{
    margin-left: 60px;
}
li a{
    text-decoration: none;
    color: white;
    font-size: 20px;
    font-family: 'Play', sans-serif;
    transition: .4s;
}
li a:hover{
    color: #4cd7a9;
}
ion-icon{
    color: #4cd7a9;
    font-size: 50px;
}
ion-icon:hover{
    animation: shake 0.5s;
    animation-iteration-count: infinite;
}

@keyframes shake {
  0% { transform: translate(1px, 1px) rotate(0deg); }
  10% { transform: translate(-1px, -2px) rotate(-1deg); }
  20% { transform: translate(-3px, 0px) rotate(1deg); }
  30% { transform: translate(3px, 2px) rotate(0deg); }
  40% { transform: translate(1px, -1px) rotate(1deg); }
  50% { transform: translate(-1px, 2px) rotate(-1deg); }
  60% { transform: translate(-3px, 1px) rotate(0deg); }
  70% { transform: translate(3px, 1px) rotate(-1deg); }
  80% { transform: translate(-1px, -1px) rotate(1deg); }
  90% { transform: translate(1px, 2px) rotate(0deg); }
  100% { transform: translate(1px, -2px) rotate(-1deg); }
}
#navbar{
    transition: top 0.3s;
    z-index: 10000;
    background: rgb(36,36,36);
    background: linear-gradient(180deg, rgba(36,36,36,1) 0%, rgba(36,36,36,1) 48%, rgba(36,36,36,0) 100%);
}
nav{
    display: flex;
    align-items: center;
    padding: 20px 40px;
    justify-content: space-between;
    position: fixed;
    width: 100%;
}

</style>