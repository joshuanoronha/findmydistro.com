<template>
  <Navbar />
  <QuestionList />
</template>

<script>
import QuestionList from "./components/QuestionList.vue";
import Navbar from "./components/Navbar.vue";

export default {
  name: "App",
  mounted() {
    const index = this.getRandomInt(this.colorList.length);
    document.body.style = this.colorList[index];
  },
  data() {
    return {
      colorList: [
        "background: linear-gradient(93deg,rgba(255, 28, 130, 1) 0%,rgba(253, 29, 29, 1) 41%,rgba(252, 119, 69, 1) 100%);",
        "background: linear-gradient(93deg, rgba(28,202,255,1) 0%, rgba(29,73,253,1) 41%, rgba(82,12,228,1) 100%);",
        "background: linear-gradient(90deg, #3F2B96 0%, #A8C0FF 100%);",
        "background: linear-gradient(90deg, #FDBB2D 0%, #3A1C71 100%);",
        "background: linear-gradient(90deg, #d53369 0%, #daae51 100%);",
        "background: linear-gradient(90deg, #4b6cb7 0%, #182848 100%);",
        `background:
        linear-gradient(135deg, #002366 25%, transparent 25%) -50px 0,
        linear-gradient(225deg, #002366 25%, transparent 25%) -50px 0,
        linear-gradient(315deg, #002366 25%, transparent 25%),
        linear-gradient(45deg, #002366 25%, transparent 25%);
        background-size: 100px 100px;
        background-color: rgb(0, 26, 102)`,
      ],
    };
  },
  methods: {
    getRandomInt(max) {
      return Math.floor(Math.random() * max);
    },
  },
  components: {
    QuestionList,
    Navbar,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap");
@import url("https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+Thai+Looped:wght@500;700&display=swap");
#app {
  font-family: "IBM Plex Sans Thai Looped", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
  max-width: 500px;
  margin: auto;
  color: white;
}
body {
  background: #000;
}
</style>
