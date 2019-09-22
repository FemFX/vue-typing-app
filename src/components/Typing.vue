<template>
  <div>
    <div class="row">
      <div class="col-md-6 mx-auto">
        <p class="lead">
          Type The Given Word Within
          <span class="text-success" id="seconds">60</span> Seconds:
        </p>
        <h2 class="display-2 mb-5" id="current-word">{{ words[random] }}</h2>
        <input
          type="text"
          class="form-control form-control-lg"
          placeholder="Start typing..."
          id="word-input"
          autofocus
          @click="start"
          @keypress="submit"
          v-model="text"
        />
        <h4 class="mt-3" id="message"></h4>

        <div class="row mt-5">
          <div class="col-md-6">
            <h3>
              Time Left:
              <span id="time">{{ time }}</span>
            </h3>
          </div>
          <div class="col-md-6">
            <h3>
              Score:
              <span id="score">{{ score }}</span>
            </h3>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Typing",
  data() {
    return {
      words: [
        "hat",
        "river",
        "lucky",
        "statue",
        "generate",
        "stubborn",
        "cocktail",
        "runaway",
        "joke",
        "developer",
        "establishment",
        "hero",
        "javascript",
        "nutrition",
        "revolver",
        "echo",
        "siblings",
        "investigate",
        "horrendous",
        "symptom",
        "laughter",
        "magic",
        "master",
        "space",
        "definition"
      ],
      text: "",
      score: 0,
      time: 60,
      interval: undefined,
      random: undefined
    };
  },
  created() {
    this.getRandom();
  },
  methods: {
    start() {
      this.interval = setInterval(() => {
        if (this.time > 0) {
          this.time -= 1;
          console.log(this.time);
        } else {
          (this.time = 60), (this.score = 0);
          this.text = "";
          this.interval = clearInterval(this.interval);
        }
      }, 1000);
    },
    submit(e) {
      if (e.key === "Enter") {
        if (this.text == this.words[this.random]) {
          this.score += 1;
          this.text = "";
          this.getRandom();
        }
      }
    },
    getRandom() {
      this.random = Math.floor(Math.random() * 25);
    }
  }
};
</script>
<style scoped>
</style>