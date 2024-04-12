<script setup lang="ts">
import { onErrorCaptured, ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'
const menuIsOpen = ref(false)

onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})
</script>
<template>
  <header class="bg-slate-950 flex px-10 py-4 justify-between z-10 absolute w-full">
    <nav>
      <ul>
        <li>
          <RouterLink to="/" class="text-slate-50 font-bold"> Accueil </RouterLink>
        </li>
      </ul>
    </nav>
    <button @pointerdown="menuIsOpen = !menuIsOpen" aria-controls="mainNav" aria-expanded="true"
      class="rounded-full border-2 border-slate-600 bg-slate-800 px-2 text-slate-50 -mt-0.5">
      menu
    </button>
    <!-- nav#mainNav>ul>li*3>a[href="#"]{item $} -->
  </header>
  <Transition class="transition-transform duration-1000" enter-from-class="-translate-y-32"
    enter-to-class="translate-y-0" leave-active-class="-translate-y-32">
    <nav id="mainNav" v-show="menuIsOpen"
      class="mt-14 z-0 text-slate-50 text-xs py-3  px-10 absolute bg-slate-900 w-screen">
      <ul class="flex justify-end gap-5">
        <li>
          <RouterLink to="/accordeon">Accordéon</RouterLink>
        </li>
        <li>
          <RouterLink to="/boucle">boucle sur des données</RouterLink>
        </li>
      </ul>
    </nav>
  </Transition>
  <RouterView class="pt-16" v-slot=" { Component }">
    <Suspense>
      <component :is="Component" />
    </Suspense>
  </RouterView>
</template>
