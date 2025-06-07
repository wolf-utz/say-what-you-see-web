<template>
  <Layout>
    <template v-slot:Header>
      <Header />
    </template>
    <template v-slot:Title> Besser sprechen mit jedem Bild </template>
    <template v-slot:Content>
      <ImageContainer />
      <UserControls />
      <FeedbackSection />
    </template>
  </Layout>
</template>

<script setup lang="ts">
import Layout from "./components/Layout.vue";
import Header from "./components/Header.vue";
import ImageContainer from "./components/ImageContainer.vue";
import UserControls from "./components/UserControls.vue";
import FeedbackSection from "./components/FeedbackSection.vue";
</script>

<style>
@font-face {
  font-family: "Inter";
  src: url("./assets/fonts/Inter-Italic-VariableFont_opsz\,wght.ttf")
    format("truetype");
  font-weight: 100 900;
}

/* Global Styles */
:root {
  --bg-primary: #2b0e2e;
  --card-bg: #f6f3f1;
  --shadow-color: #e7dcd5;
  --btn-primary: #ec1d79;
  --btn-secondary: #4a2d45;
  --text-primary: #ffffff;
  --text-secondary: #cccccc;
  --text-muted: #999999;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, sans-serif;
}

body {
  background-color: var(--bg-primary);
  color: var(--text-primary);
  line-height: 1.6;
}

.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.25rem;
}
</style>
