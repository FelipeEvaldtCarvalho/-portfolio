<template>
  <div class="container">
        <h2>
          <span class="hoverable">O</span>
          <span class="hoverable">l</span>
          <span class="hoverable">á</span>
          <span class="hoverable">,</span>
          <span class="hoverable"> m</span>
          <span class="hoverable">e</span>
          <span class="hoverable"> c</span>
          <span class="hoverable">h</span>
          <span class="hoverable">a</span>
          <span class="hoverable">m</span>
          <span class="hoverable">o</span>
        </h2>

        <h1>Felipe Carvalho,</h1>
        
        <h2>
            <span class="hoverable">s</span>
            <span class="hoverable">o</span>
            <span class="hoverable">u</span>
            <span class="hoverable"> D</span>
            <span class="hoverable">e</span>
            <span class="hoverable">s</span>
            <span class="hoverable">e</span>
            <span class="hoverable">n</span>
            <span class="hoverable">v</span>
            <span class="hoverable">o</span>
            <span class="hoverable">l</span>
            <span class="hoverable">v</span>
            <span class="hoverable">e</span>
            <span class="hoverable">d</span>
            <span class="hoverable">o</span>
            <span class="hoverable">r</span>
            <span class="hoverable"> W</span>
            <span class="hoverable">e</span>
            <span class="hoverable">b</span>
            <span class="hoverable">.</span>
        </h2>
      <ion-icon name="chevron-down-outline"></ion-icon>
  </div>
</template>

<script>
export default {
    name: "HelloComponent",

}
</script>

<style scoped>

h1, h2{
  font-family: 'Montserrat', sans-serif;
  
}

h2{
    font-size: 2.5rem;
    letter-spacing: 5px;
    color: white;
}
h1{
    font-size: 5.5rem;
    letter-spacing: 10px;
    color: #4cd7a9;
}
.container{
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin: 0 190px;
    padding-bottom: 190px;
}
ion-icon{
    font-size: 40px;
    position: absolute;
    bottom: 0;
    left: 50%;
    color: gray;

}


</style>