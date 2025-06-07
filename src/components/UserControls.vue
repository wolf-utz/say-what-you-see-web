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
  padding: 20px;
  margin-bottom: 32px;
  background: rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.12);
  border-radius: 16px;
  font-size: 1rem;
  line-height: 1.6;
  resize: vertical;
  color: var(--text-primary);
  transition: all 0.3s ease;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1),
    inset 0 1px 0 rgba(255, 255, 255, 0.1);
}

.description-input:focus {
  outline: none;
  background: rgba(255, 255, 255, 0.12);
  border-color: rgba(236, 29, 121, 0.5);
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.15), 0 0 0 3px rgba(236, 29, 121, 0.1),
    inset 0 1px 0 rgba(255, 255, 255, 0.2);
}

.description-input::placeholder {
  color: var(--text-muted);
  opacity: 0.8;
}

/* Buttons */
.button-group {
  display: flex;
  justify-content: flex-end;
  gap: 16px;
  margin-bottom: 24px;
}

.btn {
  padding: 14px 28px;
  border: none;
  border-radius: 50px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: uppercase;
  font-size: 0.875rem;
  letter-spacing: 0.8px;
  position: relative;
  overflow: hidden;
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
}

.btn-hint {
  background: rgba(74, 45, 69, 0.8);
  color: var(--text-secondary);
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.1),
    inset 0 1px 0 rgba(255, 255, 255, 0.1);
}

.btn-hint:hover {
  background: rgba(74, 45, 69, 0.9);
  /* transform: translateY(-2px); */
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2),
    inset 0 1px 0 rgba(255, 255, 255, 0.2);
}

.btn-submit {
  background: linear-gradient(135deg, var(--btn-primary) 0%, #f472b6 100%);
  color: white;
  border: 1px solid rgba(255, 255, 255, 0.2);
  box-shadow: 0 4px 16px rgba(236, 29, 121, 0.3),
    inset 0 1px 0 rgba(255, 255, 255, 0.2);
}

.btn-submit:hover {
  background: linear-gradient(135deg, #d91570 0%, #ec4899 100%);
  /* transform: translateY(-3px); */
  box-shadow: 0 12px 35px rgba(236, 29, 121, 0.4),
    inset 0 1px 0 rgba(255, 255, 255, 0.3);
}
</style>
