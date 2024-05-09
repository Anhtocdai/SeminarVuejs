<template>
    <div>
      <p>{{ count }}</p>
      <button v-on:click="increment">Tăng</button>
    </div>
  </template>

  
  <script>
  export default {
    data() {
      return {
        count: 0
      } },
    methods: {
      increment() {
        this.count++ } }
  }
  </script>
  


