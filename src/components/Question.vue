<template>
  <div>
    <div class="name">{{ name }}</div>
  </div>
</template>

<script>
export default {
  name: "Question",
  props: {
    name: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.name {
  font-size: 20px;
  padding-bottom: 20px;
}
</style>
