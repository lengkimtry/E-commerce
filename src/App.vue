<template>
  <div id="app" class="parent">
    <!-- Categories Section -->
    <div class="parent-category">
      <CategoryComponent
        v-for="(category, index) in categories"
        :key="index"
        :imageSrc="category.imageSrc"
        :title="category.title"
        :itemCount="category.itemCount"
        :imageBgColor="category.imageBgColor"
        :textBgColor="category.textBgColor"
      />
    </div>
    <br />
    <!-- Promotions Section -->
    <div class="parent-promotion">
      <PromotionComponent
        v-for="(promotion, index) in promotions"
        :key="index"
        :imageSrc="promotion.imageSrc"
        :imageAlt="promotion.imageAlt"
        :headerText="promotion.headerText"
      >
        <!-- Button Slot -->
        <Button
          :label="promotion.buttonLabel"
          :color="promotion.buttonColor"
          size="12px"
          @click="primaryAction(promotion)" 
        />
      </PromotionComponent>
    </div>
  </div>
</template>

<script>
import Button from "./components/Button.vue";
import CategoryComponent from "./components/Category.vue";
import PromotionComponent from "./components/Promotion.vue";

export default {
  name: "App",
  components: {
    CategoryComponent,
    PromotionComponent,
    Button,
  },
  data() {
    return {
      categories: [
        {
          imageSrc: "./../../public/burger.png",
          title: "Burger",
          itemCount: 5,
          imageBgColor: "#F2FCE4",
          textBgColor: "#F2FCE4",
        },
        {
          imageSrc: "./../../public/peach.png",
          title: "Peach",
          itemCount: 10,
          imageBgColor: "#FFFCEB",
          textBgColor: "#FFFCEB",
        },
        {
          imageSrc: "./../../public/kiwi.png",
          title: "Organic Kiwi",
          itemCount: 5,
          imageBgColor: "#ECFFEC",
          textBgColor: "#ECFFEC",
        },
      ],
      promotions: [
        {
          imageSrc: "/onion.png",
          imageAlt: "Fresh Onion",
          headerText: "Everyday Fresh & Clean with Our Products",
          buttonLabel: "Shop Now",
          buttonColor: "#00ff00",  // Color for this button
        },
        {
          imageSrc: "/onion.png",
          imageAlt: "Strawberry Milk",
          headerText: "Delicious & Nutritious Strawberry Milk",
          buttonLabel: "Shop Now",
          buttonColor: "#FF9F00",  // Color for this button
        },
        {
          imageSrc: "/onion.png",
          imageAlt: "Fresh Carrot",
          headerText: "Healthy Snacks with Fresh Carrots",
          buttonLabel: "Shop Now",
          buttonColor: "#FF9F00",  // Color for this button
        },
      ],
    };
  },
  methods: {
    primaryAction(promotion) {
      alert("Let's shop: " + promotion.headerText);  // Use the promotion data for the alert
    },
  },
};
</script>

<style>
.parent {
  display: flex;
  flex-direction: row;
}

.parent-category {
  display: flex;
  gap: 20px;
  margin-bottom: 20px;
}

.parent-promotion {
  display: flex;
  gap: 20px;
}

.button {
  margin-top: 10px;
}
</style>
