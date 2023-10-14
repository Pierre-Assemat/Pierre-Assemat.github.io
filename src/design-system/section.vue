<script setup lang="ts">
  import SectionItem from './section-item.vue';
  type Props = {
    name: string
  }
  const props = defineProps<Props>()
</script>

<template>
  <section>
    <div class="section-header">
      <h2>{{ props.name }}</h2>
    </div>
    <div>
      <slot>
        <SectionItem title="Title" description="Item section => Todo" />
      </slot>
    </div>
  </section>
  
</template>

<style scoped>
.section-header {
  padding: 8px 16px;
  border-radius: 4px;

  background-color: blue;
  color: white;
}
</style>