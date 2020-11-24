<template>
  <button
    class="navbar-toggler"
    type="button"
    data-toggle="collapse"
    :data-target="target"
    :aria-controls="target"
    :aria-expanded="toggled"
    aria-label="Toggle navigation"
  >
    <div class="navbar-toggler-burger">
      <div></div>
    </div>
  </button>
</template>
<script>
export default {
  props: {
    target: {
      type: [String, Number],
      description: 'Button target element',
    },
    toggled: {
      type: Boolean,
      default: false,
      description: 'Whether button is toggled',
    },
  },
};
</script>
<style scoped>
input:focus,
button:focus,
optgroup:focus,
select:focus,
textarea:focus {
  outline: none;
}
</style>
