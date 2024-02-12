<script setup lang="ts">
import { computed } from "vue";
type BaseButtonProps = {
  size?: number;
  color?: string;
};

const props = withDefaults(defineProps<BaseButtonProps>(), {
  size: 16,
  color: "skyblue",
});

const fontSize = computed(() => `${props.size}px`);
</script>

<template>
  <button class="button">
    <slot />
  </button>
</template>

<style>
.button {
  padding: 1rem 2rem;
  cursor: pointer;
  border: none;
  background-color: v-bind(color);
  font-size: v-bind(fontSize);
}
</style>
