<script setup></script>

<template>
  <section class="flex flex-col items-center gap-4">
    <span class="text-2xl text-zinc-600 font-semibold">Конвентр</span>
    <div class="flex gap-9">
      <div class="flex flex-col gap-4">
        <select class="p-2" name="units">
          <option>ТОННА</option>
          <option>КГ</option>
          <option>Г</option>
        </select>
        <input type="number" class="text-2xl rounded-xl p-2" />
      </div>
      <div class="flex flex-col gap-4">
        <select class="p-2" name="units">
          <option>ТОННА</option>
          <option>КГ</option>
          <option>Г</option>
        </select>
        <input type="number" class="text-2xl rounded-xl p-2" />
      </div>
    </div>
  </section>
</template>

<style>
input[type="number"] {
  -moz-appearance: textfield;
  -webkit-appearance: none;
  appearance: none;
}

input[type="number"]::-webkit-outer-spin-button,
input[type="number"]::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
</style>
