<template>
  <section class="container">
    <div>
      <logo />
      <h1 class="title">
        nuxt app
      </h1>
      <h2 class="subtitle">
        My first Nuxt.js project
      </h2>
      <div class="links">
      <ul>
        <li><a
          href="/posts/how"
        >Posts</a></li>
        <li><a
          href="https://nuxtjs.org/"
          target="_blank"
        >Documentation</a></li>
        <li><a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
        >GitHub</a></li>
        </ul>
      </div>
      <div class="links">
        <nuxt-link
          v-for="post in posts"
          :to="{name: 'posts-id', params: {id: post.id}}"
          :key="post.id"
          class="button--grey"
        >
          {{post.title}}
        </nuxt-link>
      </div>      
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  head () {
    return {
      title: 'Home Page +',
      meta: [
        { name: 'twitter:title', content: 'Nuxt Fundamentals'},
        { name: 'twitter:description', content: 'Nuxt + Vue = 🍕'}
      ]      
    }
  },
  computed: {
    posts () {
      return this.$store.state.posts.all
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
  text-align: left;
}
</style>
