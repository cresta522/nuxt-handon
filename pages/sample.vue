<template>
  <div class="container">
    <!-- コンポーネントのpropsに渡る -->
    <!-- コンポーネントのpropsのtitleにバインドする  -->
    <sample :title="indexTitle">
      <!-- Slot: コンポーネントにあとから渡す値 -->
      Hello Slot!
      <div slot="named">named slot</div>
    </sample>
    <div class="">
      <nuxt-link to="/about">ABOUT</nuxt-link>
    </div>
  </div>
</template>

<script>
import Sample from '@/components/Sample.vue'
export default {
  components: {
    Sample,
  },
  data() {
    return {
      indexTitle: 'Nuxt.js',
    }
  },
}
</script>
