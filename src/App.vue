<template>
  <div class="pornbg">
    <div class="pornbg-ipt">
      <input v-model="left" class="pornbg-left" type="text">
      <input v-model="right" class="pornbg-right" type="text">
    </div>
    <div class="pornbg-gen">
      <div class="gen-left">{{ left }}</div>
      <div class="gen-right">{{ right }}</div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
let left = ref(''), right = ref('')

</script>

<style lang="less" scoped>
.pornbg {
  background-color: black;
  width: 800px;
  height: 800px;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: column;

  &-ipt {
    display: flex;
    justify-content: space-around;

    .pornbg-left,
    .pornbg-right {
      background-color: rgba(255, 255, 255, 0.646);
      height: 40px;
      width: 40%;
      border: none;
      outline: none;
      margin-top: 10px;
      text-align: center;
      font-size: 30px;
      border-radius: 10px;
    }
  }

  &-gen {
    position: relative;
    top: 30%;
    display: flex;
    font-size: 100px;
    font-family: 'Fira Code';
    align-items: center;
    justify-content: center;

    .gen-left {
      color: white;
      font-weight: 700;
    }

    .gen-right {
      background-color: orange;
      font-weight: 700;
      border-radius: 10px;
    }
  }
}
</style>