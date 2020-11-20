<template>
  <li class="dropdown-option" :class="{ 'is-disabled': status }">
    <slot></slot>
  </li>
</template>

<script lang="ts">
import { computed, defineComponent } from "vue";
export default defineComponent({
  name: "DropdownItem",
  props: {
    disabled: {
      type: Boolean,
      default: false
    }
  },
  setup(props, ctx) {
    const status = computed(() => {
      console.log(ctx);
      return props.disabled;
    });
    return {
      status
    };
  }
});
</script>

<style>
.dropdown-option.is-disabled * {
  color: #6c757d;
  pointer-events: none;
  background-color: transparent;
}
</style>
