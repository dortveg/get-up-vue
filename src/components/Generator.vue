<template>
  <div class="generator">
    <button @click="randomExercise" class="genBtn">Give me an exercise!</button>
    <h3>{{ exercise }}</h3>
  </div>
</template>

<script>
export default {
  name: 'Generator',

  data() {
    return {
      exercise: ''
    }
  },

  methods: {
    randomExercise() {
      let exercises = ['Push-ups', 'Sit-ups', 'Pull-ups', 'Squats', 'Jump-Jacks'];
      const randomIndex = Math.floor(Math.random() * 5);
      const randomExercise = exercises[randomIndex];
      exercises.push(randomExercise);
      let self = this;
      for (let i = 0; i < exercises.length; i++) {
        (function (i) {
          setTimeout(function() {
            self.exercise = exercises[i];
          }, 90 * i);
        })(i);
      };
    }
  }
}
</script>

<style>
.generator {
  text-align: center;
}

.genBtn {
  width: 21.2%;
  margin-top: 2.2%;
}

h3 {
  font-family: 'Bungee';
  color: #6C8159;
  font-size: 3vw;
  margin-top: 3%;
}
</style>