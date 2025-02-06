<script setup>
import { ref } from "vue";

const display = ref("0");

const arrayButtons = [
  {
    label: "AC",
    value: "AC",
    action: () => (display.value = "0"),
    class:
      "text-blue-400 text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "C",
    value: "C",
    action: () => (display.value = display.value.slice(0, -1)),
    class:
      "text-blue-400 text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "%",
    value: "%",
    action: () =>
      (display.value = (parseFloat(display.value) / 100).toString()),
    class:
      "text-blue-400 text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "/",
    value: "/",
    action: () => addOperator("/"),
    class:
      "text-red-400 text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "7",
    value: "7",
    action: () => appendNumber("7"),
    class:
      "text-white text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "8",
    value: "8",
    action: () => appendNumber("8"),
    class:
      "text-white text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "9",
    value: "9",
    action: () => appendNumber("9"),
    class:
      "text-white text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "X",
    value: "X",
    action: () => addOperator("*"),
    class:
      "text-red-400 text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "4",
    value: "4",
    action: () => appendNumber("4"),
    class:
      "text-white text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "5",
    value: "5",
    action: () => appendNumber("5"),
    class:
      "text-white text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "6",
    value: "6",
    action: () => appendNumber("6"),
    class:
      "text-white text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "-",
    value: "-",
    action: () => addOperator("-"),
    class:
      "text-red-400 text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "1",
    value: "1",
    action: () => appendNumber("1"),
    class:
      "text-white text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "2",
    value: "2",
    action: () => appendNumber("2"),
    class:
      "text-white text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "3",
    value: "3",
    action: () => appendNumber("3"),
    class:
      "text-white text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "+",
    value: "+",
    action: () => addOperator("+"),
    class:
      "text-red-400 text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "0",
    value: "0",
    action: () => appendNumber("0"),
    class:
      "text-white text-2xl rounded-xl bg-zinc-700 col-span-2 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: ".",
    value: ".",
    action: () => appendDecimal(),
    class:
      "text-white text-2xl rounded-xl bg-zinc-700 transition duration-200 ease-in-out active:border-2 border-gray-600 hover:scale-[102%] hover:shadow-2xl",
  },
  {
    label: "=",
    value: "=",
    action: () => calculateRes(),
    class:
      "bg-orange-600 text-white text-2xl rounded-xl transition duration-200 ease-in-out active:border-2 border-gray-700 hover:scale-[102%] hover:shadow-2xl",
  },
];

function appendNumber(value) {
  if (display.value == "0") {
    display.value = value;
  } else {
    display.value += value;
  }
}

function calculateRes() {
  button.value = eval(display.value).toString();
}
</script>

<template>
  <section
    class="bg-zinc-800 flex flex-col items-center w-[35%] shadow-2xl rounded-xl ml-auto mr-auto pt-20"
  >
    <div
      class="flex text-5xl text-white h-24 items-center justify-end pr-6 w-full"
    >
      {{ display || "0" }}
    </div>
    <div
      class="grid grid-cols-[100px,100px,100px,100px] pmt-2 pr-1 pl-1 pb-8 grid-rows-[75px,75px,75px,75px,75px] gap-5"
    >
      <button
        v-for="button in arrayButtons"
        :key="button.value"
        :class="button.class"
        @click="button.action"
      >
        {{ button.label }}
      </button>
    </div>
  </section>
</template>
