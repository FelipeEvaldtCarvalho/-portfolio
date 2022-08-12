<template>
  <section id="contact">
      <div class="text">
                <div class="row">
                    <h1>Entre em Contato</h1>
                    <div class="line"></div>
                </div>
                <div class="content">
                    <p>
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni, minus!
                    </p>
                    <button type="button" class="btn" @click="showModal">Diga olá!</button>
                </div>
            </div>
            <ModalComponent 
                v-show="isModalVisible"
                @close="closeModal"
            />
            
  </section>
</template>

<script>
import ModalComponent from "./ModalComponent.vue"

export default{
    name: "ContactComponent",
    components: {
        ModalComponent,
    },
    data(){
        return{
            isModalVisible: false,
        }
    },
    methods:{
        showModal(){
            this.isModalVisible = true;
        },
        closeModal(){
            this.isModalVisible = false;
        },
    }
}
</script>

<style scoped>
section{
    height: calc(100vh -100px);
    padding: 150px 190px;
}
.row{
    display: flex;
    width: 65%;
    align-items: center;
    justify-content: space-between;
}
p{
font-family: 'Play', sans-serif;
font-size: 25px;
color: white;
max-width: 65%;
}
h1{
    font-family: 'Montserrat', sans-serif;
    color: #4cd7a9;
    font-size: 30px;
}
.line{
    width: 55%;
    height: 2px;
    border-top: 2px solid #4cd7a9;;
    margin: 0;
}
.content{
    display: flex;
    flex-direction: column;
    padding: 15px 0;
    margin: 15px;
}
.btn{
    width: 150px;
    margin: 80px 0;
    margin-left: 25%;
}
</style>