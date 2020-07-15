<template>
  <Layout language="en">
    <OneColumnSection class="pt-16 pb-4 md:pt-32 md:pb-8">
      <h2 class="px-4 text-3xl lg:px-4">Fight COVID-19 With Your Phone</h2>
    </OneColumnSection>
    <TwoColumnSection order="reversed">
      <template v-slot:column1>
        <div class="px-4 pb-16 md:pr-16">
          <p>
            Safe. Secure. Private. COVID Safe Paths, a free app, lets you see where you’ve been and alerts you if you've been exposed to COVID-19.
          </p>
          <ul class="mb-8 ml-5 list-disc">
            <li>Find out if you’ve been exposed</li>
            <li>Privately log your location</li>
            <li>Completely control your data</li>
          </ul>
          <p>
            <a id="play-store-download" href="https://play.google.com/store/apps/details?id=org.pathcheck.covidsafepaths&hl=en_US" target="_blank">
              <img class="inline-block mb-4 mr-4" src="/images/google-play.png" alt="Google Play store button" />
            </a>
            <a id="app-store-download" href="https://apps.apple.com/us/app/covid-safe-paths/id1508266966" target="_blank">
              <img class="inline-block mb-4" src="/images/app-store.png" alt="Apple store button" />
            </a>
          </p>
          <p class="mb-16">
            <a href="https://covidsafepaths.org/" target="_blank" class="underline text-comebackkc-darkblue">Learn more about the COVID Safe Paths app</a>
          </p>
        </div>
      </template>
      <template v-slot:column2>
        <div class="flex flex-col items-center justify-end h-full px-4 pb-8 md:pb-0">
          <g-image class="" src="~/images/safe-paths-app-screens.png" alt="Safe Paths app screenshot" />
        </div>
      </template>
    </TwoColumnSection>
      </Layout>
</template>

<script>
import FullWidthSection from '@/components/FullWidthSection.vue'
import OneColumnSection from '@/components/OneColumnSection.vue'\
import TwoColumnSection from '@/components/TwoColumnSection.vue'
import PageHeader from '@/components/PageHeader.vue'
import { rawHtmlMixin } from '@/mixins/rawHtmlMixin.js'

export default {
  metaInfo: {
    title: 'Downloads',
    meta: [
      {
        key: 'description',
        name: 'description',
        content: 'Keep up-to-date on important information and updates about COVID-19 testing and contact tracing within the Kansas City metro area. Learn more here.'
      }
    ]
  },
  mixins: [rawHtmlMixin],
  components: { FullWidthSection, OneColumnSection, TwoColumnSection, PageHeader }
}
</script>

