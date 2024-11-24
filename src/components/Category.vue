<template>
  <div :style="{ backgroundColor: imageBgColor }" class="category-container">
    <div class="image">
      <img :src="imageSrc" :alt="title" />
    </div>
    <div class="text">
      <h2 :style="{ backgroundColor: textBgColor }" class="header">{{ title }}</h2>
      <p class="paragraph">{{ itemCount }} items</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Category",
  props: {
    imageSrc: String,
    title: String,
    itemCount: Number,
    imageBgColor: String,
    textBgColor: String,
  },
};
</script>

<style scoped>
.category-container {
  width: 137px;
  height: 177px;
  border-radius: 10px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: transparent; /* Allow the dynamic background color to work */
}

.image {
  width: 100%;
  height: 100px; /* Fixed height for the image container */
  display: flex;
  justify-content: center;
  align-items: center;
}

.image img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.text {
  width: 100%;
  text-align: center;
  padding: 10px;
}

.header {
  color: #253d4e;
  font-size: 16px;
  font-weight: 700;
}

.paragraph {
  color: #b6b6b6;
  font-size: 10px;
}
</style>
