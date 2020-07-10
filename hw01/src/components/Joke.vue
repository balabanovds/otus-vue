<template>
  <div class="row">
    <div class="area">
      <div class="wrapper" @mouseover="hide" @mouseout="show">
        <button v-if="visible" class="no">Нет</button>
      </div>
    </div>
    <div class="area">
      <button class="yes" @click="yes">Да</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Joke",
  data() {
    return {
      visible: true
    };
  },
  methods: {
    hide() {
      this.visible = false;
    },
    show() {
      this.visible = true;
    },
    yes() {
      this.$emit("showResult");
    }
  }
};
</script>

<style scoped lang="scss">
.row {
  display: flex;
  justify-content: center;
}
.wrapper {
  width: 100px;
  height: 50px;
}
.area {
  width: 200px;
  height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
}
button {
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  &.yes {
    background-color: forestgreen;
    &:hover {
      background-color: darkgreen;
      cursor: pointer;
      box-shadow: 5px 0px 10px rgba(0, 0, 0, 0.2);
    }
  }
  &.no {
    background-color: orangered;
  }
}
</style>
