<script setup>
import { ref } from 'vue';
import { Head, Link, router } from '@inertiajs/vue3';
import ApplicationMark from '@/Components/ApplicationMark.vue';
import Banner from '@/Components/Banner.vue';
import Dropdown from '@/Components/Dropdown.vue';
import DropdownLink from '@/Components/DropdownLink.vue';
import NavLink from '@/Components/NavLink.vue';
import ResponsiveNavLink from '@/Components/ResponsiveNavLink.vue';

defineProps({
  title: String,
});

const showingNavigationDropdown = ref(false);

const switchToTeam = (team) => {
  router.put(route('current-team.update'), {
    team_id: team.id,
  }, {
    preserveState: false,
  });
};

const logout = () => {
  router.post(route('logout'));
};
</script>

<template>
  <div class="min-h-screen flex flex-col bg-white">
    <Head :title="title" />

    <Banner />

    <!-- NAV -->
    <nav class="bg-white border-b border-gray-100">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between h-16">
          <div class="flex">
            <!-- Logo -->
            <div class="shrink-0 flex items-center">
              <Link :href="route('dashboard')">
                <ApplicationMark class="block h-9 w-auto" />
              </Link>
            </div>

            <!-- Navigation Links -->
            <div class="hidden space-x-8 sm:-my-px sm:ms-10 sm:flex">
              <NavLink :href="route('dashboard')" :active="route().current('dashboard')">
                Bienvenido/a
              </NavLink>
            </div>
          </div>

          <!-- Ajustes y menú -->
          <div class="hidden sm:flex sm:items-center sm:ms-6">
            <!-- Dropdowns... (sin cambios aquí) -->
            <!-- tu contenido de settings, teams, etc -->
          </div>

          <!-- Menú hamburguesa -->
          <div class="-me-2 flex items-center sm:hidden">
            <button @click="showingNavigationDropdown = !showingNavigationDropdown"
              class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none">
              <svg class="size-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path v-if="!showingNavigationDropdown" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                  d="M4 6h16M4 12h16M4 18h16" />
                <path v-else stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                  d="M6 18L18 6M6 6l12 12" />
              </svg>
            </button>
          </div>
        </div>
      </div>

      <!-- Responsive Navigation Menu -->
      <div v-if="showingNavigationDropdown" class="sm:hidden">
        <!-- tu contenido de menú móvil -->
      </div>
    </nav>

    <!-- Contenido principal -->
    <div class="flex-1">
      <!-- Encabezado opcional -->
      <header v-if="$slots.header" class="bg-white shadow">
        <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
          <slot name="header" />
        </div>
      </header>

      <!-- Página -->
      <main>
        <slot />
      </main>
    </div>
  </div>
</template>

