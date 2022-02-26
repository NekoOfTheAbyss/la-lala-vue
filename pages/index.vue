<template>
  <div class="p-8">
    <div class="text-lg">
      <div class="
          flex
          md:flex-row md:space-x-12
          flex-col
          items-stretch
          md:justify-between
          justify-start
        ">
        <div class="py-2 w-full">
          <div class="
              p-2
              text-gray-700
              dark:text-white
              font-semibold
              border-gray-400 border-b-2
            ">
            Stuff:
          </div>
          <PageArticle :news="articlex" />
          <div class = "md:flex flex-row justify-between items-start space-y-4 md:space-y-0 md:space-x-4">
          <ul class="flex flex-col items-start w-full px-2 space-y-4">
            <li
              v-for="article in articles"
              :key="article.name.toLowerCase()"
              class="p-2 w-full"
            >
              <a
                href="javascript:void(0)"
                @click="x => setEnabled(article.name.toLowerCase())"
                class="p-2 max-w-6xl md:max-w-md w-full block bg-nett-matchpurple text-nett-maid font-semibold text-center"
              >{{ article.name.split("-").map(s => s.charAt(0).toUpperCase() + s.slice(1).toLowerCase()).join(" ") }}
              </a>
            </li>
          </ul>
          <div class="py-2 w-full">
            <PageTrial
              v-if="enabled"
              :modez="modez"
            />
          </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import articles from '@/data/Features'
export default {
  head() {
    return {
      title: 'Lala Docs',
      description:
        'A collection of random useful (probably) javascript classes and functions.',
    }
  },
  async asyncData({ $content }) {
    const articlex = await $content('main/lala').fetch()
    return {
      articles,
      enabled: false,
      modez: null,
      articlex,
    }
  },
  methods: {
    formatDate(d) {
      return new Date(d).toUTCString()
    },
    setEnabled(s) {
      this.$nuxt.$loading.start()
      this.enabled = false
      this.modez = s
      setTimeout(() => {
        this.enabled = true
        this.$nuxt.$loading.finish()
      }, 500)
    },
    getEnabled() {
      return this.enabled
    },
  },
}
</script>
