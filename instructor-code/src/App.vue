<template>
  <div>
    <h1>Bob Loblaw's Law Blogs</h1>
    <button @click='toggleForm'>Create new post</button>
    <button @click='togglePosts'>All Posts</button>
    <section v-if='showForm'>
        <h3>Create New Post:</h3> 

        <form @submit.prevent='addNewPost'>
          <p>Author: <input v-model='author' type="text"></p>  
          <p>Post:</p>
          <textarea v-model='newPost' cols="30" rows="10"></textarea>
          <button >Create</button>
        </form> 

    </section>
    <section v-else>
      <h3>Look at all most blog posts:</h3>

      <div v-for='post in posts' :key='post.id'>
        <post 
          :postProp='post' 
          myName='joe'
        ></post>
      </div>

    </section>
  </div>
</template>

<script>
import Post from './components/Post';
export default {
  data() {
    // think of the object below as 'this.state' for react
    return {
      posts: [{ id: 1, post: 'Hey im a blog', author: 'Joe' }],
      id: 1,
      showForm: true,
      author: '',
      newPost: ''
    };
  },
  methods: {
    toggleForm() {
      this.showForm = true;
    },
    togglePosts() {
      this.showForm = false;
    },
    addNewPost() {
      this.id++;
      let newP = {
        id: this.id,
        author: this.author,
        post: this.newPost
      };
      this.posts.push(newP);
      this.author = '';
      this.newPost = '';
      this.togglePosts();
    }
  },
  components: {
    Post: Post
  }
};
</script>

<style scoped>
.color {
  background: pink;
}
</style>

