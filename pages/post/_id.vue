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
                  <a :href="`/post/${related.id}`">{{related.title}}</a>
              </li>
          </ul>
      </aside>
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
                    },
                    {
                        id: 'ura',
                        title: 'What is Nuxt?',
                        content: 'Lorem Ipsum'
                    }
                ]
            }
        },
        computed: {
            post () {
                return this.posts.find(post => post.id === this.id)
            },
            relatedPosts () {
                return this.posts.filter(post => post.id !== this.id)
            }
        }
    }
</script>
