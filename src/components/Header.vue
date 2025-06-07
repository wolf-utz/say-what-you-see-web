<template>
  <div class="top-bar">
    <div class="container">
      <h1 class="logo">SagWasDuSiehst</h1>

      <!-- Desktop Navigation -->
      <nav
        class="nav-links desktop-nav"
        :class="{ 'mobile-open': isMobileMenuOpen }"
      >
        <a href="#" class="nav-link">Practice</a>
        <a href="#" class="nav-link">Learn</a>
        <a href="#" class="nav-link">Community</a>
        <div class="profile-icon">👤</div>
      </nav>

      <!-- Mobile Menu Toggle -->
      <button
        class="mobile-toggle"
        @click="toggleMobileMenu"
        :class="{ active: isMobileMenuOpen }"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const isMobileMenuOpen = ref(false);

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};
</script>

<style scoped>
/* Top Bar */
.top-bar {
  background: rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.15);
  padding: 20px 0;
  position: sticky;
  top: 0;
  z-index: 100;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

.top-bar .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 1.75rem;
  font-weight: 800;
  color: var(--text-primary);
  text-decoration: none;
  background: linear-gradient(
    135deg,
    var(--text-primary) 0%,
    var(--btn-primary) 100%
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  transition: all 0.3s ease;
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 32px;
}

.nav-link {
  color: var(--text-primary);
  text-decoration: none;
  font-weight: 600;
  font-size: 0.95rem;
  padding: 8px 16px;
  border-radius: 25px;
  transition: all 0.3s ease;
  position: relative;
  letter-spacing: 0.3px;
}

.nav-link:hover {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  color: var(--btn-primary);
  transform: translateY(-1px);
}

.profile-icon {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(15px);
  -webkit-backdrop-filter: blur(15px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.3s ease;
  font-size: 1.2rem;
}

.profile-icon:hover {
  background: rgba(255, 255, 255, 0.15);
  border-color: rgba(236, 29, 121, 0.4);
  transform: translateY(-2px);
  box-shadow: 0 4px 15px rgba(236, 29, 121, 0.2);
}

/* Mobile Menu Toggle */
.mobile-toggle {
  display: none;
  flex-direction: column;
  justify-content: space-around;
  width: 30px;
  height: 30px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
  z-index: 10;
}

.mobile-toggle span {
  display: block;
  height: 3px;
  width: 100%;
  background: var(--text-primary);
  border-radius: 3px;
  opacity: 1;
  left: 0;
  transform: rotate(0deg);
  transition: 0.25s ease-in-out;
}

.mobile-toggle.active span:nth-child(1) {
  top: 9px;
  transform: rotate(135deg);
}

.mobile-toggle.active span:nth-child(2) {
  opacity: 0;
  left: -30px;
}

.mobile-toggle.active span:nth-child(3) {
  top: 9px;
  transform: rotate(-135deg);
}

/* Responsive Design */
@media (max-width: 768px) {
  .mobile-toggle {
    display: flex;
  }

  .nav-links {
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background: rgba(43, 14, 46, 0.95);
    backdrop-filter: blur(25px);
    -webkit-backdrop-filter: blur(25px);
    border-top: 1px solid rgba(255, 255, 255, 0.15);
    border-bottom: 1px solid rgba(255, 255, 255, 0.15);
    flex-direction: column;
    gap: 0;
    padding: 20px 0;
    transform: translateY(-100%);
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
    z-index: 99;
  }

  .nav-links.mobile-open {
    transform: translateY(0);
    opacity: 1;
    visibility: visible;
  }

  .nav-link {
    padding: 16px 32px;
    border-radius: 0;
    width: 100%;
    text-align: left;
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
  }

  .nav-link:hover {
    background: rgba(255, 255, 255, 0.08);
    transform: none;
  }

  .profile-icon {
    margin: 16px 32px 0;
    align-self: flex-start;
  }

  .logo {
    font-size: 1.5rem;
  }
}

@media (max-width: 480px) {
  .top-bar {
    padding: 16px 0;
  }

  .logo {
    font-size: 1.25rem;
  }

  .container {
    padding: 0 16px;
  }
}
</style>
