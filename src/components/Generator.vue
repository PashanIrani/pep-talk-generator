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
    return { text: String, seen: [[], [], [], []] };
  },
  created() {
    this.generate();
  },
  methods: {
    getRandom() {
      let picks = [
        Math.floor(Math.random() * data[1].length),
        Math.floor(Math.random() * data[2].length),
        Math.floor(Math.random() * data[3].length),
        Math.floor(Math.random() * data[4].length),
      ];

      for (let i = 0; i < picks.length; i++) {
        picks[i] = Math.floor(Math.random() * data[i + 1].length);

        if (this.seen[i].length >= 8) this.seen[i] = [];

        while (this.seen[i].includes(picks[i])) {
          picks[i] = Math.floor(Math.random() * data[i + 1].length);
        }

        this.seen[i].push(picks[i]);
      }

      return picks;
    },
    generate() {
      let picks = this.getRandom();

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
