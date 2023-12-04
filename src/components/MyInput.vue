<template>
  <div>
    <div class="input-container">
      <img :src="currentUser.image.png" alt="" />

      <textarea
        placeholder="Add a comment..."
        name="comment"
        id=""
        cols="30"
        rows="10"
        v-model="comment.content"
      ></textarea>
      <button @click="createComment">SEND</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    currentUser: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      comment: {
        id: Math.floor(Math.random() * Date.now()),
        content: "",
        createdAt: "",
        score: 0,
        user: {
          image: {
            png: this.currentUser.image.png,
            webp: this.currentUser.image.webp,
          },
          username: this.currentUser.username,
        },
        replies: [],
      },
    };
  },
  methods: {
    createComment() {
      this.createdAt = Date.now();
      this.$emit("newComment", this.comment);
      this.comment = {
        id: Math.floor(Math.random() * Date.now()),
        content: "",
        createdAt: "",
        score: 0,
        user: {
          image: {
            png: this.currentUser.image.png,
            webp: this.currentUser.image.webp,
          },
          username: this.currentUser.username,
        },
        replies: [],
      };
    },
  },
};
</script>

<style scoped>
.input-container {
  width: 100%;
  background-color: #fff;
  padding: 20px;
  /* margin-bottom: 15px; */
  border-radius: 20px;
  display: flex;
  align-items: flex-start;
  flex-direction: row;
  justify-content: space-around;
}

img {
  width: 2.5rem;
  height: 2.5rem;
  margin-right: 10px;
}

textarea {
  width: 70%;
  height: 5rem;
  border: 1px solid rgba(0, 0, 0, 0.075);
  border-radius: 10px;
  color: hsl(211, 10%, 45%);
  opacity: 0.7;
  text-align: start;
  padding: 10px;
}

textarea:focus,
input:focus {
  outline: 1px solid rgba(0, 0, 0, 0.212);
  opacity: 1;
}
button {
  width: 15%;
  height: 2.5rem;
  background-color: #5358b6;
  color: #fff;
  border: none;
  border-radius: 10px;
  font-weight: 500;
  transition: 0.3s;
  opacity: 0.8;
}

button:hover {
  cursor: pointer;
  opacity: 1;
}
</style>
