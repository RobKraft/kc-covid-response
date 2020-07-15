<template>
  <Layout language="en">
    <OneColumnSection class="px-4 mt-8 md:mt-16">
      <h2 class="text-4xl">FAQs</h2>
      <p class="pb-8 italic md:bp-16 text-comebackkc-darkblue">Reliable information, trustworthy sources.</p>
      <p>
        Keep up to date on important information, COVID-19 updates, and news about testing and contact tracing throughout the KC metro area.
      </p>
    </OneColumnSection>
    <div class="bg-comebackkc-light-gray">
      <OneColumnSection class="py-16 text-white md:py-24">
        <div class="px-4">
          <h2 class="mb-4 text-3xl">FAQs</h2>
          <div v-for="faq in $page.faqs.edges" :key="faq.question" class="mb-8">
            <AccordionItem class="pb-8 border-b border-white" title-classes="font-bold text-2xl">
              <template v-slot:title>{{ faq.node.question }}</template>
              <template v-slot:body
                ><span v-html="styleRawHTML(faq.node.content, 'white')"></span
              ></template>
            </AccordionItem>
          </div>
        </div>
      </OneColumnSection>
      </div>
</Layout>
</template>

<script>
import FullWidthSection from '@/components/FullWidthSection.vue'
import OneColumnSection from '@/components/OneColumnSection.vue'
import PageHeader from '@/components/PageHeader.vue'
import AccordionItem from '@/components/AccordionItem.vue'
import { rawHtmlMixin } from '@/mixins/rawHtmlMixin.js'

export default {
  metaInfo: {
    title: 'FAQs',
    meta: [
      {
        key: 'description',
        name: 'description',
        content: 'Keep up-to-date on important information and updates about COVID-19 testing and contact tracing within the Kansas City metro area. Learn more here.'
      }
    ]
  },
  mixins: [rawHtmlMixin],
  components: { FullWidthSection, OneColumnSection, PageHeader, AccordionItem }
}
</script>

<page-query>
query {
  faqs: allFaq(filter: { language: { eq: "en" }}, sortBy: "order", order: ASC) {
    edges {
      node {
        question
        content
      }
    }
  } 
}
</page-query>

