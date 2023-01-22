<template>
    <div class="dialog-box" v-bind:class="{ 'display-dialog-box': display }" v-on:click="close">
        <div class="dialog-box__container">
            <span class="dialog-box__container__title">Processo</span>

            <span class="class-lei-one">1-Lei de Mendel</span>

            <div class="container-lei">
                <div class="ball-lei p1">
                    <span>A1A1</span>
                </div>
                <div class="bar1"></div>
                <div class="bar2"></div>
                <div class="bar3"></div>
                <div class="ball-lei p2">
                    <span>A2A2</span>
                </div>
                <div class="bar4"></div>
                <div class="bar5"></div>
                <div class="bar6"></div>
                <div class="ball-lei p3">
                    <span>A1A2</span>
                </div>
                <div class="bar7"></div>
                <div class="bar8"></div>
                <div class="ball-lei p4">
                    <span>A1A2</span>
                </div>
                <div class="bar9"></div>
                <div class="bar10"></div>
                <div class="bar11"></div>
                <div class="ball-lei p5">
                    <span>A1A2</span>
                </div>
                <div class="ball-lei p6">
                    <span>A1A2</span>
                </div>
                <div class="ball-lei p7">
                    <span>A1A1</span>
                </div>
                <div class="ball-lei p8">
                    <span>A1A1</span>
                </div>
                <div class="ball-lei p9">
                    <span>A1A1</span>
                </div>
                <div class="ball-lei p10">
                    <span>A2A2</span>
                </div>
            </div>

            <div class="button-form">
                <div class="buttons"  v-on:click="closeDisplay()">
                    <span class="button-back">Voltar</span>
                </div>
                <div class="buttons" v-on:click="changeTab()">
                    <span class="span-button">Explicação</span>
                </div>
            </div>
            <div class="dialog-box__container__form">
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Lei One",
    data() {
        return {
        }
    },
    props: ["display", "displayForm"],
    methods: {
        close(event) {
            if (event.target.classList[0] == "dialog-box" && !this.displayForm) {
                this.$emit("update", false)
            }
        },
        closeDisplay(){
            this.$emit("update", false)
        },
        changeTab() {
          
            this.$emit('changeTab', 'explication-one');
            this.closeDisplay();
            this.$emit('closeArguments');
        },
    }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300&display=swap');

.dialog-box {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    margin: 0;
    padding: 0;
    opacity: 0;
    visibility: hidden;
    background-color: rgba(16, 16, 16, 0.3);
    transition: opacity 0.2s, visibility 0.2s;
    z-index: 8;
    display: grid;
    justify-content: center;
    align-content: center;
}

.dialog-box__container {
    position: relative;
    min-width: 650px;
    min-height: 550px;
    padding-bottom: 45px;
    border-radius: 4px;
    background-color: #252525;
}

.dialog-box__container__close {
    position: absolute;
    display: block;
    top: 20px;
    right: 30px;
    width: 32px;
    height: 32px;
    margin: 0;
    padding: 0;
    border: none;
    border-radius: 50%;
    outline: none;
    background-color: #f4f4f4;
    overflow: hidden;
    transition: background-color 0.2s;
    cursor: pointer;
}

.dialog-box__container__close:hover {
    background-color: #e4e4e4;
}

.dialog-box__container__close:active {
    background-color: #d4d4d4;
}

.dialog-box__container__close i {
    position: absolute;
    display: block;
    top: 1px;
    left: 4.5px;
    margin: 0;
    padding: 0;
    font-size: 24px;
    color: #5B73B6;
}

.dialog-box__container__title {
    position: relative;
    top: 21px;
    left: 285px;
    margin: 0;
    padding: 0;
    margin-right: 72px;
    font-family: 'Roboto', sans-serif;
    font-size: 20px;
    font-weight: 600;
    color: #fff;
    user-select: none;
}

.dialog-box__container__form {
    position: relative;
    top: 30px;
    margin: 0;
    padding: 30px 30px 20px 30px;
}

.display-dialog-box {
    opacity: 1;
    visibility: visible;
}

.dialog-box__container::-webkit-scrollbar {
    width: 8px;
    height: 8px;
}

.dialog-box__container::-webkit-scrollbar-track {
    background: #fff;
}

.dialog-box__container::-webkit-scrollbar-thumb {
    border-radius: 4px;
    background: #ddd;
}

.dialog-box__container::-webkit-scrollbar-thumb:hover {
    background: #ccc;
}

.dialog-box__container::-webkit-scrollbar-corner {
    background: #fff;
}

.class-lei-one {
    position: relative;
    top: 71px;
    right: 120px;
    margin: 0;
    padding: 0;

    font-family: 'Roboto', sans-serif;
    font-size: 14px;
    font-weight: 600;
    color: #fff;
    user-select: none;
}

.container-lei { 
    position: relative;
    top: 100px;
    left: 112px;
    background-color: #1B1A17;
    width: 426px;
    height: 297px;
    border-radius: 15px;
}

.ball-lei {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background-color: #019267;
}

.ball-lei span {
    position: relative;
    top: 3px;
    left: 5.5px;
    font-family: 'Roboto', sans-serif;
    font-style: normal;
    font-weight: 800;
    font-size: 8px;
    line-height: 12px;

    text-align: center;

    color: #FFFFFF;
}


.p1 {
    position: relative;
    left: 120px;
    top: 40px;
}

.p2 {
    position: relative;
    left: 275px;
    top: 10px;
}

.p3 {
    position: relative;
    top: 60px;
    left: 5px;
}

.p4 {
    position: relative;
    top: 30px;
    left: 120px;
    
}

.p5 {
    position: relative;
    left: 275px;
}

.p6 {
    position: relative;
    left: 390px;
    bottom: 30px;
}

.p7 {
    position: relative;
    left: 5px;
    top: 18px;
}

.p8 {
    position: relative;
    bottom: 12px;
    left: 120px;
}

.p9 {
    position: relative;
    bottom: 42px;
    left: 275px;
}

.p10 {
    position: relative;
    bottom: 72px;
    left: 390px;
}

.bar1{ 
    position: absolute;
    top: 55px;
    left: 150px;
    width: 126px;
    height: 0px;

    border: 1px solid #FFFFFF;
}
.bar2{ 
    position: absolute;
    top: 70px;
    left: 134px;
    width: 0;
    height: 50px;

    border: 1px solid #FFFFFF;
}
.bar3{ 
    position: absolute;
    top: 70px;
    left: 289px;
    width: 0;
    height: 50px;

    border: 1px solid #FFFFFF;
}

.bar4 { 
    position: absolute;
    top: 135px;
    left: 150px;
    width: 126px;
    height: 0px;

    border: 1px solid #FFFFFF;
}

.bar5 {
    position: absolute;
    top: 135px;
    left: 29px;
    width: 100px;
    height: 0px;

    border: 1px solid #FFFFFF;
}
.bar6 {
    position: absolute;
    top: 135px;
    left: 305px;
    width: 100px;
    height: 0px;

    border: 1px solid #FFFFFF;
}

.bar7 { 
    position: absolute;
    top: 150px;
    left: 134px;
    width: 0;
    height: 50px;

    border: 1px solid #FFFFFF;
}

.bar8 { 
    position: absolute;
    top: 150px;
    left: 289px;
    width: 0;
    height: 50px;

    border: 1px solid #FFFFFF;
}
.bar9 { 
    position: absolute;
    top: 213px;
    left: 150px;
    width: 126px;
    height: 0px;

    border: 1px solid #FFFFFF;
}

.bar10 {
    position: absolute;
    top: 213px;
    left: 29px;
    width: 100px;
    height: 0px;

    border: 1px solid #FFFFFF;
}
.bar11 {
    position: absolute;
    top: 213px;
    left: 305px;
    width: 100px;
    height: 0px;

    border: 1px solid #FFFFFF;
}
.buttons {
    position: relative;
    width: 123px;
    height: 41px;
    margin-left: 100px;
    cursor: pointer;
    
    background: #379237;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    border-radius: 0px 10px 10px 10px;
}

.button-form{
    position: relative;
    top: 140px;
    left: 50px;
    width: fit-content;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.button-back {
    position: relative;
    top: 10px;
    left: 45px;
    font-family: 'Roboto', sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 12px;
    line-height: 15px;
    cursor: pointer;

    color: #FFFFFF;
}

.span-button {
    position: relative;
    top: 10px;
    left: 32px;
    font-family: 'Roboto', sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 12px;
    line-height: 15px;

    cursor: pointer;
    color: #FFFFFF;
}

.buttons:hover{
    transition: 0.2s;
    background-color: #307e30;
}
</style>