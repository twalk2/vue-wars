<template>
  <div id="app">
    <div class="flex justify-center text-yellow-400 bg-black text-2xl">
      <router-link to="/">Home</router-link>|
      <router-link to="/characters">Characters</router-link>
    </div>
    <router-view />
  </div>
</template>
