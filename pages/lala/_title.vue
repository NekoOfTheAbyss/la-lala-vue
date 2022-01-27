<template>
  <div class="p-8">
    <div class="text-lg">
      <div
        class="
          flex
          md:flex-row md:space-x-12
          flex-col
          items-stretch
          md:justify-between
          justify-start
        "
      >
        <div class="py-2 w-full">
          <div
            class="
              p-2
              text-gray-700
              dark:text-white
              font-semibold
              border-zinc-400 border-b-2
            "
          >
            {{ article.title }}
          </div>
          <div class="p-4 text-sm">{{ formatDate(article.creat) }}</div>

          <div class="md:flex flex-row items-start justify-between px-2">
            <div class="flex flex-col items-start w-full md:w-auto order-2">
              <PageTable :news="article" />
            </div>
            <div class="flex flex-col items-start w-full order-1">
              <PageArticle :news="article" />
              <div class = "flex flex-col items-start justify-start">
            <div class = "p-3">
              {{result}}
            </div>
            <button
            class = "p-4 bg-zinc-600 text-white rounded-lg transition duration-500 ease-in-out transform hover:translate-y-1"
              @click="getResult"
            >
              Try it!
            </button>
          </div>
            </div>
          </div>
          
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import lala from '@/lala'
export default {
  head() {
    return {
      title: this.article.title,
      description: this.article.description,
    }
  },
  async asyncData({ params, $content }) {
    const article = await $content(`lala/${params.title}`).fetch()
    return {
      article,
      lala,
      result: "",
    }
  },
  methods: {
    formatDate(d) {
      return new Date(d).toUTCString()
    },
    getResult() {
      console.log(typeof this.lala.random[this.article.url])
      console.log(typeof this.lala.random.string)
      this.result = this.lala.random[this.article.url] ? this.lala.random[this.article.url]() : this.lala[this.article.url] ? new this.lala[this.article.url]() : 'Idk what to add here'
    }
  },
}
</script>
