<template>
    <ul>
        <li><a href="https://github.com/FelipeEvaldtCarvalho/" target="blank"><ion-icon name="logo-github"></ion-icon></a></li>
        <li><a href="https://www.linkedin.com/in/felipe-evaldt-carvalho-9ab1461aa/" target="blank"><ion-icon name="logo-linkedin"></ion-icon></a></li>
        <li><a href="https://wa.me/5551993871466" target="blank"><ion-icon name="logo-whatsapp"></ion-icon></a></li>
        <div class="line"></div>
    </ul>
</template>

<script>
export default {
    name: "LateralIconsComponent",

}
</script>

<style scoped>
.line{
    height: 200px;
    width: 1px;
    border-right: 2px solid gray;
}
ul{
    position: fixed;
    bottom: 0;
    left: 50px;
    display: flex;
    flex-direction: column;
    align-items: center;
    list-style: none;
    height: 350px;
    width: 50px;
    justify-content: space-between;
}
li a{
    color: gray;
    font-size: 30px;
    transition: 1s;
}
li a :hover{
    color: #4cd7a9;
    font-size: 30px;
    position: relative;
    top: -5px;
}

</style>