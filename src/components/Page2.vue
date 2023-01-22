<template>
    <div class="container-main">
        <div class="title-container">
            <span>Simulação</span>
        </div>

        <div class="back-button" v-on:click="startChangeTab()">
            <img src="../assets/img/arrow.png"/>
        </div>
        <div class="container-simulation">
            <div class="icon-x" v-on:click="clickCancel()">
                <img src="../assets/img/close.png" />
            </div>
            <span class="text-title-options">Selecione as opções</span>
            <div class="options-one">
                <div class="dominante">
                    <h3>Dominante</h3>
                    <div id="mendel-one" @click="clickCat(1)">
                        <span>A1A1</span>
                    </div>
                    <div id="mendel-two" @click="clickCat(2)">
                        <span>B1B1</span>
                    </div>
                </div>
            </div>
            <div class="divider"></div>
            <div class="options-two">
                <div class="dominante">
                    <h3>Recessivo</h3>
                    <div id="mendel-one-a2" @click="clickCat(3)">
                        <span>A2A2</span>
                    </div>
                    <div id="mendel-two-b2" @click="clickCat(4)">
                        <span>B2B2</span>
                    </div>
                </div>
            </div>
        </div>
        <div class="button-simulation" v-on:click="simulation()">
            <img src="../assets/img/simulacao.png" />
        </div>
        <LeiOne v-bind:display="displayLeiOne" v-on:update="displayLeiOne = $event" @changeTab="changeTab" @closeArguments="closeArguments"/>
        <LeiTwo v-bind:display="displayLeiTwo" v-on:update="displayLeiTwo = $event" @changeTab="changeTab"  @closeArguments="closeArguments" />
        <Alert ref="alert"></Alert>
    </div>
</template>

<script>
import Alert from '../components/Alert.vue'
import LeiOne from '../components/LeiOne.vue'
import LeiTwo from '../components/LeiTwo.vue'

export default {
    data() {
        return {
            op: 0,
            op1: 1,
            op2: 2,
            op3: 3,
            leiOne: 0,
            leiTwo: 0,
            displayLeiOne: false,
            displayLeiTwo: false,
        }
    },
    props: {

    },
    components: {
        Alert,
        LeiOne,
        LeiTwo
    },
    methods: {
        changeTab() {
            if (this.leiOne == 1 && this.leiTwo == 0) {
                this.$emit('changeTab', 'explication-one');
            } else if(this.leiOne == 1 && this.leiTwo == 1){
                this.$emit('changeTab', 'explication-two');
            }

        },
        startChangeTab(){
            this.$emit('changeTab', 'start-screen');
            this.closeArguments();
        },
        clickCat(number) {

            if(this.leiOne == 1 && number == 1 && this.leiTwo == 0 || number == 3 && this.leiTwo == 0 && this.leiOne != 0){
                this.message("Você já selecionou essa opção", "danger")
                return;
            }

            if (this.leiOne == 0 || this.leiTwo == 0) {
                if (number == 1) {
                    document.getElementById('mendel-one').style.backgroundColor = '#1B1A17';
                    document.getElementById('mendel-one-a2').style.backgroundColor = '#1B1A17';


                    this.message("Você selecionou as duas primeiras opções", "sucess");

                    this.leiOne = 1;


                } else if (number == 2 && this.leiOne == 1) {
                    document.getElementById('mendel-two').style.backgroundColor = '#1B1A17';
                    document.getElementById('mendel-two-b2').style.backgroundColor = '#1B1A17';

                    this.message("Você selecionou as duas segundas opções", "sucess")

                    this.leiTwo = 1;
                } else if (number == 3) {
                    this.message("Você não pode escolher a segunda opção primeiro", "danger")
                } else if (number == 4) {
                    this.message("Você não pode escolher a segunda opção primeiro", "danger")
                } else if (number == 2 && this.leiOne == 0) {
                    this.message("Você não pode escolher a segunda linha primeiro", "danger")
                }
            } else {
                this.message("Você já selecionou todas as opções", "danger");
            }

        },

        clickCancel() {
            this.leiOne = 0;
            this.leiTwo = 0;
            document.getElementById('mendel-one').style.backgroundColor = '#252525';
            document.getElementById('mendel-one-a2').style.backgroundColor = '#252525';

            document.getElementById('mendel-two').style.backgroundColor = '#252525';
            document.getElementById('mendel-two-b2').style.backgroundColor = '#252525';

            this.message("Você apagou todas as opções", "sucess")
        },
        simulation() {

            console.log(this.leiOne ,this.leiTwo)
            if (this.leiOne == 0 && this.leiTwo == 0) {
                this.message("Você só pode simular caso escolha alguma opção", "danger")
            } else if (this.leiOne == 1 && this.leiTwo == 0 ) {
                this.displayLeiOne = true
            } else if (this.leiOne == 1 && this.leiTwo == 1) {
                this.displayLeiTwo = true
            }
        },
        closeArguments(){
            this.leiOne = 0;
            this.leiTwo = 0;

            document.getElementById('mendel-one').style.backgroundColor = '#252525';
            document.getElementById('mendel-one-a2').style.backgroundColor = '#252525';

            document.getElementById('mendel-two').style.backgroundColor = '#252525';
            document.getElementById('mendel-two-b2').style.backgroundColor = '#252525';
        },
        message(text, status) {
            this.$refs.alert.message(text, status);
        },
    },
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
    left: 19%;
    width: 100%;
    font-family: 'Roboto', sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 24px;
    line-height: 29px;
    text-align: center;

    color: #00C897;
}

.container-simulation {
    position: relative;
    top: 17%;
    margin-left: auto;
    margin-right: auto;
    width: 1000px;
    height: 450px;

}

.text-title-options {
    position: relative;
    top: -10px;
    left: 396px;
    font-family: 'Roboto', sans-serif;
    font-style: normal;
    font-weight: 400;
    font-size: 22px;
    line-height: 29px;
    text-align: center;

    color: #fff;
}

.divider {
    position: relative;
    bottom: 60px;
    margin-left: auto;
    margin-right: auto;
    width: 2px;
    height: 300px;
    background-color: #FFD365;
}

.dominante {
    position: relative;
    max-width: fit-content;
    top: 80px;
    left: 120px;
}

.dominante h3 {
    position: relative;
    bottom: 40px;
    left: 106px;
    font-family: 'Roboto', sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 16px;
    line-height: 19px;

    max-width: fit-content;
    color: #fff;

}

.dominante span {
    font-family: 'Roboto', sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 16px;
    line-height: 19px;

    text-align: center;
    color: #fff;

}


.dominante div {
    width: 280px;
    height: 50px;
    display: flex;
    align-items: center;
    text-align: center;
    justify-content: center;
    margin-bottom: 20px;
    border-bottom: 1px solid #fff;
    cursor: pointer;
}

.options-two {
    position: relative;
    max-width: fit-content;
    bottom: 459px;
    left: 480px;
}

.dominante div:hover {
    transition: 0.5s;
    background-color: #1B1A17;
}

.icon-x {
    position: absolute;
    right: 10px;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    cursor: pointer;
    background-color: #019267;
}

.icon-x img {
    position: relative;
    left: 13px;
    top: 13px;
    width: 14px;
    height: 14px;
}

.icon-x:hover {
    transition: 0.2s;
    background-color: #027553;
}

.button-simulation {
    position: relative;
    width: 60px;
    height: 60px;
    background-color: #019267;
    border-radius: 50%;
    top: 15%;
    left: 93%;
    cursor: pointer;
}

.button-simulation img {
    position: relative;
    top: 15px;
    left: 15px;
    width: 30px;
    height: auto;
}
.button-simulation:hover {
    transition: 0.2s;
    background-color: #027553;
}

.back-button {
    position: absolute;
    left: 60px;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    cursor: pointer;
    background-color: #019267;
}

.back-button img {
    position: relative;
    left: 13px;
    top: 11px;
    width: 16px;
    height: 16px;
}

.back-button:hover {
    transition: 0.2s;
    background-color: #027553;
}
</style>