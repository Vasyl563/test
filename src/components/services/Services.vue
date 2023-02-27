<template>
  <div class=" ml-[3.5rem] pr-[3rem] max-[450px]:pr-[1.5rem] max-[450px]:ml-[1.7rem]">
    <h3 class="size-md mt-[1rem] pb-[.5rem] flex justify-end">Services</h3>
    <div class="border-b-[#DADADA] border-b-2"></div>
    <ServiceItem
        v-for="(service, index) in services"
        :key="index"
        :service="service"
    />
    <div class="border-b-[#DADADA] border-b-2 w-full mt-[1rem]"></div>
    <div class="pt-[9px] flex justify-between">
      <h4 class="font-bold size-xl mb-10">Total</h4>
      <h5 class="font-bold size-xl pr-4">{{ sum }}</h5>
    </div>
  </div>
</template>

<script setup>
import {computed, ref} from "vue";
import ServiceItem from "@/components/services/ServiceItem.vue";

const services = ref(
    [
      {
        bgColor: '#B1E19B',
        text: 'Manual tour booking',
        count: 11
      },
      {
        bgColor: '#ACE2F8',
        text: 'Package tours',
        count: 3
      },
      {
        bgColor: '#ACE2F8',
        text: 'Hotels',
        count: 1
      }
    ]
)

const sum = computed(() => services.value.reduce((acc, item) => acc + item.count, 0))

</script>
