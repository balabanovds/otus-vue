<template>
  <h1 v-if="visible">Молодец!!!</h1>
</template>

<script>
export default {
  name: "Result",
  props: {
    visible: Boolean
  }
};
</script>

<style scoped></style>
