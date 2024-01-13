<template>
  <div>
    <h2>Question 5</h2>
    <div>response: {{ response }}</div>
    <button @click="getRandomResponse">push</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      response: null,
    };
  },
  methods: {
    getRandomResponse() {
      let array = [];
      for (let i = 0; i < 100; i++) {
        fetch("http://localhost:3000")
          .then((response) => {
            return response.json();
          }) //{id:2, quote:'dd'}
          .then((responseData) => {
            if (array.some((obj) => obj.value.id === responseData.id)) {
              const findIndex = array.findIndex(
                (obj) => obj.value.id === responseData.id
              );
              array[findIndex].count++;
            } else {
              array.push({ count: 1, value: responseData });
            }
          });
      }
      this.response = array;
    },
  },
  watch: {
    response(newRes) {
      this.response = newRes;
    },
  },
};
</script>
