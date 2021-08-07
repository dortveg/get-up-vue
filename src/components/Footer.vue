<template>
  <div class="about">
    <p class="info">Start the timer. You will get yelled at after an hour. Get up, move, and reset the timer. Repeat.</p>
    <p class="copyright"><a @mouseover="toggleDonate" class="link" href="javascript:void()">Donate </a>| ©2021 GT |<a class="link" href="https://github.com/dortveg"> GitHub</a></p>
    <div @mouseleave="toggleDonate" v-show="showDonate" class="donateInfo">
      <span class="plea">If you love this app, please show your support and help make it bigger and better!</span>
      <hr>
      <h6>BTC: 1JZEk5FkuTGLWpMdgzXH3AHfqohXaqyFsZ</h6>
      <h6>ERC20: 0xcfC8D2e358F656440C8628722fA850cB12245D31</h6>
      <h6>NANO: nano_37n6z9gqs1j73pwq3gzswegdyk8haty1pifu7obk9eftutxujzer6n5j7kkp</h6>
      <h6>XMR: 49j14X3nqN74eqDkVLKiARjJsXC4EZHLWKZsg6HMwntLXAhHH6J75GeBpevKaS8NZ956cb43KsUKbh9KAjuJugzA7RNKhhU</h6>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Footer',
  data() { 
    return { 
      showDonate: false
    } 
  },

  methods: {
    toggleDonate() {
      this.showDonate = !this.showDonate;
    }
  }
}
</script>

<style>
.about {
  text-align: center;
  position: fixed;
  bottom: 0;
  width: 100%;
  margin-bottom: 1vh;
}

p {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 1.2vw;
  color: #9e9e9e;
  font-family: 'Syne';
}

.copyright {
  margin-top: 7vh;
  font-size: 1vw;
}

.link:link, .link:visited {
  color: #353232;
  background-color: transparent;
  text-decoration: none;
}

.link:hover {
  color: grey;
  background-color: transparent;
  text-decoration: none;
}

.donateInfo {
  position: fixed;
  bottom: 0%;
  right: 4%;
  background-color: #1f1c2d;
  color: #f3ecce;
  width: 42vw;
  z-index: 1;
  border-radius: 5px;
  font-family: 'Syne';
  padding-top: .7vh;
  padding-bottom: .5vh;
}

.plea {
  font-size: .9vw;
}

hr {
  width: 90%;
  border-color: #f3ecce;
  margin-bottom: .9vh;
}

h6 {
  margin-top: .5vh;
  margin-bottom: .5vh;
  font-size: .6vw;
}
</style>