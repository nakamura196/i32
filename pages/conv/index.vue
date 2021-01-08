<template>
  <div>
    <v-container class="my-10">
      <v-row>
        <v-col cols="12" sm="6">
          <v-card>
            <v-card-title class="headline grey lighten-2">{{
              $t('IIIF Manifest -> Curation')
            }}</v-card-title>
            <v-card-text class="py-5"
              ><v-text-field
                v-model="manifest"
                :label="$t('Manifest URI')"
                required
              ></v-text-field>

              <v-btn color="primary" @click="validate">{{
                $t('Submit')
              }}</v-btn>

              <v-simple-table class="mt-10">
                <template v-slot:default>
                  <thead>
                    <tr>
                      <th class="text-left">{{ $t('Example') }}</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr>
                      <td>
                        <nuxt-link
                          :to="
                            localePath({
                              name: 'conv-convert2curation',
                              query: {
                                manifest:
                                  'https://dzkimgs.l.u-tokyo.ac.jp/iiif/zuzoubu/04/manifest.json',
                              },
                            })
                          "
                          >大正新脩大藏經図像部第4巻</nuxt-link
                        >（SAT大正蔵図像DB）
                      </td>
                    </tr>
                    <tr v-if="false">
                      <td>
                        <a
                          href="convert2curation?manifest=https://dzkimgs.l.u-tokyo.ac.jp/iiif/zuzoubu/04/manifest.json"
                          >大正新脩大藏經図像部第4巻</a
                        >（SAT大正蔵図像DB）
                      </td>
                    </tr>
                  </tbody>
                </template>
              </v-simple-table>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
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
