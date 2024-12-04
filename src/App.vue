<template>
  <div
    id="app"
    class="bg-gray-300 flex-col justify-evenly space-y-4 h-screen w-full p-10"
  >
    <!-- Categories Section -->
    <div class="flex gap-[20px]">
      <CategoryComponent
        v-for="(category, index) in categories"
        :key="index"
        :image="category.image"
        :name="category.name"
        :productCount="category.productCount"
        :color="category.color"
        :textBgColor="category.textBgColor"
      />
    </div>
    <div class="parent-promotion">
      <PromotionComponent
        v-for="(promotion, index) in promotions"
        :key="index"
        :title="promotion.title"
        :buttonColor="promotion.buttonColor"
        :url="promotion.url"
        :color="promotion.color"
        :image="promotion.image"
      />
    </div>
  </div>
</template>

<script>
import Button from "./components/Button.vue";
import axios from "axios";
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
      categories: [],
      promotions: [],
    };
  },
  methods: {
    shopNow() {
      alert("Primary button clicked!");
    },
    fetchCategories() {
      axios
        .get("http://127.0.0.1:3000/api/categories")
        .then((response) => {
          this.categories = response.data.map((item) => ({
            name: item.name,
            image: item.image,
            productCount: item.productCount,
            color: item.color,
            textBgColor: item.textBgColor,
          }));
        })
        .catch((error) => {
          console.error("Error fetching categories:", error);
          alert("Failed to load categories. Please try again later.");
        });
    },

    fetchPromotions() {
      axios
        .get("http://127.0.0.1:3000/api/promotions")
        .then((response) => {
          console.log("Promotions:", response.data); // Check the console to see the data
          this.promotions = response.data.map((item) => ({
            // Store the response data in the promotions array
            title: item.title,
            buttonColor: item.buttonColor || "#007bff", // Provide defaults if needed
            url: item.url || "",
            color: item.color || "#ffffff",
            image: item.image || "",
          }));
        })
        .catch((error) => {
          console.error("Error fetching promotions:", error);
        });
    },
  },
  mounted() {
    // Fetch data when the component is mounted
    this.fetchCategories();
    this.fetchPromotions();
  },
};
</script>

<style>
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
