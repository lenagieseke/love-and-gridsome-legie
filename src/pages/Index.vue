<template>
  <Layout>

    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image alt="Example image" src="~/favicon.png" width="135" />

    <h1>All Posts</h1>
    <ul>
    <li v-for="post in $page.allBlogPost.edges" :key="post.node.id">
        <a :href="post.node.path">{{ post.node.title }} (posted on {{ post.node.date}})</a>
    </li>
    </ul>

    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur excepturi labore tempore expedita, et iste tenetur suscipit explicabo! Dolores, aperiam non officia eos quod asperiores
    </p>

    <p class="home-links">
      <a href="https://gridsome.org/docs/" target="_blank" rel="noopener">Gridsome Docs</a>
      <a href="https://github.com/gridsome/gridsome" target="_blank" rel="noopener">GitHub</a>
    </p>

  </Layout>
</template>

<page-query>
query{
    allBlogPost{
      edges{
        node{
            id
            path
            title
            date(format: "MMMM DD, YYYY")
        }
      }
    }
}
</page-query>



<script>
export default {
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
