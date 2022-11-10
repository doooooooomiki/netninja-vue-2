<template>
  <div id="app">
    <nav>
      <ul>
        <li>
          <router-link to="/">Home</router-link>
        </li>
        <li>
          <router-link to="/about">About</router-link>
        </li>
        <li>
          <router-link to="/router">Router</router-link>
        </li>
      </ul>
    </nav>
    <router-view />
  </div>
</template>

<style></style>
