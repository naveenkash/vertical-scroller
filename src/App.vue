<template>
  <div id="app">
    <div class="makeItScroll">
      <div class="scroll-direction">
        <h1>Scroll Down</h1>
      </div>
    </div>
    <ScrollMain />
    <div class="makeItScroll">
      <div class="scroll-direction">
        <h1>Scroll Up</h1>
      </div>
    </div>
  </div>
</template>

<script>
import ScrollMain from "./components/scrollMain";
export default {
  name: "app",
  components: {
    ScrollMain
  },
  data() {
    return {};
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Noto+Sans&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Noto Sans", sans-serif;
}
.makeItScroll {
  height: 100vh;
  width: 100%;
}
.scroll-direction {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}
.scroll-direction h1 {
  font-size: 50px; 
  background: -webkit-linear-gradient(#eee, #333);
  background: linear-gradient(to right,rgb(2, 255, 171), rgb(77, 255, 71));
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.fixed {
  position: fixed;
  top: 0;
  bottom: 0;
  width: 500px;
  overflow: hidden;
  display: block;
}
</style>
