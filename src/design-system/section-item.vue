<script setup lang="ts">
  type Skill = {
    id: string
    label: string
  }

  type Props = {
    title: string
    description?: string
    skills?: Skill[]
  }
  const props = withDefaults(defineProps<Props>(), {
    description: undefined,
    skills: undefined
  })
</script>

<template>
  <div class="section-item">
    <span class="item-title">{{ props.title }}</span>
    <span v-if="props.description" class="item-description">{{ props.description }}</span>
    <div v-if="props.skills" class="skills-section">
      <span>Skills gained</span>
      <ul>
        <li v-for="skill in props.skills" :key="skill.id">{ skill.label }</li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
  .section-item {
    display: flex;
    flex-direction: column;
  }

  .item-title {
    font-size: 1.4dvw;
    font-weight: bold;
  }
  .item-description {
    font-size: 1dvw;
  }
  .skills-section{
    /* TODO */
  }
</style>