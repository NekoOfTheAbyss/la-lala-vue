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
              border-gray-400 border-b-2
            "
          >
            Recent Posts:
          </div>
          <ul class="flex flex-col items-start w-full px-2 list-disc list-inside">
            <li v-for="article in articles" :key="article.url.toLowerCase()">
              <NuxtLink :to="`/guides/${article.url.toLowerCase()}`"
                >{{ article.title }}           <span class="p-4 text-sm">{{ formatDate(article.creat) }}</span>

              </NuxtLink>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    function getMS(d) {
      return new Date(d).getTime()
    }
    let articles = await $content('blog').fetch()
    if(Array.isArray(articles)) articles = articles.sort((a, b) => getMS(a.creat) - getMS(b.creat)).reverse()
    else articles = [articles]
    return {
      articles,
    }
  },
  methods: {
    formatDate(d) {
      return new Date(d).toUTCString()
    }
  }
}
</script>
