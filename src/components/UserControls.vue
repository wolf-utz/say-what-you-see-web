<template>
  <div class="user-controls">
    <!-- Text input -->
    <textarea
      class="description-input"
      placeholder="Type your description here..."
    ></textarea>

    <!-- Buttons -->
    <div class="button-group">
      <button class="btn btn-hint">Hint</button>
      <button class="btn btn-submit">Submit</button>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style>
/* Text Input */
.description-input {
  width: 100%;
  min-height: 120px;
  padding: 16px;
  margin-bottom: 24px;
  border: 2px solid #ddd;
  border-radius: 8px;
  font-size: 1rem;
  line-height: 1.5;
  resize: vertical;
  background-color: var(--btn-secondary);
  color: var(--text-primary);
  border: none;
}

.description-input::placeholder {
  color: var(--text-muted);
}

/* Buttons */
.button-group {
  display: flex;
  justify-content: flex-end;
  gap: 16px;
  margin-bottom: 24px;
}

.btn {
  padding: 12px 24px;
  border: none;
  border-radius: 999px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s;
  text-transform: uppercase;
  font-size: 0.875rem;
  letter-spacing: 0.5px;
}

.btn-hint {
  background-color: var(--btn-secondary);
  color: var(--text-secondary);
}

.btn-submit {
  background-color: var(--btn-primary);
  color: white;
}

.btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}
</style>
