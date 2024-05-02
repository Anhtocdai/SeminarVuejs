<template>
  <input v-model.trim="message" placeholder="Enter your message">
</template>

  <script>
  export default {
    data() {
      return {
        count: 0
      };
    },
    methods: {
      increment() {
        this.count++;
      },
      decrement() {
        this.count--;
      }
    }
  };
  </script>
  
  <style scoped>
  /* CSS styles for the Counter component */
  .counter button {
    padding: 10px 20px;
    font-size: 16px;
    margin: 0 10px;
    cursor: pointer;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 5px;
    transition: background-color 0.3s;
  }
  </style>


