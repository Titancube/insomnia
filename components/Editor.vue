<template>
  <div class="w-full">
    <!-- Date -->
    <div class="w-full p-4 flex justify-center">
      <span class="text-3xl font-bold">{{ date }}</span>
    </div>
    <!-- Title -->
    <div class="w-full p-4 flex justify-center">
      <input
        type="text"
        :value="title"
        placeholder="제목"
        class="px-4 py-2 rounded-md text-xl font-bold outline-none focus:outline-none w-2/3 shadow-md shadow-slate-400"
      />
    </div>
    <!-- Content -->
    <div action="" class="w-full p-4 flex justify-center">
      <textarea
        name="diaryContent"
        id="diaryContent"
        v-html="content"
        class="px-4 py-2 rounded-md outline-none focus:outline-none w-2/3 resize-none shadow-md shadow-slate-400"
      ></textarea>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'nuxt-property-decorator'
import { format } from 'date-fns'
import { ko } from 'date-fns/locale'

@Component
export default class Editor extends Vue {
  date = format(new Date(), 'yyyy년 MM월 dd일', { locale: ko })
  title: string = ''
  content: string = ''
}
</script>

<style scoped lang="postcss">
#diaryContent {
  min-height: 400px;
}
</style>
