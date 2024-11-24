<template>
  <button 
    :class="buttonClass" 
    :style="{ backgroundColor: buttonColor, color: buttonTextColor, fontSize: size }">
    {{ label }}
  </button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    label: {
      type: String,
      required: true,
    },
    color: {
      type: String,
      required: true,
    },
    size: {
      type: String,
      default: '14px',  // Default size in case not passed
    },
  },
  computed: {
    buttonClass() {
      return 'button';  // Apply any common class styles
    },
    buttonColor() {
      return this.color;  // Use the `color` prop for the button background
    },
    buttonTextColor() {
      return this.color === '#FF9F00' ? '#fff' : '#253d4e';  // Dynamically set text color based on background
    },
  },
};
</script>

<style scoped>
.button {
  padding: 12px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  transition: background-color 0.3s ease, transform 0.2s;
}

.button:hover {
  transform: translateY(-2px);
}

.button:active {
  transform: translateY(2px);
}
</style>
