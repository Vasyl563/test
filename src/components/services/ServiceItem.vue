<template>
  <div class="flex justify-between my-1">
    <div class="p-1 pr-[7rem] size-md max-[540px]:pr-5 max-[540px]:text-xs  max-[408px]:pr1" :style="{background: service.bgColor}">{{ service.text }}</div>
    <div class="font-bold pr-4 size-md">{{ service.count }}</div>
  </div>
</template>

<script setup>
defineProps({
  service: {
    type: Object,
    default: () => null
  }
})

</script>
