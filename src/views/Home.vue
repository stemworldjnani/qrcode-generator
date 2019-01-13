<template lang="pug">
dl.home
  dt URL
  dd
    input(type="text", v-model="url", size="80")
  dt QRCode
  dd
    QRCode(:url="url")
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import QRCode from "@/components/QRCode.vue";

@Component({
  components: { QRCode }
})
export default class Home extends Vue {
  url = ''
}
</script>


<style lang="scss" scoped>
</style>
