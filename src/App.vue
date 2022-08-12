<template>
  <div>
    <NavComponent />
    <LateralIconsComponent />
    <HelloComponent />
    <AboutComponent />
    <WorkComponent />
    <ContactComponent />
    <FooterComponent />
  </div>
</template>
<script>
import NavComponent from "./components/NavComponent.vue"
import LateralIconsComponent from "./components/LateralIconsComponent.vue"
import HelloComponent from "./components/HelloComponent.vue"
import AboutComponent from "./components/AboutComponent.vue"
import WorkComponent from "./components/WorkComponent.vue"
import ContactComponent from "./components/ContactComponent.vue"
import FooterComponent from "./components/FooterComponent.vue"


export default {
  name: 'App',
  components: {
    NavComponent,
    LateralIconsComponent,
    HelloComponent,
    AboutComponent,
    WorkComponent,
    ContactComponent,
    FooterComponent,
}
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@200&family=Play&display=swap');
*{
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
body{
  background-color: #242424;
}
html {
  scroll-behavior: smooth;
}
::-webkit-scrollbar {
  width: 8px;
} 
   
::-webkit-scrollbar-thumb {  
width: 6px; 
background-color: gray;
border-radius: 5px;
transition: 0.6s;
}
::-webkit-scrollbar-thumb:hover {
  background: #4cd7a9;
}
.hoverable{
    transition: .3s;
}
.hoverable:hover{
    color: #4cd7a9;
}
.btn{
    color: #4cd7a9;
    background-color: transparent;
    border: 2px solid #4cd7a9;
    border-radius: 30px;
    padding: 5px 30px;
    transition: .4s;
    font-family: 'Play', sans-serif;
    font-size: 20px;
    cursor: pointer;
}
.btn:hover{
    background-color: rgb(64, 64, 64, 60%);
}
</style>
