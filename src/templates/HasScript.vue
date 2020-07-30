<template v-on:load="forceRerender">
  <Layout>
    <OneColumnSection class="px-4 my-8 md:my-16">
      <div class="my-8 md:my-16">
        <h2 class="text-5xl" v-html="$page.hasScript.title"></h2>
      </div>
    </OneColumnSection>
    <VueRemarkContent />
  </Layout>
</template>

<script>
import OneColumnSection from '@/components/OneColumnSection.vue'
import { rawHtmlMixin } from '@/mixins/rawHtmlMixin.js'


export default {
  metaInfo() {
    return {
      title: this.$page.hasScript.title,
      meta: [{ key: 'description', name: 'description', content: this.$page.hasScript.metaDescription },{ key: 'og:title', name: 'og:title', content: this.$page.hasScript.title },{ key: 'og:description', name: 'og:description', content: this.$page.hasScript.ogDescription },{ key: 'og:image', name: 'og:image', content: 'https://comebackkc.com' + this.$page.hasScript.ogImage }]
    }
  },
  mixins: [rawHtmlMixin],
  components: { OneColumnSection }
}
</script>

<page-query>
query ($id: ID!) {
  hasScript(id: $id) {
    title
    metaDescription
    content
  }
}
</page-query>