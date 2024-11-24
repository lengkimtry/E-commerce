<template>
  <div class="container">
    <div class="image">
      <img :src="imageSrc" :alt="imageAlt" />
    </div>
    <div class="text">
      <h1 class="header">{{ headerText }}</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "Promotion",
  props: {
    imageSrc: {
      type: String,
      required: true,
    },
    imageAlt: {
      type: String,
      required: false,
      default: "Promotion Image",
    },
    headerText: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.container {
  background-color: #f0e8d5;
  width: 512px;
  height: 300px;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
}

.image {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.image img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  border-radius: 10px;
}

.text {
  background-color: orange;
  width: 100%;
  text-align: center;
}

.header {
  color: #253d4e;
  font-size: 24px;
  font-weight: 700;
  text-align: left;
  width: 271px;
  height: 92px;
  position: absolute;
  top: 75px;
  left: 48px;
}
</style>
