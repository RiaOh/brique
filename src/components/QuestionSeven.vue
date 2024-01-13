<template>
  <div>
    <h2>Question 7</h2>
    <input type="text" v-model="bracket" />
    <div>result: {{ result }}</div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      bracket: "",
    };
  },
  computed: {
    result() {
      let result = 0;
      //((()()()())))())()
      let arr = [];
      for (let i = 0; i < this.bracket.length; i++) {
        if (this.bracket[i] === "(") {
          if (arr.length === 0) {
            arr.push(this.bracket[i]);
          }
        }
      }
      return result;
    },
  },
};
</script>
