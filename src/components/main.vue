<script setup>
import IconCommunity from './icons/IconCommunity.vue';
import Bull from './icons/Bull.vue';
</script>

<template class="container">
  
          <div class="containerbackground">
            <p class=" text-blue-200 font-extrabold">DONGHONG</p>
           
        </div>
      <header class="py-12 px-10 text-center max-w-5xl mx-auto">
      <div class="flex justify-between ">
        <div class="flex justify-center gap-4 mb-4">
          <div class="flex items-center justify-center">
            <div class="w-14 h-14 rounded-full flex items-center justify-center text-xs">
              <IconCommunity />
            </div>
            <div class="text-xl font-bold text-blue-900 pb-2">9001</div>
          </div>
          <div class="w-14 h-14 rounded-full border flex items-center justify-center text-xs">
            CE
          </div>
        </div>
        <div class="w-14 h-14 flex items-center text-xs">
          <Bull/>
        </div>
      </div>  
      <h1 class="text-4xl font-extrabold text-blue-900">
        DAMAI ATTACHMENT
      </h1>
      <p class=" text-2xl mt-2 text-blue-900 font-bold">
        EXCAVATOR ATTACHMENT MANUFACTURER SINCE 2007
      </p>
    </header>
    <section class="flex items-center justify-center">
      <div class="grid  grid-cols-4 gap-6">

        <div
          v-for="i in 16"
          :key="i"
          class="bg-gray-100 w-48 h-40 border rounded-xl flex items-center justify-center
                 hover:shadow-lg transition"
        >
            <span class=" text-gray-400 text-sm ">
              Product {{ i }}
            </span>
          
        </div>

      </div>
    </section>

    <section class=" py-12">
      <div class="mx-auto px-4 flex gap-12 items-center justify-center">

        <div class="space-y-3 text-sm">
          <div class="py-2 text-lg font-extrabold text-last-justify">
            Yantai Damai Construction Machinery Co., Ltd.
          </div>
          <div class="py-2 text-lg font-extrabold text-last-justify">
            Yantai Donghong Construction Machinery Co., Ltd.
          </div>

        </div>

        <div>
        <div class="flex gap-4 items-center justify-center">
          <div class="w-24 h-24 border rounded flex items-center justify-center text-xs text-gray-500">
            WeChat
          </div>
          <div class="w-24 h-24 border rounded flex items-center justify-center text-xs text-gray-500">
            WhatsApp
          </div>
        </div>
                  <div class="text-lg font-semibold">
            Phone: +86-159-6646-3508
                  </div>
        </div>

      </div>
    </section>

</template>

