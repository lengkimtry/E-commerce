<template>
  <div id="app" class="parent">
    <!-- Categories Section -->
    <div class="parent-category">
      <div v-for="(category, index) in categories" :key="index">
        <Category
          :imageSrc="category.imageSrc"
          :title="category.title"
          :itemCount="category.itemCount"
          :imageBgColor="category.imageBgColor"
          :textBgColor="category.textBgColor"
        />
      </div>
    </div>
    <br />
     <!-- Promotions Section -->
     <div class="parent-promotion">
      <div
        class="child-promotion"
        v-for="(promotion, index) in promotions"
        :key="index"
      >
        <!-- Pass props dynamically to Promotion component -->
        <Promotion
          :imageSrc="promotion.imageSrc"
          :imageAlt="promotion.imageAlt"
          :headerText="promotion.headerText"
        />
        <Button
          class="button"
          :label="promotion.buttonLabel"
          :color="promotion.buttonColor"
          size="12px"
          @click="primaryAction"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Button from "./components/Button.vue";
import Category from "./components/Category.vue";
import Promotion from "./components/Promotion.vue";

export default {
  name: "App",
  components: {
    Category,
    Promotion,
    Button,
  },
  data() {
    return {
      // Default mock data for display
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
          title: "peach",
          itemCount: 10,
          imageBgColor: "#FFFCEB",
          textBgColor: "#FFFCEB",
        },
        {
          imageSrc: "./../../public/kiwi.png",
          title: "organic kiwi",
          itemCount: 5,
          imageBgColor: "#ECFFEC",
          textBgColor: "#ECFFEC",
        },
        {
          imageSrc: "./../../public/apple.png",
          title: "apple",
          itemCount: 10,
          imageBgColor: "#FEEFEA",
          textBgColor: "#FEEFEA",
        },
        {
          imageSrc: "./../../public/snack.png",
          title: "snack",
          itemCount: 5,
          imageBgColor: "#FFF3EB",
          textBgColor: "#FFF3EB",
        },
        {
          imageSrc: "./../../public/blackplum.png",
          title: "black plum",
          itemCount: 10,
          imageBgColor: "#FFF3FF",
          textBgColor: "#FFF3FF",
        },
        {
          imageSrc: "./../../public/cabbage.png",
          title: "vigetable",
          itemCount: 5,
          imageBgColor: "#F2FCE4",
          textBgColor: "#F2FCE4",
        },
        {
          imageSrc: "./../../public/headphone.png",
          title: "headphone",
          itemCount: 10,
          imageBgColor: "#FFFCEB",
          textBgColor: "#FFFCEB",
        },
        {
          imageSrc: "./../../public/cakemilk.png",
          title: "cake & mike",
          itemCount: 5,
          imageBgColor: "#F2FCE4",
          textBgColor: "#F2FCE4",
        },
        {
          imageSrc: "./../../public/orange.png",
          title: "orange",
          itemCount: 10,
          imageBgColor: "#FFF3FF",
          textBgColor: "#FFF3FF",
        },
      ],
      promotions: [
        {
          imageSrc: "/onion.png",
          imageAlt: "Fresh Onion",
          headerText: "Everyday Fresh & Clean with Our Products",
          buttonLabel: "Buy Now",
          buttonColor: "#007BFF",
        },
        {
          imageSrc: "/onion.png",
          imageAlt: "Strawberry Milk",
          headerText: "Delicious & Nutritious Strawberry Milk",
          buttonLabel: "Learn More",
          buttonColor: "#28A745",
        },
        {
          imageSrc: "/onion.png",
          imageAlt: "Fresh Carrot",
          headerText: "Healthy Snacks with Fresh Carrots",
          buttonLabel: "Explore",
          buttonColor: "#FFC107",
        },
      ],
    };
  },
  methods: {
    primaryAction() {
      alert("Primary button clicked!");
    },
    // Keeping fetch methods for future use
    async fetchCategories() {
      // Placeholder for API call
      console.log("Fetching categories...");
    },
    async fetchPromotions() {
      // Placeholder for API call
      console.log("Fetching promotions...");
    },
  },
  mounted() {
    // Commented out for now; uncomment to enable API fetching
    // this.fetchCategories();
    // this.fetchPromotions();
  },
};
</script>

<style>
.parent {
  display: flex;
  flex-direction: column;
}

.parent-category {
  display: flex;
  flex-direction: row;
  gap: 22px;
}

.parent-promotion {
  display: flex;
  flex-direction: row;
  gap: 20px;
}

.child-promotion {
  position: relative;
  margin-top: 20px;
}

.button {
  position: absolute;
  top: 190px;
  left: 48px;
}

</style>
