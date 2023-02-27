<template>
  <div>
    <section class="chat-area flex flex-col text-left">
      <div
          v-for="(item, index) in listMessages"
          :key="index"
          class="message message-in">
       <div class="flex">
         <span class="mr-3 font-bold">{{ item.author}}</span>
         <span class="text-[#808080]">{{ item.date}}</span>
       </div>
       <p class="message-text p-5">{{ item.text }}</p>
      </div>
    </section>
    <form
        @submit.prevent="sendMessage('in')"
        class="text-center flex flex-col bg-[#F2F2F2] pt-6 -mx-5"
      >
        <div class="mx-5">
          <label for="person1-input"></label>
          <input
              v-model="Message"
              id="person1-input"
              type="text"
              class="w-full p-5 btn-border rounded-sm h-[63px]"
          >
        </div>
        <button
            type="submit"
            class="bg-[#FDD639] btn rounded-2xl w-[17.5rem] m-auto my-10"
        >
          Send a message
        </button>
      </form>
  </div>
</template>

<script setup>
import {ref} from "vue";

const message = ref('')
const author = ref('')
const listMessages = ref([
  {
    text: 'Hey Eva! You\'re cool. Nice pic!',
    author: 'Samuel Jackson',
    date: '13 Apr 2022',
  },
  {
    text: 'Thanks for your services! We really liked the ocean view room.  We hope to cooperate in the near future. We are sure you will do everything to make our next holiday fantastic.',
    author: 'Angela Deimon',
    date: '10 Apr 2022',
  },
  {
    text: 'Eva, hello! There is such a question: How can I contact you if I am abroad in roaming?',
    author: 'Ronald Harris',
    date: '8 Apr 2022',
  }
])

const sendMessage = (direction) => {
  if (!Message.value.length) return
  if (direction === 'in') {
    listMessages.value.push({
      text: Message.value,
      author: 'Vasyl Diakovych',
      date: new Date().toDateString().slice(4, 20),
    })
    Message.value = ''
  } else {
    alert('something went wrong')
  }
}
</script>

<style scoped>
.message {
  margin-bottom: 38px;
  border-radius: 10px;
  font-size: .9em;
}

.message-text {
  background: #F2FBFF;
  box-shadow: 0px 4px 10px rgba(128, 128, 128, 0.1);
  border: 1px solid #C4CBCF;
  color: black;
}

.btn {
  padding: 12px 45px;
  color: #333333;
  font-size: clamp(14px, 2vw, 16px);
}
.btn-border {
  border: 1px solid #000000;
}
</style>
