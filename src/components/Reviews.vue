<template>
  <div class="flex justify-between mb-6 ">
    <div class="flex items-center">
      <h2 class="font-bold size-xl mr-4">
        Latest reviews
      </h2>
      <a href="#" class="text-[#005DA1] underline">All reviews</a>
    </div>
    <div class="flex justify-between">
      <div class="flex items-center mr-5">
        <button @click="like++">
          <img :src="Like" alt="Like" class="mr-1 w-[17px]">
        </button>
        <h3>{{ like }}</h3>
      </div>
      <div class="flex items-center">
        <button @click="comments++">
          <img :src="Comment" alt="Like" class="mr-1 w-[17px]">
        </button>
        <h3>{{ comments }}</h3>
      </div>
    </div>
  </div>
</template>

<script setup>
import {ref} from "vue";
import Like from '@/assets/img/like.svg';
import Comment from '@/assets/img/comment.svg';

const like = ref(131);
const comments = ref(14)
</script>
