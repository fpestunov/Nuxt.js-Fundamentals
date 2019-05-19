<template>
  <div class="container">
    <article>
      <h1 class="title">{{post.title}}</h1>
      <p>{{post.content}}</p>
    </article>
    <aside>
      <h3>Posts you might enjoy</h3>
      <ul>
        <li v-for="related in relatedPosts">
          <nuxt-link :to="{name: 'posts-id', params: {id: related.id}}">
            {{related.title}}
          </nuxt-link>
        </li>
      </ul>
    </aside>   

    <aside>
      <h3>Posts you might enjoy 2</h3>
      <ul>
        <li v-for="post in posts">
          <nuxt-link :to="{name: 'posts-id', params: {id: post.id}}" :key="post.id">
            {{post.title}}
          </nuxt-link>
        </li>
      </ul>
    </aside>   
  </div>
</template>

<script>
  export default {
    data () {
      return {
        id: this.$route.params.id
      }
    },
    computed: {
      post () {
        // return this.posts.find(post => post.id === this.id)
        return this.$store.state.posts.all.find(post => post.id === this.id)
      },
      relatedPosts () {
        // return this.posts.filter(post => post.id !== this.id)
        this.$store.state.posts.all.filter(post => post.id !== this.id)
      },
      posts() {
        return this.$store.state.posts.all
      }
    }
  }
</script>

<style scoped>
  .container {
    display: flex;
    justify-content: space-between;
    line-height: 1.5;
  }
  article * {
    margin-bottom: 1rem;
  }
  aside {
    min-width: 280px;
    max-width: 280px;
    padding-left: 2rem;
  }
  .title {
    font-size: 2rem;
  }
</style>
