<template>
<div>
    <div class = 'header'>
        <button @click='toggleCreate'>CREATE</button>
        <h2>Battle Bots</h2>
        <button @click='toggleCollection'>COLLECTION</button>
    </div>
    <div>
        <section v-if='changePage'>
        <create
          :addNewBot='addNewBot'
        ></create> 
        </section>

        <section v-else>
        <collection
         :botgroup='bots'
        ></collection>
        </section>
     </div>
  </div>
</template>

<script>
import Create from "./components/Create";
import Collection from "./components/Collection";

export default {
  data() {
    return {
      changePage: true,
      bots: [
        {
          botName: "Leo",
          attackVal: 30,
          healthVal: 20
        },
        {
          botName: "Line",
          attackVal: 40,
          healthVal: 10
        },
        {
          botName: "Lea",
          attackVal: 10,
          healthVal: 40
        }
      ]
    };
  },
  methods: {
    toggleCreate() {
      this.changePage = true;
    },
    toggleCollection() {
      this.changePage = false;
    },
    addNewBot(botName, attackVal, healthVal) {
      let newB = {
        botName: botName,
        attackVal: attackVal,
        healthVal: healthVal
      };
      this.bots.push(newB);
    }
  },
  components: {
    Create: Create,
    Collection: Collection
  }
};
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-around;
  width: 100%;
  padding-bottom: 5px;
  border-bottom: solid grey 1px;
}
h2 {
  font-family: Arial;
}
</style>


    <!-- <h1>Frenchie's Blog</h1>
    <button @click='toggleForm'>Create new post</button>
    <button @click='togglePosts'>All Posts</button>
    <section v-if='showForm'>
        <h3>Create New Post:</h3>    

        <form @submit.prevent='addNewPost'>
          <p>Author: <input v-model='author' type="text"></p>
          <p>Post:</p>
          <textarea v-model='newPost' cols="30" rows="10"></textarea>
          <button>Create</button>
        </form>  
        
    </section>
    <section v-else>
      <h3>Look at all most blog posts:</h3>
      <div v-for='post in posts' :key='post.id'>
        <post
        :postProp= 'post'
        ></post>
      </div>

    </section>
  </div>
</template>

<script>
import Post from "./components/Post";
export default {
  data() {
    // think of the object below as 'this.state' for react
    return {
      posts: [{ id: 1, post: "Hey I am a blog" }],
      id: 1,
      showForm: true,
      author: "",
      newPost: ""
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
      this.author = "";
      this.newPost = "";
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
</style> -->
