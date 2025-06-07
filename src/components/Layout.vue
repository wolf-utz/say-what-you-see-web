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
}

/* Card */
.card {
  position: relative;
  max-width: 800px;
  margin: 0 auto;
  background: var(--card-bg);
  border-radius: 12px;
  padding: 32px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  position: relative;
  overflow: hidden;
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
