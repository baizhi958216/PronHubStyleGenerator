<template>
  <div class="pornbg-ipt">
    <input v-model="left" class="pornbg-left" type="text">
    <input v-model="right" class="pornbg-right" type="text">
  </div>

  <div class="generate">
    <button class="generate-btn" @click="generate">Generate</button>
  </div>

  <div class="pornbg">
    <div class="gen-left">{{ left }}</div>
    <div class="gen-right">{{ right }}</div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import html2canvas from 'html2canvas'
import { saveAs } from 'file-saver';
let left = ref(''), right = ref('')

const generate = () => {
  html2canvas(document.querySelector('.pornbg')).then((canvas)=>{
    canvas.toBlob((blob)=>{
      saveAs(blob,`${left.value}${right.value}.png`)
    })
  })
}


</script>

<style lang="less" scoped>
.pornbg-ipt {
  display: flex;
  justify-content: space-around;

  .pornbg-left,
  .pornbg-right {
    background-color: rgba(233, 231, 231, 0.912);
    height: 40px;
    width: 40%;
    border: none;
    outline: none;
    text-align: center;
    font-size: 30px;
    border-radius: 10px;
    margin: 30px 0;
  }
}

.generate {
  display: flex;
  justify-content: center;
  align-items: center;

  &-btn {
    font-size: 40px;
    color: orange;
    border: none;
    cursor: pointer;
    background-color: rgb(63, 63, 63);
    font-family: 'Fira Code';
    font-weight: 600;
    margin-bottom: 20px;
  }
}

.pornbg {
  background-color: black;
  width: 80%;
  height: 50vh;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  font-size: 70px;
  overflow: scroll;

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
</style>