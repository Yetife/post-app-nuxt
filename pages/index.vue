<template>
  <div>
    <navbar />
    <div class="blogs-page">
      <div class="main-content">
        <div class="container">
          <div class="columns is-mobile">
            <div class="column is-8 is-offset-2">
              <div class="section">
                <div class="title">
                  <h1>Newest Posts</h1>
                  <hr>
                </div>
                <PostItem
                  v-for="post in posts"
                  :key="post._id"
                  :title="post.title"
                  :subtitle="post.subtitle"
                  :date="post.createdAt",
                  :isRead="post.isRead"
                />
              </div>
              <!-- end of post -->
            </div>
            <!-- end of side bar -->
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '~/components/Navbar'
import PostItem from "~/components/PostItem";
export default {
  name: 'IndexPage',
  components: {
    Navbar, PostItem
  },
  data(){
    return{
      title: 'My title from page',
    }
  },
  computed:{
    posts(){
      return this.$store.state.posts
    }
  }
}
</script>
<style>

</style>
