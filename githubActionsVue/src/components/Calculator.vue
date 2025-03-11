<template>
    <div class="calculator">
      <h1>Teclat de Calculadora</h1>
      <div class="grid">
        <button v-for="num in numbers" :key="num" @click="showNumber(num)">
          {{ num }}
        </button>
      </div>
      <p v-if="message">{{ message }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        message: '',
        numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9]
      };
    },
    methods: {
      showNumber(number) {
        this.message = `Has clicat el número: ${number}`;
      }
    }
  };
  </script>
  
  <style scoped>
  .calculator {
    text-align: center;
    font-family: Arial, sans-serif;
  }
  
  .grid {
    display: grid;
    grid-template-columns: repeat(3, 60px);
    gap: 10px;
    justify-content: center;
  }
  
  button {
    width: 60px;
    height: 60px;
    font-size: 20px;
    cursor: pointer;
    border: none;
    background-color: #f0f0f0;
    transition: background 0.3s;
  }
  
  button:hover {
    background-color: #d0d0d0;
  }
  </style>
  