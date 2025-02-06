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
    <span class="pb-4 text-zinc-600 text-2xl font-semibold">Счетчик</span>
    <div
      class="flex flex-col shadow-xl gap-6 items-center p-12 rounded-xl bg-zinc-300"
    >
      <span class="text-5xl text-zinc-700">{{ count }}</span>
      <div class="flex gap-4">
        <Buttons
          @click="decrement()"
          class="text-2xl text-zinc-700 bg-zinc-200 pl-4 pr-4 rounded-md"
        >
          +
        </Buttons>
        <Buttons
          @click="increment()"
          value="-"
          class="text-2xl text-zinc-700 bg-zinc-200 pl-4 pr-4 rounded-md"
        >
          -
        </Buttons>
      </div>
    </div>
  </section>
</template>
