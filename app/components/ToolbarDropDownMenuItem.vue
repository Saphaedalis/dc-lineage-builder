<template>
  <component
    :is="as === 'button' ? 'button' : props.as"
    :type="as === 'button' ? 'button' : null"
    v-bind="$attrs"
    class="menu-item"
    role="menuitem"
  >
    <slot />
  </component>
</template>

<script setup lang="ts">
import type { PropType } from 'vue';

const props = defineProps({
  as: {
    type: String as PropType<'button' | string>,
    default: 'button',
  },
});
</script>

<style scoped>
.menu-item {
  border: none;
  display: block;
  background: inherit;
  color: inherit;
  text-align: left;
  padding: 10px;
  cursor: pointer;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow: hidden;

  &:hover {
    background: rgba(255, 255, 255, 0.25);
  }
}
</style>
