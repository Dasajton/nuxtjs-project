<template>
  <div>
    <main class="user-layout bg-gray-100">
      <article class="sidebar">
        <p>Dashboard</p>
        <p>Settings</p>
      </article>

      <section>
        <!-- here nuxt will replace page content -->
        <slot></slot>
      </section>
    </main>
  </div>
</template>

<style>
.user-layout {
  display: flex;
}

.sidebar {
  display: flex;
  flex-direction: column;
}
</style>
