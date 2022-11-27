<template>
  <main class="LayoutMain">
    <ul v-if="response.data.value">
      <li v-for="newsInfo in newsInfos">
        {{ newsInfo.subject }}
      </li>
    </ul>
  </main>
</template>

<script setup lang="ts">
const response: any = await useFetch('https://afterworks.g.kuroco.app/rcms-api/5/news')
const newsInfos: any = response.data.value ? response.data.value.list : []
</script>
