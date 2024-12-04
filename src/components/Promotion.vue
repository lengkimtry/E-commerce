<template>
  <div :style="{ backgroundColor: color }" class=" flex sm:w-[104px] lg:w-[500px] rounded-[15px]">
    <div class="text">
      <h1 class="header">{{ title }}</h1>
      <button 
        :style="{ backgroundColor: buttonColor }" 
        class="button" 
        @click="navigateToUrl"
      >
        Shop Now
      </button>
    </div>
    <div class="image">
      <img :src="'http://localhost:3000/' + image" :alt="title" />
    </div>
  </div>
</template>


<script>
export default {
  name: "Promotion",
  props: {
    title: String,          // Text for the header
    buttonColor: String,    // Button's background color
    url: String,            // URL to navigate to on button click
    color: String,          // Background color for the container
    image: String,          // Source URL for the image
  },
  methods: {
    navigateToUrl() {
      if (this.url) {
        window.location.href = this.url; // Navigate to the specified URL
      } else {
        alert("URL is not defined");
      }
    },
  },
};
</script>


<style scoped>


/* Text Section Styling */
.text {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center; /* Center-align text */
  margin-bottom: 20px; /* Add space between text and image */
}

.header {
  color: #253d4e; /* Dark color for contrast */
  font-size: 1.5rem; /* Adjust font size for responsiveness */
  font-weight: 700;
  margin-bottom: 15px;
}

/* Button Styling */
.button {
  color: white; /* White text for better contrast */
  font-size: 1rem; /* Responsive font size */
  padding: 12px 24px;
  border: none;
  border-radius: 10px; /* Rounded corners for a modern look */
  cursor: pointer;
  background-color: #007bff; /* Fallback button color */
  transition: background-color 0.3s ease, transform 0.2s, box-shadow 0.3s ease;
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.2); /* Add a subtle shadow */
}

.button:hover {
  background-color: #0056b3; /* Darker shade for hover */
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.25); /* Enhance shadow on hover */
}

.button:active {
  transform: translateY(2px);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2); /* Reduce shadow on click */
}

/* Image Section Styling */
.image {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.image img {
  width: 100%; /* Make the image responsive */
  max-width: 400px; /* Limit maximum width */
  height: auto;
  object-fit: contain; /* Maintain aspect ratio */
  border-radius: 10px; /* Rounded corners */
  transition: transform 0.3s ease;
}

.image img:hover {
  transform: scale(1.05); /* Slight zoom on hover */
}
</style>


