<template>
  <div class="fixed top-0 bottom-0 left-0 right-0">
    <div class="center">
      <img :src="srcImg" alt="" class="m-auto" ref="img" width="250px" height="250px">
      <h2 class="text-[30px] m-5" ref="h2">能和我一起打瓦嘛？</h2>
      <div class="flex justify-around">
        <button class="bg-violet-400 hover:bg-violet-300" @click="resolve" v-if="!state" ref="button"
          :style="size">来吧走起</button>
        <button class="bg-indigo-400 hover:bg-indigo-300" @click="reject" v-if="!state">狠狠拒绝</button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { useTemplateRef, ref, computed } from 'vue'
import jpg from '../assets/test07.jpg'
import jpg1 from '../assets/test02.jpg'
import jpg2 from '../assets/test03.jpg'
import jpg3 from '../assets/test04.jpg'
import jpg4 from '../assets/test05.jpg'
import jpg5 from '../assets/test06.jpg'
import jpg6 from '../assets/test01.png'

const h2 = useTemplateRef<HTMLElement>('h2')
const img = useTemplateRef<HTMLElement>('img')
const button = useTemplateRef<HTMLButtonElement>('button')
const state = ref(false)
const num = ref(1)
const srcImg = ref(jpg1)
const arr = [jpg1, jpg2, jpg3, jpg4, jpg5, jpg6]
let index = 1

const size = computed(() => {
  return {
    transform: `scale(${num.value})`
  }
})

function resolve() {
  h2.value && (h2.value.innerText = '超级爱你！！')
  img.value && (img.value.setAttribute('src', jpg))
  state.value = true
}

function reject() {
  num.value += 0.6
  if (index < 5) {
    srcImg.value = arr[++index]
  }

}
</script>

<style scoped>
.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

button {
  border-radius: 10px;
  padding: 10px 22px;
  font-size: 18px;
  color: #fff;
}
</style>