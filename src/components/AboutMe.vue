<template>
    <div class="container-main">
        <div class="title-container">
            <span>AboutMe</span>
        </div>
        <div class="perfils-container">
            <span>- EQUIPE:</span>
            <div class="img-equipe">
                <img src="../assets/img/MaraBastos.jpeg"/>
                <span>Mara Bastos</span>
            </div>
            <div class="img-equipe">
                <img src="../assets/img/DanielleCosta.jpeg" />
                <span>Danielle Costa</span>
            </div>
            <div class="img-equipe">
                <img src="../assets/img/BiancaSouza.jpeg"/>
                <span>Bianca Souza</span>
            </div>
        </div>

        <div class="fonts-project">
            <span class="title-container-fonts ">- Fontes: </span>
            <a href="https://www.todamateria.com.br/primeira-lei-de-mendel/" target="_blank">
                <span>Primeira Lei de Mendel</span>
            </a>
            <a href="https://www.todamateria.com.br/segunda-lei-de-mendel/" target="_blank">
                <span>Segunda Lei de Mendel</span>
            </a>
        </div>
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
    top: 40px;
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
    top: 12.3%;
    display: flex;
    margin-left: auto;
    margin-right: auto;
    right: 6%;
    justify-content: space-between;
    max-width: fit-content;
}

.img-container img {
    width: 300px;
    height: auto;
}

.text {
    position: relative;
    margin-top: 80px;
    margin-left: 40px;
    left: 20%;
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
    top: 19%;
    left: 44%;
    width: 173px;
    height: 51px;
    cursor: pointer;

    background-color: #019267;
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

.buttons:hover {
    transition: 0.2s;
    background-color: #027c58;
}

.perfils-container{
    position: relative;
    top: 100px;
    left: 23.7%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    max-width: fit-content;

}
.perfils-container span {
    position: absolute;
    top: -50px;

    font-family: 'Roboto';
    font-style: normal;
    font-weight: 700;
    font-size: 18px;
    line-height: 16px;
    text-align: center;

    color: #FFFFFF;
}


.img-equipe {
    width: 200px;
    height: 400px;
    margin-left: 40px;
    display: flex;
}
.img-equipe img {
    width: 140px;
    height: 200px;
    object-fit: cover;
    border: 2px solid #027c58;
}

.img-equipe span {
    position: relative;
    top: 220px;
    right: 100px;
    display: flex;
    max-width: fit-content;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 700;
    font-size: 14px;
    line-height: 16px;
    text-align: center;

    color: #FFFFFF;
}

.fonts-project {
    position: relative;
    top: 80px;
    left: 23.7%;
    display: flex;
    align-items: center;
    justify-content: space-between;

    max-width: fit-content;
}

.title-container-fonts {
    position: absolute;
    top: -50px;

    font-family: 'Roboto';
    font-style: normal;
    font-weight: 700;
    font-size: 18px;
    line-height: 16px;
    text-align: center;

    color: #FFFFFF;
    
}


.fonts-project a span{
    margin-left: 30px;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 700;
    font-size: 14px;
    line-height: 16px;
    text-align: center;
    text-decoration: underline;


    color:  #FFD365;
}

</style>