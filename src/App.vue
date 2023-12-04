<template>
  <div class="main-container">
    <my-comment :comments="comments"></my-comment>
    <!-- <comment-list :comments="comments"></comment-list> -->
    <my-input
      :current-user="currentUser"
      @newComment="createComment"
    ></my-input>
  </div>
</template>

<script>
import MyComment from "./components/MyComment";
import CommentList from "./components/CommentList.vue";
import MyInput from "./components/MyInput.vue";
export default {
  components: {
    MyComment,
    CommentList,
    MyInput,
  },
  data() {
    return {
      comments: [
        {
          id: 1,
          content:
            "Impressive! Though it seems the drag feature could be improved. But overall it looks incredible. You've nailed the design and the responsiveness at various breakpoints works really well.",
          createdAt: "1 month ago",
          score: 12,
          user: {
            image: {
              png: "images/avatars/image-amyrobson.png",
              webp: "images/avatars/image-amyrobson.webp",
            },
            username: "amyrobson",
          },
          replies: [
            {
              id: 3,
              content:
                "If you're still new, I'd recommend focusing on the fundamentals of HTML, CSS, and JS before considering React. It's very tempting to jump ahead but lay a solid foundation first.",
              createdAt: "1 week ago",
              score: 4,
              replyingTo: "maxblagun",
              user: {
                image: {
                  png: "images/avatars/image-ramsesmiron.png",
                  webp: "images/avatars/image-ramsesmiron.webp",
                },
                username: "ramsesmiron",
              },
            },
          ],
        },
        {
          id: 2,
          content:
            "Woah, your project looks awesome! How long have you been coding for? I'm still new, but think I want to dive into React as well soon. Perhaps you can give me an insight on where I can learn React? Thanks!",
          createdAt: "2 weeks ago",
          score: 5,
          user: {
            image: {
              png: "images/avatars/image-maxblagun.png",
              webp: "images/avatars/image-maxblagun.webp",
            },
            username: "maxblagun",
          },
          replies: [
            {
              id: 3,
              content:
                "If you're still new, I'd recommend focusing on the fundamentals of HTML, CSS, and JS before considering React. It's very tempting to jump ahead but lay a solid foundation first.",
              createdAt: "1 week ago",
              score: 4,
              replyingTo: "maxblagun",
              user: {
                image: {
                  png: "images/avatars/image-ramsesmiron.png",
                  webp: "images/avatars/image-ramsesmiron.webp",
                },
                username: "ramsesmiron",
              },
            },
            {
              id: 4,
              content:
                "I couldn't agree more with this. Everything moves so fast and it always seems like everyone knows the newest library/framework. But the fundamentals are what stay constant.",
              createdAt: "2 days ago",
              score: 2,
              replyingTo: "ramsesmiron",
              user: {
                image: {
                  png: "images/avatars/image-juliusomo.png",
                  webp: "images/avatars/image-juliusomo.webp",
                },
                username: "juliusomo",
              },
            },
          ],
        },
      ],
      currentUser: {
        image: {
          png: "./images/avatars/image-juliusomo.png",
          webp: "./images/avatars/image-juliusomo.webp",
        },
        username: "juliusomo",
      },
    };
  },
  methods: {
    createComment(comment) {
      this.comments.push(comment);
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Rubik:wght@400;500;700&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Rubik", sans-serif;
}
body {
  background-color: hsl(228, 33%, 97%);

  padding: 50px;
}
.main-container {
  margin: 0 auto;
  max-width: 700px;
  display: flex;
  flex-direction: column;
}
</style>
