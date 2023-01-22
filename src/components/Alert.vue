<template>
    <div class="alert" v-bind:class="[status, {'display-alert': display}]">
      <p class="alert__message">{{ text }}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: "Alert",
    data () {
      return {
        text: "",
        status: "sucess",
        display: false
      }
    },
    methods: {
      message (text, status, time = 2500) {
        this.text = text
        this.status = status
        this.display = true
        setTimeout(() => {this.display = false}, time)
      }
    }
  }
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300&display=swap');
  .alert {
    position: fixed;
    top: 0px;
    left: 50%;
    margin: 0;
    padding: 12px 10px 12px 12px;
    transform: translateX(-50%);
    border-radius: 4px;
    user-select: none;
    white-space: nowrap;
    box-shadow: 0px 0px 10px 0px rgba(32, 32, 32, 0.5);
    opacity: 0;
    visibility: hidden;
    transition: all 0.2s;
    z-index: 10;
  }
  
  .alert__message {
    position: relative;
    display: block;
    font-family: 'Roboto', sans-serif;
    font-size: 16px;
    color: #fff;
  }
  
  .alert__close {
    position: absolute;
    display: block;
    top: 6px;
    right: 8px;
    width: 32px;
    height: 32px;
    margin: 0;
    padding: 0;
    border: none;
    border-radius: 50%;
    outline: none;
    background: none;
    overflow: hidden;
    transition: background-color 0.2s;
    cursor: pointer;
  }
  
  .alert__close i {
    position: absolute;
    display: block;
    top: 1px;
    left: 4px;
    margin: 0;
    padding: 0;
    font-size: 24px;
    color: #fff;
  }
  
  .display-alert {
    top: 24px;
    opacity: 1;
    visibility: visible;
  }
  
  .sucess {
    background-color: #4caf50;
  }
  
  .sucess .alert__close:hover {
    background-color: #3c9f40;
  }
  
  .sucess .alert__close:active {
    background-color: #2c8f30;
  }
  
  .danger {
    background-color: #f44336;
  }
  
  .danger .alert__close:hover {
    background-color: #e43326;
  }
  
  .danger .alert__close:active {
    background-color: #d42316;
  }
  </style>