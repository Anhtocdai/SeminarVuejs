<template>
  <div>
    <div class='quiz-question' v-for="(question, index) in questions" :key="index">
      <h2>{{ question.title }}</h2>
      <ul class='quiz-options'>
        <li class='quiz-option' v-for="(option, optionIndex) in question.options" :key="optionIndex" @click="checkAnswer(index, option)">
          {{ option }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      questions: [
        {
          title: "Quiz 1: Which Vue directive is used to conditionally display an element?",
          options: ["v-model", "v-bind", "v-show", "v-for"],
          correctAnswer: "v-show"
        },
        {
          title: "Quiz 2: To display the value from the data property 'message' inside a <p> tag with text interpolation, what is the correct syntax?",
          options: ["<p>// message //</p>", "<p>'' message ''</p>", "<p>{{ message }}</p>", "<p>## message ##</p>"],
          correctAnswer: "<p>{{ message }}</p>"
        },
        {
          title: "Quiz 3: How do you define a computed property in Vue?",
          options: ["As a method inside the 'computed' instance", "As a variable inside the 'computed' instance", "As a method inside the 'methods' instance", "As a variable inside the 'methods' instance"],
          correctAnswer: "As a method inside the 'computed' instance"
        }
      ]
    };
  },
  methods: {
    checkAnswer(questionIndex, selectedOption) {
      const correctAnswer = this.questions[questionIndex].correctAnswer;

      if (selectedOption === correctAnswer) {
        this.$emit('show-modal', '<h1> Chúc mừng, bạn đã trả lời đúng! </h1>');
      } else {
        this.$emit('show-modal', "<h1> Chúc bạn may mắn lần sau (^ . ^)</h1>");
      }
    }
  }
};
</script>

<style scoped>
.quiz-question {
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 15px;
  margin-bottom: 20px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.quiz-question h2 {
  margin-top: 0;
}

.quiz-options {
  list-style-type: none;
  padding-left: 0;
}

.quiz-option {
  cursor: pointer;
  padding: 10px;
  background-color: #ffffff;
  border: 1px solid #ddd;
  border-radius: 5px;
  margin-bottom: 5px;
  transition: background-color 0.3s ease;
}

.quiz-option:hover {
  background-color: #f0f0f0;
}
</style>
