<template>
  <div>
    <v-container class="my-10">
      <h2>{{ $t('Convert IIIF Manifest to Curation') }}</h2>
    </v-container>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component({
  components: {},
})
export default class about extends Vue {
  baseUrl: string = process.env.BASE_URL || ''

  head() {
    const title =
      this.$i18n.locale === 'ja'
        ? '東京大学史料編纂所'
        : 'Historiographical Institute The University of Tokyo'
    return {
      titleTemplate: null,
      title,
    }
  }
}
</script>
<style>
table th {
  border: 1px solid #ddd;
}
table td {
  border: 1px solid #ddd;
}
</style>
