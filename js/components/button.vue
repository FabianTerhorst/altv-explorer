<template functional>
  <div class="icon-button noselect clickable" v-on="$listeners" :width="`${size + 4}px`" :height="`${size + 4}px`">
    <icon :icon="icon" :size="size / 1.2"></icon>
  </div>
</template>

<script>

/*
  CONTEXT
  Parent, Self

  STATES
  Unfocused -> Parent:hover -> Self:hover -> Self:active
*/

module.exports = {
  name: "icon-button",
  props: {
    size: { type: Number, required: false, default: 16 },
    icon: { type: String, required: true },
  }
}
</script>

<style>
div.icon-button {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;

  border-radius: 4px;
  z-index: 1;
}

div.icon-button {
  background-color: rgba(255, 255, 255, 0);
  opacity: 0.6;
  transition: background-color 0.2s ease;
}

div.icon-button:hover {
  background-color: rgba(255, 255, 255, 0.1);
  opacity: 0.9;
}

div.icon-button:active,
div.icon-button:focus {
  background-color: rgba(255, 255, 255, 0.2);
  opacity: 1.0;
}
</style>