<template>
  <div class="image-container">
    <div class="image-wrapper" @click="openModal">
      <img
        src="https://media.gettyimages.com/id/836665562/de/foto/gl%C3%BCcklich-genie%C3%9Fen-sommer-familientag-im-vergn%C3%BCgungspark.jpg?s=1024x1024&w=gi&k=20&c=kPnO_YSxBE9Ne5J_r8Ak2jnQORyvQjSu6lOIHUEPxbU="
        alt="Family enjoying summer day at amusement park"
        class="main-image"
      />
      <div class="image-overlay">
        <div class="zoom-icon">🔍</div>
        <p class="zoom-text">Click to enlarge</p>
      </div>
    </div>
  </div>

  <!-- Modal -->
  <Teleport to="body">
    <div v-if="isModalOpen" class="modal-overlay" @click="closeModal">
      <div class="modal-content" @click.stop>
        <button class="modal-close" @click="closeModal">&times;</button>
        <img
          src="https://media.gettyimages.com/id/836665562/de/foto/gl%C3%BCcklich-genie%C3%9Fen-sommer-familientag-im-vergn%C3%BCgungspark.jpg?s=1024x1024&w=gi&k=20&c=kPnO_YSxBE9Ne5J_r8Ak2jnQORyvQjSu6lOIHUEPxbU="
          alt="Family enjoying summer day at amusement park"
          class="modal-image"
        />
      </div>
    </div>
  </Teleport>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from "vue";

const isModalOpen = ref(false);

const openModal = () => {
  isModalOpen.value = true;
  document.body.style.overflow = "hidden"; // Prevent background scrolling
};

const closeModal = () => {
  isModalOpen.value = false;
  document.body.style.overflow = "auto"; // Restore scrolling
};

// Close modal on escape key
const handleEscape = (event: KeyboardEvent) => {
  if (event.key === "Escape" && isModalOpen.value) {
    closeModal();
  }
};

onMounted(() => {
  document.addEventListener("keydown", handleEscape);
});

onUnmounted(() => {
  document.removeEventListener("keydown", handleEscape);
  document.body.style.overflow = "auto"; // Cleanup
});
</script>

<style scoped>
.image-container {
  width: 100%;
  max-width: 500px;
  margin: 0 auto 32px;
  position: relative;
}

.image-wrapper {
  position: relative;
  cursor: pointer;
  border-radius: 20px;
  overflow: hidden;
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.15);
  transition: all 0.3s ease;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.15), 0 4px 16px rgba(0, 0, 0, 0.1),
    inset 0 1px 0 rgba(255, 255, 255, 0.1);
}

.image-wrapper:hover {
  /* transform: translateY(-4px); */
  box-shadow: 0 16px 50px rgba(0, 0, 0, 0.2), 0 8px 25px rgba(0, 0, 0, 0.15),
    inset 0 1px 0 rgba(255, 255, 255, 0.2);
}

.image-wrapper:hover .image-overlay {
  opacity: 1;
}

.main-image {
  width: 100%;
  height: auto;
  display: block;
  border-radius: 20px;
}

.image-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.4);
  backdrop-filter: blur(10px);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: all 0.3s ease;
  border-radius: 20px;
}

.zoom-icon {
  font-size: 2rem;
  margin-bottom: 8px;
  color: white;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
}

.zoom-text {
  color: white;
  font-size: 0.9rem;
  font-weight: 600;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.5);
  letter-spacing: 0.5px;
  margin: 0;
}

/* Modal Styles */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.8);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
  padding: 20px;
  animation: modalFadeIn 0.3s ease;
}

.modal-content {
  position: relative;
  max-width: 90vw;
  max-height: 90vh;
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(25px);
  -webkit-backdrop-filter: blur(25px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 20px;
  padding: 20px;
  box-shadow: 0 25px 80px rgba(0, 0, 0, 0.3),
    inset 0 1px 0 rgba(255, 255, 255, 0.2);
  animation: modalScaleIn 0.3s ease;
}

.modal-image {
  width: 100%;
  height: auto;
  max-width: 80vw;
  max-height: 80vh;
  object-fit: contain;
  border-radius: 16px;
  display: block;
}

.modal-close {
  position: absolute;
  top: -10px;
  right: -10px;
  width: 40px;
  height: 40px;
  border: none;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.9);
  color: #333;
  font-size: 24px;
  font-weight: bold;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.2s ease;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
}

.modal-close:hover {
  background: var(--btn-primary);
  color: white;
  transform: scale(1.1);
}

/* Animations */
@keyframes modalFadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes modalScaleIn {
  from {
    opacity: 0;
    transform: scale(0.8);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

/* Responsive Design */
@media (max-width: 768px) {
  .modal-content {
    padding: 15px;
    margin: 10px;
  }

  .modal-image {
    max-width: 95vw;
    max-height: 85vh;
  }

  .zoom-text {
    font-size: 0.8rem;
  }

  .zoom-icon {
    font-size: 1.5rem;
  }
}
</style>
