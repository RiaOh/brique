<template>
  <div>
    <QuestionFour />
    <hr />
    <question-five />
    <hr />
    <question-seven />
  </div>
</template>

<script>
import QuestionFour from "./components/QuestionFour.vue";
import QuestionFive from "./components/QuestionFive.vue";
import QuestionSeven from "./components/QuestionSeven.vue";

export default {
  name: "App",
  components: {
    QuestionFour,
    QuestionSeven,
    QuestionFive,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
