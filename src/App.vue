<template>
  <Navbar/>
  <QuestionList />
</template>

<script>
import QuestionList from "./components/QuestionList.vue";
import Navbar from "./components/Navbar.vue";

export default {
  name: "App",
  data() {
    return {};
  },
  components: {
    QuestionList,
    Navbar,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');
 @import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+Thai+Looped:wght@500;700&display=swap');
#app {
  font-family: 'IBM Plex Sans Thai Looped',Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
  max-width: 500px;
  margin: auto;
  color: white;
}
</style>
