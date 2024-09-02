<script setup>
const course=useCourse()
const route=useRoute()

const chapter=computed(()=>{
  return course.chapters.find(
    (chapter)=>chapter.slug===route.params.chapterSlug
  )
})

const lesson=computed(()=>{
  return chapter.value.lessons.find(
    (lesson)=>lesson.slug===route.params.lessonSlug
  )
})

</script>


<template>
  <div>
    <h1>{{chapter.title}}</h1>
    <p>{{lesson.title}}</p>
  </div>
</template>
