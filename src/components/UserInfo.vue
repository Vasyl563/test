<template>
  <div class="md flex">
    <img :src="Avatar" alt="Avatar" class="avatar rounded-full absolute z-20 mt-4">
    <div class="ml-3 flex flex-col w-full ml-[100px]">
      <h1 class="font-bold size-xl pl-[3.5rem]">Eva Jonson</h1>
      <h2 class="text-[#808080] mt-[2px] mb-[5px] size-xl pl-[3.5rem]">Seles Manager</h2>
      <p class="border-2 rounded-md bg-[#FFFBC8] size-md flex item-center text-[#333333]  leading-9 relative z-10 justify-items-start pl-[3.5rem]">
        I will find the best offers for you.<br>
        My services are absolutely free.</p>
      <Services/>
    </div>
  </div>
</template>

<script setup>
import Avatar from '@/assets/img/avatar.png';
import Services from "@/components/services/Services.vue";
</script>

<style>
.avatar {
  min-width: clamp(150px, 10%, 160px);
}

.size-xl {
  font-size: clamp(1rem, 3vw, 1.7rem);
}

.size-md {
  font-size: clamp(0.9rem, 3vw, 1.5rem);
}
</style>
