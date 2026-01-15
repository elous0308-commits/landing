<script setup>
import productGrid from './productGrid.vue';

import IconCommunity from './icons/IconCommunity.vue';
import Bull from './icons/Bull.vue';
import CE from './icons/CE.vue';
</script>

<template class="container">
  
          <div class="containerbackground">
            <p class=" text-blue-200 font-extrabold">DONGHONG</p>
           
        </div>
      <header class="py-12 px-10 text-center max-w-5xl mx-auto">
      <div class="flex justify-between ">
        <div class="flex justify-center gap-6 mb-4">
          <div class="flex items-center justify-center">
            <div class="w-14 h-14 rounded-full flex items-center justify-center">
              <IconCommunity />
            </div>
            <div class="text-xl font-bold text-blue-900 pb-2">9001</div>
          </div>
          <div class="w-8 pb-2 flex items-center justify-center ">
            <CE />
          </div>
        </div>
        <div class="w-14 h-14 flex items-center ">
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
 <productGrid></productGrid>
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
            Telegram
          </div>
          <div class="w-24 h-24 border rounded flex items-center justify-center text-xs text-gray-500">
            WhatsApp
          </div>
        </div>
                  <div class="text-lg font-semibold">
            Phone: +7(959)-***-**-**
                  </div>
        </div>

      </div>
    </section>  
    <hr class="border-8">
    <footer>
      <div class="flex items-end ml-10 mt-14 mb-2">
        <div class="text-8xl text-blue-200 font-extrabold">01</div>
        <div class="pb-1.5 text-gray-500">QUALIFICATION<br>CERTIFICAT</div>
      </div>
      <div class="h-12 bg-blue-500"></div>
    </footer>
</template>

