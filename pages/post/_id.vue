<template>
  <div class="container">
      <article>
          <h1 class="title">{{post.title}}</h1>
          <p>{{post.content}}</p>
      </article>
  </div>
</template>
<script>
    export default {
        data () {
            return {
                id: this.$route.params.id,
                posts: [
                    {
                        id: 'balut',
                        title: 'What is Balut?',
                        content: 'Lorem Ipsum'
                    },
                    {
                        id: 'WhereIsIt',
                        title: 'Where is the signin button?',
                        content: 'Lorem Ipsum'
                    }
                ]
            }
        },
        computed: {
            post () {
                return this.posts.find(post => post.id === this.id)
            }
        }
    }
</script>
