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
  padding: 35px 25px;
  text-align: center;
  margin: 10px;
  font-size: 20px;
  border: 2px solid white;
  border-radius: 8px;
}
.option:hover {
  text-shadow: 0 0 4px #fff;
  box-shadow: 0px 0px 6px 1px #fff;
  font-weight: 700;
  outline: 0px
}
</style>