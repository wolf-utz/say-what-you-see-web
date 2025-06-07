<template>
  <!-- Feedback section -->
  <div class="feedback">
    <h3 class="feedback-title">Feedback</h3>
    <p class="feedback-text">
      Your feedback will appear here after submission.
    </p>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
/* Feedback */
.feedback {
  background-color: rgba(0, 0, 0, 0.05);
  padding: 16px;
  border-radius: 8px;
}

.feedback-title {
  font-size: 1rem;
  margin-bottom: 8px;
  color: var(--text-primary);
}

.feedback-text {
  color: var(--text-muted);
  font-size: 0.9rem;
}
</style>
