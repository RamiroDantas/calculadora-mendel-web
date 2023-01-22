<template>
    <div class="container-main">
        <div class="title-container">
            <span>Explicação</span>
        </div>

        <div class="img-container">
            <img src="../assets/img/mendel1.jpeg"/>
        </div>

        <p class="text">
            A primeira lei de mendel, também conhecida como lei da segregação dos fatores ou lei da <br/>
            pureza dos gametas, diz que cada característica é condicionada por um par de fatores que <br />
            se separam na formação dos gametas. Mendel deduziu isso cruzando as ervilhas, e <br />
            observou que ao longo das gerações um par de ervilhas amarelas poderia gerar uma ervilha <br/>
            verde, mas que outro par de ervilhas amarelas nunca havia gerado uma verde. Com base <br />
            nisso, observou que poderiam haver linhagens puras ou híbridas.
        </p>

        <div class="buttons" v-on:click="changeTab()">
            <span class="button-back">Início</span>
        </div>
    </div>
</template>

<script>
export default {
    props: {
      
    },
    methods: {
        changeTab() {
            this.$emit('changeTab', 'start-screen');
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

.title-container {
    position: relative;
    top: 7%;
    margin-left: auto;
    margin-right: auto;
    width: 200px;
}

.title-container span {
    position: relative;
    bottom: 20px;
    left: 18%;
    width: 100%;
    font-family: 'Roboto', sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 24px;
    line-height: 29px;
    text-align: center;

    color: #00C897;
}

.img-container {
    position: relative;
    top: 13%;
    margin-left: auto;
    margin-right: auto;
    max-width: fit-content;
}
.img-container img {
    width: 550px;
    height: auto;
}

.text {
    position: relative;
    top: 20%;
    right: 0.2%;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 700;
    font-size: 14px;
    line-height: 16px;
    text-align: center;

    color: #FFFFFF;
}


.buttons {
    position: relative;
    top: 30%;
    margin-left: auto;
    margin-right: auto;
    width: 173px;
    height: 51px;
    cursor: pointer;
    
    background: #379237;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    border-radius: 0px 10px 10px 10px;
}

.button-back {
    position: relative;
    top: 15px;
    left: 70px;
    font-family: 'Roboto', sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 14px;
    line-height: 15px;
    cursor: pointer;

    color: #FFFFFF;
}

.buttons:hover{
    transition: 0.2s;
    background-color: #307e30;
}

</style>