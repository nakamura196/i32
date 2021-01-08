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
  layout: 'conv',
  components: {},
})
export default class about extends Vue {
  baseUrl: string = process.env.BASE_URL || ''

  head() {
    const title = this.$t('IIIF Converter')
    return {
      titleTemplate: null,
      title,
    }
  }
}
</script>
