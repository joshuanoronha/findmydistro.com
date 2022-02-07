<template>
  <div class="option">{{ name }}</div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: "",
    },
  },
};
</script>

<style scoped>
.option {
  padding: 25px;
  text-align: center;
  margin: 10px;
  border: 2px solid white;
  border-radius: 8px;
}
.option:hover {
  padding: 19px;
  border: 3px solid white;
  font-weight: 700;
  outline: 0px
}
</style>