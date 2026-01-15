<script setup>
import { ref, nextTick } from 'vue'

import img1 from "../assets/img/1.jpg"
import img2 from "../assets/img/2.jpg"
import img3 from "../assets/img/3.jpg"
import img from "../assets/img/img.png"

const products = [
  { id: 1, title: 'Товар 1', img: img, desc: 'Описание товара 1' },
  { id: 2, title: 'Товар 2', img: img, desc: 'Описание товара 2' },
  { id: 3, title: 'Товар 3', img: img, desc: 'Описание товара 3' },
  { id: 4, title: 'Товар 4', img: img, desc: 'Описание товара 4' },
  { id: 5, title: 'Товар 5', img: img, desc: 'Описание товара 5' },
  { id: 6, title: 'Товар 6', img: img, desc: 'Описание товара 6' },
  { id: 7, title: 'Товар 7', img: img, desc: 'Описание товара 7' },
  { id: 8, title: 'Товар 8', img: img, desc: 'Описание товара 8' },
  { id: 9, title: 'Товар 9', img: img, desc: 'Описание товара 9' },
  { id: 10, title: 'Товар 10', img: img, desc: 'Описание товара 10' },
  { id: 11, title: 'Товар 11', img: img, desc: 'Описание товара 11' },
  { id: 12, title: 'Товар 12', img: img, desc: 'Описание товара 12' },
  { id: 13, title: 'Товар 13', img: img, desc: 'Описание товара 13' },
  { id: 14, title: 'Товар 14', img: img, desc: 'Описание товара 14' },
  { id: 15, title: 'Товар 15', img: img, desc: 'Описание товара 15' },
  { id: 16, title: 'Товар 16', img: img, desc: 'Описание товара 16' },
]

const active = ref(null)
const phase = ref('idle')
const modalStyle = ref({})

const open = async (e, product) => {
  const rect = e.target.getBoundingClientRect()
  active.value = product
  phase.value = 'expand'

  // старт — как картинка
  modalStyle.value = {
    top: rect.top + 'px',
    left: rect.left + 'px',
    width: rect.width + 'px',
    height: rect.width + 'px',
    transform: 'translate(0,0)',
    borderRadius: '12px',
  }

  await nextTick()

  requestAnimationFrame(() => {
    modalStyle.value = {
      top: '50%',
      left: '50%',
      width: '1000px',
      height: '450px',
      transform: 'translate(-50%, -50%)',
    }
  })

  setTimeout(() => {
    phase.value = 'opened'
  }, 450)
}

const close = () => {
  active.value = null
  phase.value = 'idle'
}
</script>
<template>
  <!-- GRID -->
  <div class="grid grid-cols-4 gap-4  ">
    <img
      v-for="p in products"
      :key="p.id"
      :src="p.img"
      class="rounded-lg cursor-pointer w-40 border-2 bg-gray-100"
      @click="open($event, p)"
    />
  </div>

  <!-- MODAL -->
  <Teleport to="body">
    <div v-if="active" class="fixed inset-0 z-50 ">
      
      <!-- overlay -->
      <div
        class="absolute inset-0 bg-black/40"
        @click="close"
      />

      <!-- PANEL (ЕДИНЫЙ ОБЪЕКТ) -->
      <div
        class="fixed bg-white shadow-2xl overflow-hidden transition-all duration-500 ease-in-out z-10 border-2 rounded-lg"
        :style="modalStyle"
      >
        <div class="flex h-full">
          
          <!-- IMAGE (часть панели) -->
          <div class="w-2/5 h-full overflow-hidden">
            <img
              :src="active.img"
              class="w-full h-full object-cover transition-transform duration-500 border-r-2 bg-gray-100"
              :class="phase === 'opened' ? 'scale-100' : 'scale-105'"
            />
          </div>

          <!-- CONTENT -->
          <div
            class="w-3/5 p-6 transition-all duration-300"
            :class="phase === 'opened'
              ? 'opacity-100 translate-x-0'
              : 'opacity-0 translate-x-6'"
          >
            <h2 class="text-2xl font-bold mb-3">
              {{ active.title }}
            </h2>
            <p class="text-gray-600 text-sm">
              {{ active.desc }}
            </p>
          </div>

        </div>
      </div>
    </div>
  </Teleport>
</template>