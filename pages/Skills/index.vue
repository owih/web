<template>
  <div class="container">
    <div class="title-with-link animation animation_line-up">
      <h1 class="page-title inline-block mr-3 mb-0">
        {{ useDefaultLinks.skills.title }}
      </h1>
      <NuxtLink :to="useDefaultLinks.about.url" class="link">
        {{ useDefaultLinks.about.title }}
      </NuxtLink>
    </div>
    <section>
      <div class="xl:pt-20 animation animation_show">
        <SkillsPanel />
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
useHead({
  title: useDefaultLinks.skills.pageTitle,
  meta: [
    { name: 'description', content: useDefaultLinks.skills.description }
  ]
})
const { setSkillsToStore } = useSkillsStore()
const skills = await getSkillsFromApi()
setSkillsToStore(skills)
</script>
