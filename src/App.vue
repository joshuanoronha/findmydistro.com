<template>
  <Question question="Welcome to Your Vue.js App" :answers="answers" />
</template>

<script>
import Question from "./components/Question.vue";

export default {
  name: "App",
  data() {
    return {
      answers: [
        { index: 1, value: "Ubuntu" },
        { index: 2, value: "Manjaro" },
      ],
    };
  },
  components: {
    Question,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
  max-width: 400px;
  margin: auto;
  color: white;
}
</style>
