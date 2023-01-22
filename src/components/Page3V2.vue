<template>
    <div class="container-main">
        <div class="title-container">
            <span>Explicação</span>
        </div>

        <div class="img-container">
            <img src="../assets/img/mendel2.jpeg" />

            <p class="text">

                A segunda lei de Mendel, também <br />
                conhecida como lei da segregação <br />
                independente, diz que cada par de <br />
                alelos segregam-se de maneira <br />
                independente de outros pares de <br />
                alelos, durante a formação dos <br />
                gametas. Ela foi formulada com base <br />
                em análises da herança de duas ou <br />
                mais características acompanhadas <br />
                ao mesmo tempo. De forma <br />
                simplificada, Gregor Mendel foi capaz <br />
                de notar que ao cruzar uma ervilha de<br />
                cor amarela e textura lisa com uma <br />
                verde e rugosa, pode nascer uma <br />
                amarela rugosa. Ou seja, a <br />
                característica cor não depende da <br />
                característica textura.

            </p>
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
    left: 45%;
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

.buttons:hover {
    transition: 0.2s;
    background-color: #307e30;
}
</style>