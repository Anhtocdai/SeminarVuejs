<template>
  <div class="modal" v-show="show">
    <div v-html="message"></div>
    <button @click="$emit('close')">Close</button>
  </div>
</template>

<script>
export default {
  props: ['message', 'show'],
  methods: {
  },
    
};
</script>

<style>
.modal {
  position: fixed;
  width: 40vh;
  height: 30vh;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #ffffff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
}

.modal p {
  margin-bottom: 10px;
}

.modal button {
  padding: 10px 20px;
  background-color: #007bff;
  color: #ffffff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  margin: auto;
  margin: 20px 20px 20px 90px;
}

.modal button:hover {
  background-color: #0056b3;
}
</style>
