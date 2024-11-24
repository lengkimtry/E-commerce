<template>
  <div class="container">
    <div class="text">
      <h1 class="header">{{ headerText }}</h1>
      <slot></slot> <!-- Slot for additional content like the button -->

    </div>
    <div class="image">
      <img :src="imageSrc" :alt="imageAlt" />
    </div>
  </div>
</template>

<script>
export default {
  name: "Promotion",
  props: {
    imageSrc: String,
    imageAlt: String,
    headerText: String,
  },
  data() {
    return {
      // Local promotion object with title, button label, and button color
      promotion: {
        title: "Make your Breakfast Healthy and Easy",
        buttonLabel: "Shop Now", // Text for the button
        buttonColor: "#ff9f00", // Button color
      },
    };
  },
  methods: {
    primaryAction() {
      this.shopNow(this.promotion);  // Call shopNow with the promotion data
    },
    shopNow(promotion) {
      alert("Let's shop: " + promotion.title);  // Show the promotion title
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
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  position: relative;
}

.text {
  width: 45%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  text-align: left;
  padding: 10px;
  margin: 0;
}

.header {
  color: #253d4e;
  font-size: 24px;
  font-weight: 700;
  margin-bottom: 10px;
}

.button {
  background-color: #ffffff;
  color: #253d4e;
  font-size: 16px;
  padding: 12px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.2s;
}

.button:hover {
  background-color: #ff9f00;
  transform: translateY(-2px);
}

.button:active {
  transform: translateY(2px);
}

.image {
  width: 50%;
  height: auto;
  display: flex;
  justify-content: center;
  align-items: center;
}

.image img {
  width: 80%;
  height: auto;
  object-fit: cover;
  border-radius: 10px;
}
</style>
