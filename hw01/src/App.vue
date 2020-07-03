<template>
  <div id="app">
    <Hero />
    <Joke @showResult="showResult = !showResult" />
    <Result :visible="showResult" />
  </div>
</template>

<script>
import Hero from "./components/Hero";
import Joke from "./components/Joke";
import Result from "./components/Result";

export default {
  name: "App",
  data() {
    return {
      showResult: false
    };
  },
  watch: {
    showResult() {
      setTimeout(() => {
        this.showResult = false;
      }, 1000);
    }
  },
  components: {
    Hero,
    Joke,
    Result
  }
};
</script>

<style lang="scss">
* {
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  max-width: 800px;
  margin: 60px auto 0;
}
</style>
