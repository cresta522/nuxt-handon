<template>
  <div class="sample">
    <h1>{{ title }}</h1>
    <div class="sample">Hello , {{ name }}</div>
    <div class="reversed">reversed name is {{ reverseName }}</div>
    <div class="num">count is {{ num }}</div>
    <div :class="[{ 'd-none': num !== 7 }]">click 7 times</div>
    <button type="button" class="btn" @click="plus()">加算</button>

    <div><slot /></div>
    <div class="blue">
      <slot name="named" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Default Title',
    },
  },
  data() {
    return {
      name: 'konagaya',
      num: 0,
    }
  },
  computed: {
    // computedはキャッシュされるため、プロパティが変化しなかったら実行されない
    reverseName() {
      // not void
      return this.name.split('').reverse().join('')
    },
  },
  methods: {
    plus() {
      // void型？
      this.num++
    },
  },
}
</script>
