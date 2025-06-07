<template>
  <div class="top-bar">
    <div class="container">
      <h1 class="logo">SagWasDuSiehst</h1>
      <nav class="nav-links">
        <a href="#" class="nav-link">Practice</a>
        <a href="#" class="nav-link">Learn</a>
        <a href="#" class="nav-link">Community</a>
        <div class="profile-icon">👤</div>
      </nav>
    </div>
  </div>
</template>

<style scoped>
/* Top Bar */
.top-bar {
  background-color: var(--bg-primary);
  padding: 16px 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.top-bar .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--text-primary);
  text-decoration: none;
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 24px;
}

.nav-link {
  color: var(--text-primary);
  text-decoration: none;
  font-weight: 500;
  transition: opacity 0.2s;
}

.nav-link:hover {
  opacity: 0.8;
}

.profile-icon {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background-color: rgba(255, 255, 255, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}
</style>
