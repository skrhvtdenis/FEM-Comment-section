<template>
  <div class="item-list" v-for="comment in comments">
    <div class="comment-item">
      <div class="rating">
        <button class="btn">
          <svg width="11" height="11" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M6.33 10.896c.137 0 .255-.05.354-.149.1-.1.149-.217.149-.354V7.004h3.315c.136 0 .254-.05.354-.149.099-.1.148-.217.148-.354V5.272a.483.483 0 0 0-.148-.354.483.483 0 0 0-.354-.149H6.833V1.4a.483.483 0 0 0-.149-.354.483.483 0 0 0-.354-.149H4.915a.483.483 0 0 0-.354.149c-.1.1-.149.217-.149.354v3.37H1.08a.483.483 0 0 0-.354.15c-.1.099-.149.217-.149.353v1.23c0 .136.05.254.149.353.1.1.217.149.354.149h3.333v3.39c0 .136.05.254.15.353.098.1.216.149.353.149H6.33Z"
              fill="#C5C6EF"
            />
          </svg>
        </button>
        <p v-bind:score="comment.score">{{ comment.score }}</p>
        <button class="btn">
          <svg width="11" height="3" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M9.256 2.66c.204 0 .38-.056.53-.167.148-.11.222-.243.222-.396V.722c0-.152-.074-.284-.223-.395a.859.859 0 0 0-.53-.167H.76a.859.859 0 0 0-.53.167C.083.437.009.57.009.722v1.375c0 .153.074.285.223.396a.859.859 0 0 0 .53.167h8.495Z"
              fill="#C5C6EF"
            />
          </svg>
        </button>
      </div>
      <div class="comment">
        <div class="comment-header">
          <div class="header-info">
            <img :src="comment.user.image.png" alt="profile-pic" />
            <p class="name">{{ comment.user.username }}</p>
            <p class="text">{{ comment.createdAt }}</p>
          </div>
          <button @click="wtf" class="reply-btn">
            <svg
              width="14"
              height="13"
              xmlns="http://www.w3.org/2000/svg"
              class="reply-btn-svg"
            >
              <path
                d="M.227 4.316 5.04.16a.657.657 0 0 1 1.085.497v2.189c4.392.05 7.875.93 7.875 5.093 0 1.68-1.082 3.344-2.279 4.214-.373.272-.905-.07-.767-.51 1.24-3.964-.588-5.017-4.829-5.078v2.404c0 .566-.664.86-1.085.496L.227 5.31a.657.657 0 0 1 0-.993Z"
                fill="#5357B6"
              />
            </svg>
            Reply
          </button>
        </div>
        <p class="text">
          {{ comment.content }}
        </p>
      </div>
    </div>
    <div class="comment-item reply-item" v-for="reply in comment.replies">
      <div class="rating">
        <button class="btn">
          <svg width="11" height="11" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M6.33 10.896c.137 0 .255-.05.354-.149.1-.1.149-.217.149-.354V7.004h3.315c.136 0 .254-.05.354-.149.099-.1.148-.217.148-.354V5.272a.483.483 0 0 0-.148-.354.483.483 0 0 0-.354-.149H6.833V1.4a.483.483 0 0 0-.149-.354.483.483 0 0 0-.354-.149H4.915a.483.483 0 0 0-.354.149c-.1.1-.149.217-.149.354v3.37H1.08a.483.483 0 0 0-.354.15c-.1.099-.149.217-.149.353v1.23c0 .136.05.254.149.353.1.1.217.149.354.149h3.333v3.39c0 .136.05.254.15.353.098.1.216.149.353.149H6.33Z"
              fill="#C5C6EF"
            />
          </svg>
        </button>
        <p>{{ reply.score }}</p>
        <button class="btn">
          <svg width="11" height="3" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M9.256 2.66c.204 0 .38-.056.53-.167.148-.11.222-.243.222-.396V.722c0-.152-.074-.284-.223-.395a.859.859 0 0 0-.53-.167H.76a.859.859 0 0 0-.53.167C.083.437.009.57.009.722v1.375c0 .153.074.285.223.396a.859.859 0 0 0 .53.167h8.495Z"
              fill="#C5C6EF"
            />
          </svg>
        </button>
      </div>
      <div class="comment">
        <div class="comment-header">
          <div class="header-info">
            <img :src="reply.user.image.png" alt="profile-pic" />
            <p class="name">{{ reply.user.username }}</p>
            <p class="text">{{ reply.createdAt }}</p>
          </div>
          <button @click="wtf" class="reply-btn">
            <svg
              width="14"
              height="13"
              xmlns="http://www.w3.org/2000/svg"
              class="reply-btn-svg"
            >
              <path
                d="M.227 4.316 5.04.16a.657.657 0 0 1 1.085.497v2.189c4.392.05 7.875.93 7.875 5.093 0 1.68-1.082 3.344-2.279 4.214-.373.272-.905-.07-.767-.51 1.24-3.964-.588-5.017-4.829-5.078v2.404c0 .566-.664.86-1.085.496L.227 5.31a.657.657 0 0 1 0-.993Z"
                fill="#5357B6"
              />
            </svg>
            Reply
          </button>
        </div>
        <p class="text">
          {{ comment.content }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    comments: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {};
  },
  methods: {
    checkIf() {
      console.log(comments);
    },
  },
};
</script>

<style scoped>
.item-list {
  display: flex;
  align-items: center;
  flex-direction: column;
}
.comment-item {
  width: 100%;
  background-color: #fff;
  padding: 20px;
  margin-bottom: 10px;
  border-radius: 20px;
  display: flex;
  align-items: center;
  flex-direction: row;
  justify-content: space-between;
}

.reply-item {
  width: 90%;
  align-self: flex-end;
}

.rating {
  margin-right: 10px;
  background-color: hsl(228, 33%, 97%);
  padding: 10px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: space-around;
  flex-direction: column;
}

.btn {
  border: none;
  margin: 5px 0;
  background-color: hsl(228, 33%, 97%);
}
.btn:hover {
  cursor: pointer;
}
.btn:hover path {
  fill: #9596f3;
}

.rating p {
  font-size: 1.25rem;
  color: hsl(240, 32%, 39%);
  font-weight: 500;
}

.comment-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.header-info {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 10px;
}
.comment-header img {
  width: 30px;
  height: 30px;
  margin-right: 10px;
}

.text {
  font-size: 1rem;
  color: hsl(211, 10%, 45%);
}
.name {
  margin-right: 10px;
}
.reply-btn {
  border: none;
  background-color: #fff;
  text-align: center;
  font-size: 1rem;
  color: hsl(240, 32%, 39%);
  font-weight: 700;
}
.reply-btn:hover {
  color: #c3c4ef;
  cursor: pointer;
}

.reply-btn:hover path {
  fill: #c3c4ef;
}
</style>
