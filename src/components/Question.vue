<template>
  <div class="hello">
    <div v-for="item in questions" :key="item.key">
      {{ item.question.name }}
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
import { questions } from "./data.json";
import Option from "./Option.vue";
export default {
  name: "Question",
  components: {
    Option,
  },
  props: {
    question: String,
  },
  data() {
    return {
      questions,
    };
  },
  methods: {
    addScore(preferences) {
      this.$emit("update", preferences);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
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
