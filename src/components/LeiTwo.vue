<template>
    <div class="dialog-box" v-bind:class="{ 'display-dialog-box': display }" v-on:click="close">
        <div class="dialog-box__container">
            <span class="dialog-box__container__title">Processo</span>

            <span class="class-lei-one">2-Lei de Mendel</span>

            <div class="container-lei">
                <div class="part1-container">
                    <div class="ball-lei p1">
                    </div>
                    <span class="text1">A1A1B1B1</span>
                    <div class="ball-lei p2">
                    </div>
                    <span class="text2">A2A2B2B2</span>
                    <div class="bar-x x1">X</div>
                    <div class="ball-lei p3">
                    </div>
                    <div class="bar-x x2">X</div>
                    <span class="text3">A1A2B2B1</span>
                    <div class="ball-lei p4">
                    </div>
                    <span class="text4">A1A2B2B1</span>
                </div>
                <div class="divider"></div>
                <div class="ball-lei p5">
                </div>
                <span class="text5">A1A1B1B1</span>
                <div class="ball-lei p6">
                </div>
                <span class="text6" >A1A1B1B2</span>
                <div class="ball-lei p7">
                </div>
                <span class="text7">A1A2B1B1</span>
                <div class="ball-lei p8">
                </div>
                <span class="text8">A1A2B1B2</span>
                <div class="ball-lei p9">
                </div>
                <span class="text9">A1A1B1B2</span>
                <div class="ball-lei p10">
                </div>
                <span class="text10">A1A1B2B2</span>
                <div class="ball-lei p11">
                </div>
                <span class="text11">A1A2B1B2</span>
                <div class="ball-lei p12">
                </div>
                <span class="text12">A1A2B2B2</span>
                <div class="ball-lei p13">
                </div>
                <span class="text13">A1A2B1B1</span>
                <div class="ball-lei p14">
                </div>
                <span class="text14">A1A2B1B2</span>
                <div class="ball-lei p15">
                </div>
                <span class="text15">A2A2B1B1</span>
                <div class="ball-lei p16">
                </div>
                <span class="text16">A2A2B1B2</span>
                <div class="ball-lei p17">
                </div>
                <span class="text17">A1A2B1B2</span>
                <div class="ball-lei p18">
                </div>
                <span class="text18">A1A2B1B2</span>
                <div class="ball-lei p19">
                </div>
                <span class="text19">A2A2B1B2</span>
                <div class="ball-lei p20">
                </div>
                <span class="text20">A2A2B2B2</span>
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
    name: "Lei Two",
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
            this.$emit('changeTab', 'explication-two');
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
    min-height: 630px;
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
    top: 61px;
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
    top: 90px;
    left: 112px;
    background-color: #1B1A17;
    width: 426px;
    height: 440px;
    border-radius: 15px;
}

.ball-lei {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background-color: #019267;
}

.container-lei span {
    position: relative;
    font-family: 'Roboto', sans-serif;
    font-style: normal;
    font-weight: 800;
    font-size: 8px;
    line-height: 12px;

    text-align: center;

    color: #FFFFFF;
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
    top: 110px;
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


.p1 {
    position: relative;
    left: 150px;
    top: 40px;
}

.p2 {
    position: relative;
    left: 250px;
    bottom: 8px;
}

.p3 {
    position: relative;
    left: 150px;
    top: 5px;
}

.p4 {
    position: relative;
    left: 250px;
    bottom: 43px;
}

.text1 {
    position: relative;
    left: 148px;
    top: 40px;
}

.text2 {
    position: relative;
    left: 247px;
    bottom: 8px;
}

.text3 {
    position: relative;
    left: 147px;
    top: 5px;
}

.text4 {
    position: relative;
    left: 247px;
    bottom: 43px;
}

.divider {
    position: absolute;
    width: 397px;
    height: 0px;
    left: 14px;
    top: 160px;

    border: 1px solid #FFFFFF;
}
.bar-x {
    width: 8px;
    height: 14px;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 800;
    font-size: 12px;
    line-height: 14px;
    /* identical to box height */

    text-align: center;

    color: #FFFFFF;
}

.x1 {
    position: absolute;
    left: 212px;
    top: 50px;
}

.x2 {
    position: absolute;
    left: 212px;
    top: 110px;
}

.part1-container{
    position: relative;
    bottom: 10px;
}

.p5 {
    position: relative;
    left: 60px;
}

.p6 {
    position: relative;
    left: 150px;
    bottom: 48px;
}
.p7 {
    position: relative;
    left: 250px;
    bottom: 96px;
}

.p8 {
    position: relative;
    left: 340px;
    bottom: 144px;
}

.p9 {
    position: relative;
    left: 60px;
    bottom: 128px;
}
.p10 {
    position: relative;
    left: 150px;
    bottom: 176px;
}

.p11 {
    position: relative;
    left: 250px;
    bottom: 224px;
}

.p12 {
    position: relative;
    left: 340px;
    bottom: 272px;
}

.p13 {
    position: relative;
    left: 60px;
    bottom: 260px;
}

.p14 {
    position: relative;
    left: 150px;
    bottom: 308px;
}

.p15 {
    position: relative;
    left: 250px;
    bottom: 356px;
}
.p16 {
    position: relative;
    left: 340px;
    bottom: 404px;
}

.p17 {
    position: relative;
    left: 60px;
    bottom: 390px;
}

.p18 {
    position: relative;
    left: 150px;
    bottom: 438px;
}
.p19 {
    position: relative;
    left: 250px;
    bottom: 486px;
}

.p20 {
    position: relative;
    left: 340px;
    bottom: 534px;
}

.text5 {
    position: relative;
    left: 57px;
}

.text6 {
    position: relative;
    left: 147px;
    bottom: 48px;
}

.text7 {
    position: relative;
    left: 247px;
    bottom: 96px;
}

.text8 {
    position: relative;
    left: 337px;
    bottom: 144px;
}

.text9 {
    position: relative;
    left: 57px;
    bottom: 128px;
}
.text10 {
    position: relative;
    left: 147px;
    bottom: 176px;
}

.text11 {
    position: relative;
    left: 247px;
    bottom: 224px;
}

.text12 {
    position: relative;
    left: 337px;
    bottom: 272px;
}

.text13 {
    position: relative;
    left: 57px;
    bottom: 260px;
}

.text14 {
    position: relative;
    left: 147px;
    bottom: 308px;
}

.text15 {
    position: relative;
    left: 247px;
    bottom: 356px;
}
.text16 {
    position: relative;
    left: 337px;
    bottom: 404px;
}

.text17 {
    position: relative;
    left: 57px;
    bottom: 390px;
}

.text18 {
    position: relative;
    left: 147px;
    bottom: 438px;
}
.text19 {
    position: relative;
    left: 247px;
    bottom: 486px;
}

.text20 {
    position: relative;
    left: 337px;
    bottom: 534px;
}
</style>