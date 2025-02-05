<script setup>
import { ref } from "vue";
import Buttons from "./smlComponents/Buttons.vue";
const count = ref("0");

function decrement() {
  count.value++;
}
function increment() {
  count.value--;
}
</script>

<template>
  <section class="flex flex-col p-16 rounded-md items-center">
    <span class="pb-4 text-2xl font-bold">Счетчик</span>
    <div class="flex flex-col gap-6 items-center p-12 rounded-xl bg-zinc-700">
      <span class="text-5xl text-white">{{ count }}</span>
      <div class="flex gap-4">
        <Buttons
          @click="decrement()"
          class="text-4xl t text-white bg-red-400 w-14 rounded-md"
        >
          +
        </Buttons>
        <Buttons
          @click="increment()"
          value="-"
          class="text-4xl text-white bg-red-400 w-14 rounded-md"
        >
          -
        </Buttons>
      </div>
    </div>
  </section>
</template>
