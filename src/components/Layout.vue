<template>
  <div class="app">
    <header>
      <slot name="Header"></slot>
    </header>

    <main class="main-content">
      <div class="container">
        <div class="card">
          <div class="card-content">
            <slot name="Content"></slot>
          </div>
        </div>
      </div>
    </main>

    <footer>
      <slot name="Foter"></slot>
    </footer>
  </div>
</template>

<style scoped>
/* Main Content */
.main-content {
  padding: 40px 0;
  min-height: calc(100vh - 70px);
  display: flex;
  flex-direction: column;
  background: linear-gradient(
    135deg,
    #2b0e2e 0%,
    #4a1a4d 50%,
    #7c2669 80%,
    #ec1d79 100%
  );
  position: relative;
}

/* Card */
.card {
  position: relative;
  max-width: 800px;
  margin: 0 auto;
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(25px);
  -webkit-backdrop-filter: blur(25px);
  border: 1px solid rgba(255, 255, 255, 0.15);
  border-radius: 20px;
  padding: 32px;
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.15), 0 6px 20px rgba(0, 0, 0, 0.08),
    inset 0 1px 2px rgba(255, 255, 255, 0.2),
    inset 0 -1px 2px rgba(0, 0, 0, 0.05);
  position: relative;
  overflow: hidden;
  transition: all 0.3s ease;
}

.card:hover {
  background: rgba(255, 255, 255, 0.08);
  border-color: rgba(255, 255, 255, 0.2);
  transform: translateY(-2px);
  box-shadow: 0 16px 50px rgba(0, 0, 0, 0.2), 0 8px 25px rgba(0, 0, 0, 0.1),
    inset 0 1px 2px rgba(255, 255, 255, 0.25),
    inset 0 -1px 2px rgba(0, 0, 0, 0.05);
}

.card-shadow {
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 16px;
  background-color: var(--shadow-color);
}

.card-content {
  position: relative;
  z-index: 1;
}
</style>
