<template>
  <NuxtLayout>
    <div v-if="error.statusCode === '404'" class="prose">
      <h1>404</h1>
      <p>It looks like this page doesn't exist.</p>
    </div>
    <div v-else class="prose">
      <h1>Dang</h1>
      <p>It looks like something broke.</p>
      <p>Sorry about that.</p>
    </div>
    <div class="prose">
      <strong>{{ error.message }}</strong>
      <p>
        Go to the
        <a class="hover:cursor-pointer" @click="handleError">First lesson</a>
      </p>
    </div>
  </NuxtLayout>
</template>

<script setup>
const error = useError();

const handleError = () => {
clearError({
  redirect: '/course/chapter/1-chapter-1/lesson/1-introduction-to-typescript-with-vue-3',
});
};
</script>
