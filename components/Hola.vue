<script setup>
const { data: posts } = await useAsyncData("posts", () =>
  $fetch("https://jsonplaceholder.typicode.com/posts")
);

const { pending, data: comments } = useLazyAsyncData("comments", () =>
  $fetch("https://jsonplaceholder.typicode.com/posts/1/comments")
);
watch(comments, (newComments) => {});

const allCaps = (asdf) => asdf.toUpperCase();
</script>
<template>
  <div>
    <HeadTitle />
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum unde quas
    quasi repellendus consequatur illo. Maxime est eveniet autem voluptatibus,
    dicta beatae id optio, laboriosam corrupti nulla, pariatur error fuga!
    <br />
    <br />
    <li v-for="post in posts">{{ post.title }}</li>
  </div>
  <hr />
  <div>
    <div v-if="pending">Loading......</div>
    <div v-else>
      <li v-for="comment in comments">{{ allCaps(comment.name) }}</li>
    </div>
  </div>
</template>
