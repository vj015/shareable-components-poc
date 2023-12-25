<template>
  <button
    @click="handleApiCall()"
    :style="{
      padding: '15px',
      fontSize: '20px',
      background: background,
      color: color,
    }"
  >
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "MyButton",
  props: {
    background: {
      default: "#456099",
    },
    color: {
      default: "#fff",
    },
    text: {
      default: "My Button",
    },
  },
  methods: {
    async handleApiCall() {
      console.log("Hello i am working");
      await fetch("https://fakestoreapi.com/products/1")
        .then((res) => res.json())
        .then((json) => console.log(json));
    },
  },
};
</script>
