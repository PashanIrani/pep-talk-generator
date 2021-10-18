<template>
  <div>
    <p>{{ text }}</p>
    <button @click="generate">Generate Another</button>
  </div>
</template>

<script>
import data from "../config/pep-talk-data";

export default {
  name: "Generator",
  data: () => {
    return { text: String };
  },
  created() {
    this.generate();
  },
  methods: {
    generate() {
      let picks = [
        Math.floor(Math.random() * data["1"].length),
        Math.floor(Math.random() * data["2"].length),
        Math.floor(Math.random() * data["3"].length),
        Math.floor(Math.random() * data["4"].length),
      ];

      this.text =
        data["1"][picks[0]] +
        " " +
        data["2"][picks[1]] +
        " " +
        data["3"][picks[2]] +
        " " +
        data["4"][picks[3]];
    },
  },
};
</script>

<style scoped>
button {
  border: none;
  background: none;
  font-size: 30px;
  font-family: Vintage, Helvetica, Arial, sans-serif;
}
</style>
