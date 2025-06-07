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
</style>
