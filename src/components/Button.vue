<template>
  <button
    class="button"
    @click="$emit('onClick', label)"
    :class="{ double, triple, operation }"
  >{{ label }}</button>
</template>

<script>
export default {
  props: {
    label: {},
    operation: { type: Boolean },
    double: { type: Boolean },
    triple: { type: Boolean }
  }
};
</script>

<style>
:root {
  --bg-button: #f0f0f0;
  --border-button: 1px solid #888;
}

.button {
  font-size: 1.4em;
  background-color: var(--bg-button);
  border: none;
  border-right: var(--border-button);
  border-bottom: var(--border-button);
  outline: none;
  transition: background 0.1s;
}

.button:hover {
  opacity: 95%;
}

.button:active {
  background-color: #ccc;
}

.double {
  grid-column: span 2;
}

.triple {
  grid-column: span 3;
}

.operation {
  background-color: #fa8231;
  color: #fff;
}

.button.operation:active {
  background-color: #fa8231cc;
}
</style>