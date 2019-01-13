<template lang="pug">
  canvas(ref="canvas")
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";
import QRious from 'qrious'

@Component
export default class extends Vue {
  @Prop({ required: true })
  url!: string

  mounted() {
    this.$watch('url', url => {
      new QRious({
        element: this.$refs.canvas,
        value: url
      })
    }, { immediate: true })
  }
}
</script>