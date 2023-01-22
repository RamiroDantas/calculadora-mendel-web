<template>
    <div class="container-main">
        <div class="title-container">
            <img class="img-title" src="../assets/img/Icon-title.png" />
            <span>Calculadora de Mendel</span>
        </div>
        <img class="img-molecula" src="../assets/img/molecular.png" />

        <div class="icon-if">
            <img class="img-if" src="../assets/img/ImageIf.png" />
        </div>

        <div class="init-simulation" v-on:click="changeTab()">
            <span>Iniciar Simulação</span>
        </div>

        <div class="button-infos" v-on:click="infoChangeTab()">
            <img class="img-info" src="../assets/img/i.png"/>
        </div>
    </div>
</template>

<script>
export default {
    props: {
      
    },
    methods: {
        changeTab() {
            this.$emit('changeTab', 'simulation-screen');
        },
        infoChangeTab(){
            this.$emit('changeTab', 'about-me');
        }
    }
}

</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300&display=swap');
.container-main {
    width: 100vw;
    height: 100vh;
}

.img-molecula {
    position: relative;
    top: 0px;
    left: 15%;
    width: 40%;
    height: auto;
}

.img-title {
    position: relative;
    width:  50px;
    height: auto;
}

.title-container{
    position: relative;
    top: 30px;
    margin-left: auto;
    margin-right: auto;
    width: 19%;
}
.title-container span{
    position: relative;
    bottom: 20px;
    left: 5px;
    font-family: 'Roboto', sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 29px;
    text-align: center;

    color: #00C897;
}

.init-simulation{
    position: relative;
    left: 43%;
    bottom: 32%;
    width: 220px;
    height: 50px;
    border-radius: 0px 20px 20px 20px;
    background-color: #019267;
    cursor: pointer;
    box-shadow: 2px 2px 1px rgba(0, 0, 0, 0.25);
}

.init-simulation:hover{
    transition: 0.2s;
    background-color: #027c58
}
.init-simulation span {
    position: relative;
    top: 15px;
    left: 56px;
    font-family: Arial, Helvetica, sans-serif;
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 18px;
    text-align: center;

    color: #FFFFFF;
}

.img-if { 
    position: relative;
    width: 110px;
    height: auto;
}

.icon-if {
    position: relative;
    bottom: 55%;
    left: 90%;
}

.button-infos {
    position: absolute;
    width: 30px;
    height: 30px;
    bottom: 5%;
    right: 2%;
    cursor: pointer;
    background-color: #019267;
    border-radius: 50%;
}

.img-info {
    width: 30px;
    height: auto;
}
.button-infos:hover{
    transition: 0.2s;
    background-color: #027c58
}
</style>