<script setup>
const { data: posts } = await useAsyncData("posts", () =>
  $fetch("https://jsonplaceholder.typicode.com/posts")
);

const { data: post } = await useAsyncData("post", () =>
  $fetch(
    `https://jsonplaceholder.typicode.com/posts/${Math.floor(
      Math.random() * 10
    )}`
  )
);

// fetch('https://jsonplaceholder.typicode.com/posts/1')

const { pending, data: comments } = useLazyAsyncData("comments", () =>
  $fetch("https://jsonplaceholder.typicode.com/posts/1/comments")
);

const allCaps = (asdf) => asdf.toUpperCase();
</script>
<template>
  <div>
    <HeadTitle />

    <h1 class="fs-1 text-primary text-uppercase text-center py-4">
      {{ post.title }}
    </h1>
    <p class="fs-2">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum unde quas
      quasi repellendus consequatur illo. Maxime est eveniet autem voluptatibus,
      dicta beatae id optio, laboriosam corrupti nulla, pariatur error fuga!
    </p>

    <li v-for="post in posts" class="col-12 col-md-9 offset-md-3">
      {{ post.title }}
    </li>
  </div>
  <hr />
  <div class="pb-5">
    <div v-if="pending">Loading......</div>
    <div v-else>
      <li v-for="comment in comments" class="text-success">
        {{ allCaps(comment?.name) }}
      </li>
    </div>
  </div>
</template>
