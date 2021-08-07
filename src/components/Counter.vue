<template>
  <div class="main">
    <h2>Time since you moved your lazy ass:</h2>
    <h1 :class="{ warning: warning }" class="count">{{ count }}</h1>
    <button @click="start" :class="{ disabled: !disabled }" :disabled="!disabled">Start Timer</button>
    <button @click="stop" :class="{ disabled: disabled }" :disabled="disabled">Stop Timer</button>
  </div>
</template>

<script>
const alert1 = new Audio('src/sounds/1.wav');
const alert2 = new Audio('src/sounds/2.wav');
const alert3 = new Audio('src/sounds/3.wav');
const alert4 = new Audio('src/sounds/4.wav');
const alert5 = new Audio('src/sounds/5.wav');
const alert6 = new Audio('src/sounds/6.wav');
const alerts = [alert1, alert2, alert3, alert4, alert5, alert6];

export default {
  name: 'Counter',

  data() {
    return {
      timer: null,
      sec: 0,
      min: 0,
      hr: 0,
      count: '00:00:00',
      disabled: true,
      warning: false
    }
  },

  methods: {
    tick() {
      if (this.min === 59) {
        this.min = 0;
        this.hr++;
    
        const randomAlert = Math.floor(Math.random() * 6);
        alerts[randomAlert].play();
        this.warning = true;
      } else if (this.sec === 59) {
        this.sec = 0;
        this.min++;
      } else {
        this.sec++;
      }
    
      if (this.sec <= 9 && this.min <= 9) {
        this.count = `0${this.hr}:0${this.min}:0${this.sec}`;
      } else if (this.sec >= 10 && this.min <= 9) {
        this.count = `0${this.hr}:0${this.min}:${this.sec}`;
      } else if (this.sec <= 9 && this.min >= 10) {
        this.count = `0${this.hr}:${this.min}:0${this.sec}`;
      } else {
        this.count = `0${this.hr}:${this.min}:${this.sec}`;
      }
    },

    start() {
      this.timer = setInterval(this.tick, 1000);
      this.disabled = !this.disabled;
    },

    stop() {
      clearInterval(this.timer);
      this.disabled = !this.disabled;
      if (this.warning) {
        !this.warning;
      }
      this.count = '00:00:00';
    }
  }
}
</script>

<style>
.main {
  text-align: center;
  margin-top: 10vh;
}

h1 {
  font-size: 4.5vw;
  color: #E4D6A9;
  font-family: 'Syne';
}

h2 {
  font-size: 3vw;
  color: #E4D6A9;
  font-family: 'Bungee';
}

button {
  width: 9.5%;
  color: #141313;
  background: #E4D6A9;
  border: none;
  border-radius: 5px;
  outline: none;
  cursor: pointer;
  font-family: 'Julius';
  font-weight: bold;
  font-size: 1vw;
  margin-left: 1%;
  margin-right: 1%;
  margin-top: 2%;
  padding-top: 1.3%;
  padding-bottom: 1.3%
}

button:hover {
  background: #bba251;
}

.disabled {
  background-color: #414141;
  color: grey;
  cursor: default;
  pointer-events: none;
}

.warning {
  color: #5e2424;
}
</style>