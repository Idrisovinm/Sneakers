<script setup>
defineProps({
  id: Number,
  title: String,
  imageUrl: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickFavorite: Function,
  onClickAdd: Function
})
</script>

<template>
  <div>
    <div
      class="relative flex flex-col w-full h-full border border-slate-100 rounded-xl p-8 cursor-pointer transition hover:shadow-xl hover:transform hover:-translate-y-2"
    >
      <img
        v-if="onClickFavorite"
        :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'"
        alt="Like 1"
        class="absolute top-8 left-8"
        @click="onClickFavorite"
      />
      <img :src="imageUrl" alt="Sneaker" />
      <p class="h-full w-full">{{ title }}</p>

      <div class="flex justify-between mt-5">
        <div class="flex flex-col gap-2">
          <span class="text-slate-400">Цена:</span>
          <span class="font-bold">{{ price }} руб.</span>
        </div>
        <img v-if="onClickAdd" @click="onClickAdd" :src="!isAdded ? '/plus.svg' : '/checked.svg'" alt="Plus" />
      </div>
    </div>
  </div>
</template>
