<template>
  <div v-if="headings.length > 0" class="sticky top-8">
    <h3
      class="font-semibold text-gray-400 text-xs uppercase tracking-widest font-sans"
    >
      Contents
    </h3>

    <nav class="mt-3 space-y-1">
      <NavLink
        v-for="heading in headings"
        :to="`#${heading.id}`"
        :key="heading.id"
        :class="{ 'pl-6': heading.depth === 3 }"
      >
        {{ heading.text }}
      </NavLink>
    </nav>
  </div>
</template>

<script>
export default {
  props: {
    headings: { default: () => [] },
  },
};
</script>
