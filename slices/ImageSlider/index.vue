<template>
  <section class="section">
    <prismic-rich-text :field="slice.primary.title" class="title" />
    <prismic-rich-text :field="slice.primary.description" />
    <prismic-image :field="slice.primary.mainimage" />
    <ix-img :src="slice.primary.mainimage.url" :field="slice.primary.mainimage" sizes="400px"/>
    <prismic-image v-for="items in slice.items" :key="items.imageslider.url" :field="items.imageslider"/>
  </section>
</template>
<script>
import VueImgix from '../../plugins/vue-imgix'

export default {
  props: {
    slice: {
      type: Object,
      required: true,
      default() {
        return {}
      }
    }
  },
}
</script>
<style scoped>
.section {
  position: relative;
  background: #F7F7F7;
  color: #111;
  padding: 4em;
  text-align: center;
}
a {
  color: #111;
}
.title {
  margin-bottom: 2em;
}
</style>

