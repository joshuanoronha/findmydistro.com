<template>
  <div>
    <div v-for="item in questions" :key="item.key">
      <Question class="question" :name="item.question.name" />
      <div class="options">
        <div
          v-for="option in item.options"
          :key="option.name"
          class="option"
          @click="addScore(option.preferences)"
        >
          <Option :name="option.name" />
        </div>
      </div>
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
    };
  },
  methods: {
    addScore(preferences) {
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
.options {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
.option {
  flex: 0 50%;
}
</style>