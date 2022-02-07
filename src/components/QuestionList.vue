<template>
  <div>
    <div v-for="(item, index) in questions" :key="item.key">
      <div v-if="index == current">
        <Question class="question question-height">{{
          item.question.name
        }}</Question>
        <div class="options">
          <div
            v-for="option in item.options"
            :key="option.name"
            class="option"
            @click="addScore(option.preferences)"
          >
            <Option>{{ option.name }}</Option>
          </div>
        </div>
      </div>
    </div>
    <div class="distro" v-if="distro">
      <Question class="question-height">Your distro is {{ distro }}</Question>
      <Option class="replay" @click="restart">&#x21bb;</Option>
    </div>
  </div>
</template>

<script>
import Question from "./Question.vue";
import Option from "./Option.vue";
import { questions } from "../data/data.json";

export default {
  components: {
    Question,
    Option,
  },
  data() {
    return {
      questions,
      current: 0,
      distro: "",
    };
  },
  methods: {
    restart() {
      this.distro = "";
      this.current = 0;
    },
    addScore(preferences) {
      this.current += 1;
      if (this.current === questions.length) {
        this.distro = "Ubuntu";
      }
      console.log(preferences);
      this.$emit("update", preferences);
    },
  },
};
</script>

<style scoped>
.question {
  margin-left: 10px;
}
.question-height {
  height: 100px;
}
.options {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
.option {
  flex: 0 50%;
}
.distro {
  margin: auto;
  text-align: center;
}
.replay::v-deep {
  display: flex;
  padding: 10px;
  width: 100px;
  margin: auto;
  justify-content: center;
}
.replay {
  font-family: Lucida Sans Unicode;
  font-size: 35px;
}
</style>