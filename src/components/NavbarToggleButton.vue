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
    <div @click.prevent="toggle" class="navbar-toggler-burger">
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
<style lang="scss" scoped>
input:focus,
button:focus,
optgroup:focus,
select:focus,
textarea:focus {
  outline: none;
}

.navbar-toggler[aria-expanded='true'] .navbar-toggler-burger {
  display: block;
  width: 24px;
  height: 26px;
  cursor: pointer;
  position: relative;
  margin-left: 24px;
  div {
    position: absolute;
    top: 12px;
    left: 0;
    width: 24px;
    visibility: hidden;
    height: 2px;
    display: block;
    background: white;
  }
  div:before {
    visibility: visible;
    transform: translateY(0) rotate(45deg);
  }
  div:after {
    visibility: visible;
    transform: translateY(0) rotate(-45deg);
  }
}
.navbar-toggler-burger {
  display: block;
  width: 24px;
  height: 26px;
  cursor: pointer;
  position: relative;
  margin-left: 24px;
  div {
    position: absolute;
    top: 12px;
    left: 0;
    width: 24px;
    height: 2px;
    display: block;
    background: #dff1fd;
    border-radius: 99em;
  }
  div:after,
  div:before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 24px;
    height: 2px;
    background: inherit;
    transition: transform 0.3s ease;
    border-radius: 99em;
  }
  div:before {
    transform: translateY(-6px);
  }
  div:after {
    transform: translateY(6px);
  }
}
</style>

