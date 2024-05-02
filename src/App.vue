<template>
  <div id="app">
    <MyQuiz @show-modal="handleModal" />
    <AppModal :message="modalMessage" :show="showModal" @close="closeModal" />
  </div>
</template>

<script>
import { ref } from 'vue';
import MyQuiz from './components/MyQuiz.vue';
import AppModal from './components/AppModal.vue';

export default {
  components: {
    MyQuiz,
    AppModal
  },
  setup() {
    const modalMessage = ref('');
    const showModal = ref(false);

    const handleModal = (message) => {
      modalMessage.value = message;
      showModal.value = true;
    };

    const closeModal = () => {
      showModal.value = false;
    };

    return {
      modalMessage,
      showModal,
      handleModal,
      closeModal
    };
  }
}
</script>

