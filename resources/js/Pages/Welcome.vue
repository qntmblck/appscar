<template>

  <Head>
    <title>Tu carga, nuestra misión</title>
    <meta
      name="description"
      content="Transportes SCAR, con más de 25 años de experiencia, ofrece soluciones de transporte de carga seguras, eficientes y sostenibles en Chile."
    />
  </Head>

  <div class="bg-white">
    <!-- HEADER -->
<header class="fixed top-0 left-0 right-0 z-50 w-full bg-gray-900 shadow-lg">
  <nav class="mx-auto flex items-center justify-between px-6 py-0 lg:px-8 max-w-7xl" aria-label="Menú principal">

    <!-- Logo -->
    <div class="flex items-center">
      <a href="#inicio" class="p-1" aria-label="Inicio">
        <span class="sr-only">Transportes SCAR</span>
        <img class="h-12 w-auto" src="img/logoscar.png" alt="Logo de Transportes SCAR" />
      </a>
    </div>

    <!-- Menú móvil -->
    <div class="flex lg:hidden">
      <button
        type="button"
        class="inline-flex items-center justify-center rounded-md p-2.5 text-white"
        @click="mobileMenuOpen = true"
        aria-label="Abrir menú"
      >
        <Bars3Icon class="h-6 w-6" aria-hidden="true" />
      </button>
    </div>

    <!-- Navegación escritorio -->
    <div class="hidden lg:flex lg:gap-x-10">
      <a
        v-for="item in navigation"
        :key="item.name"
        :href="item.href"
        class="text-sm font-semibold text-white hover:text-indigo-300"
      >
        {{ item.name }}
      </a>
    </div>

    <!-- Botones Login/Register -->
    <div class="hidden lg:flex lg:flex-1 lg:justify-end space-x-4" v-if="canLogin">
      <Link
        :href="route('login')"
        class="text-sm font-semibold text-white hover:text-indigo-300"
        aria-label="Ingresar"
      >
        Ingresar <span aria-hidden="true">&rarr;</span>
      </Link>
      <Link
        v-if="canRegister"
        :href="route('register')"
        class="text-sm font-semibold text-white hover:text-indigo-300"
        aria-label="Registrar"
      >
        Registrar <span aria-hidden="true">&rarr;</span>
      </Link>
    </div>
  </nav>

  <!-- MENÚ MÓVIL -->
  <Dialog class="lg:hidden" @close="mobileMenuOpen = false" :open="mobileMenuOpen">
    <div class="fixed inset-0 z-40 bg-black/25" aria-hidden="true"></div>
    <DialogPanel class="fixed inset-y-0 right-0 z-50 w-full max-w-sm overflow-y-auto bg-gray-900 px-6 py-6 sm:ring-1 sm:ring-white/10">
      <div class="flex items-center justify-between">
        <a href="#inicio" class="p-1" aria-label="Inicio">
          <img class="h-10 w-auto" src="img/logoscar.png" alt="Logo de Transportes SCAR" />
        </a>
        <button type="button" class="-m-2.5 rounded-md p-2.5 text-gray-400" @click="mobileMenuOpen = false" aria-label="Cerrar menú">
          <XMarkIcon class="h-6 w-6" aria-hidden="true" />
        </button>
      </div>
      <div class="mt-6 flow-root">
        <div class="-my-6 divide-y divide-gray-500/25">
          <div class="space-y-2 py-6">
            <a v-for="item in navigation" :key="item.name" :href="item.href" class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold text-white hover:bg-gray-800">
              {{ item.name }}
            </a>
          </div>
          <div class="py-6">
            <Link v-if="canLogin" :href="route('login')" class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold text-white hover:bg-gray-800">
              Ingresar
            </Link>
            <Link v-if="canRegister" :href="route('register')" class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold text-white hover:bg-gray-800">
              Registrar
            </Link>
          </div>
        </div>
      </div>
    </DialogPanel>
  </Dialog>
</header>
    <!-- MAIN CONTENT -->
    <main>
      <!-- HERO SECTION -->
      <section id="inicio" class="relative pt-20 sm:pt-2 pb-16 sm:pb-2">
  <div class="relative h-[90vh] overflow-hidden bg-fixed bg-center bg-cover" style="background-image: url('/img/dashboard/truck.jpg');">
    <div class="absolute inset-0 bg-gray-900/60 mix-blend-multiply"></div>
    <div class="relative z-10 flex flex-col justify-center items-center h-full text-center px-6">
      <h1 class="text-4xl font-bold tracking-tight text-white">
        Llevamos tu carga a todo Chile
      </h1>
      <p class="mt-6 text-base sm:text-lg leading-7 text-gray-300 max-w-xl">
        Con más de 25 años de experiencia en transporte terrestre, Transportes SCAR garantiza seguridad, eficiencia y cumplimiento en cada ruta.
      </p>
      <div class="mt-10 flex justify-center gap-x-6">
        <a href="#sobre-nosotros" class="rounded-md bg-indigo-600 px-4 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500">
          Conócenos
        </a>
        <a href="#servicios" class="text-sm font-semibold leading-6 text-white">
          Nuestros servicios <span aria-hidden="true">→</span>
        </a>
      </div>
    </div>
  </div>
</section>


      <!-- CLIENTES ACTUALIZADO -->
<section id="clientes" class="bg-gray-50 pt-2 sm:pt-2 lg:pt-4 pb-8 sm:pb-10 lg:pb-10">
  <div class="max-w-7xl mx-auto px-0 py-0 lg:px-20">
    <div class="mt-8 grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-6 items-center justify-center">

      <!-- Línea 1 -->
      <div class="flex justify-center items-center">
        <img class="h-8 object-contain saturate-75" src="/img/latam.png?v=2" alt="Latam" loading="lazy" />
      </div>
      <div class="flex justify-center items-center">
        <img class="h-8 object-contain saturate-75" src="/img/dashboard/essity.svg?v=2" alt="Essity" loading="lazy" />
      </div>
      <div class="flex justify-center items-center">
        <img class="h-10 object-contain saturate-75" src="/img/ripley.png?v=2" alt="Ripley" loading="lazy" />
      </div>
      <div class="flex justify-center items-center">
        <img class="h-8 object-contain saturate-75" src="/img/walmart.png?v=2" alt="Walmart" loading="lazy" />
      </div>
      <div class="flex justify-center items-center">
        <img class="h-8 object-contain saturate-75" src="/img/dashboard/deco.png?v=2" alt="Deco Muebles" loading="lazy" />
      </div>

      <!-- Línea 2 -->
      <div class="flex justify-center items-center">
        <img class="h-14 object-contain saturate-75" src="/img/dashboard/fruna.webp?v=2" alt="Fruna" loading="lazy" />
      </div>
      <div class="flex justify-center items-center">
        <img class="h-12 object-contain saturate-75" src="/img/dashboard/fibox.png?v=2" alt="Fibox" loading="lazy" />
      </div>
      <div class="flex justify-center items-center">
        <img class="h-6 object-contain saturate-75" src="/img/tottus.png?v=2" alt="Tottus" loading="lazy" />
      </div>
      <div class="flex justify-center items-center">
        <img class="h-12 object-contain saturate-75" src="/img/dashboard/falabella.png?v=2" alt="Falabella" loading="lazy" />
      </div>
      <div class="flex justify-center items-center">
        <img class="h-14 object-contain saturate-75" src="/img/dashboard/prisa.png?v=2" alt="Prisa" loading="lazy" />
      </div>

      <!-- Línea 3 -->
      <div class="flex justify-center items-center">
        <img class="h-6 object-contain saturate-75" src="/img/dashboard/canontex.png?v=2" alt="Canontex" loading="lazy" />
      </div>
      <div class="flex justify-center items-center">
        <img class="h-8 object-contain saturate-75" src="/img/paris.png?v=2" alt="Paris" loading="lazy" />
      </div>
      <div class="flex justify-center items-center">
        <img class="h-16 object-contain saturate-75" src="/img/dashboard/geo.png?v=2" alt="Geoprospec" loading="lazy" />
      </div>
      <div class="flex justify-center items-center">
        <img class="h-16 object-contain saturate-75" src="/img/contrumart.jpeg?v=2" alt="Construmart" loading="lazy" />
      </div>
      <div class="flex justify-center items-center">
        <img class="h-8 object-contain saturate-75" src="/img/tecnopapel.png?v=2" alt="Tecnopapel" loading="lazy" />
      </div>
    </div>
  </div>
</section>


      <!-- PANORAMA LOGÍSTICO -->
      <section id="panorama-logistico" class="bg-white py-6">
  <div class="mx-auto max-w-4xl text-center">
    <p class="text-4xl font-bold tracking-tight text-gray-900">
      Panorama Logístico
    </p>
    <p class="mt-4 text-lg text-gray-700 text-justify">
      Factores clave que impactan el transporte de carga en Chile, desde la economía hasta la sostenibilidad.
    </p>
  </div>
  <div class="mt-8 grid grid-cols-1 md:grid-cols-3 gap-8 max-w-7xl mx-auto px-6 lg:px-8">
    <div
      v-for="(item, index) in panoramaItems"
      :key="index"
      class="bg-gray-100 p-6 rounded-lg shadow-md hover:bg-gray-200 transition"
    >
      <h3 class="text-lg font-semibold text-gray-900">{{ item.title }}</h3>
      <p class="mt-4 text-lg text-gray-700 text-justify">{{ item.description }}</p>
      <a
        :href="item.link"
        target="_blank"
        rel="noopener"
        class="inline-block mt-4 text-indigo-600 font-semibold hover:underline text-sm"
        aria-label="Ver más sobre {{ item.title }}"
      >
        Ver más
      </a>
    </div>
  </div>
      </section>

      <!-- SOBRE NOSOTROS -->
      <section id="sobre-nosotros" class="bg-gray-100 py-12">
  <div class="mx-auto max-w-4xl text-center">
    <p class="text-4xl font-bold tracking-tight text-gray-900">
      Sobre Nosotros
    </p>
    <p class="mt-4 text-lg text-gray-700 text-justify">
      Desde nuestros inicios hace más de 25 años, en Transportes SCAR hemos recorrido miles de kilómetros en las rutas más exigentes de Chile, transportando cargas que requieren máxima seguridad y eficiencia. Con un equipo comprometido y tecnología de punta, hemos establecido un estándar de calidad que nos posiciona como empresa destacada en la industria.
    </p>
    <p class="mt-4 text-lg text-gray-700 text-justify">
      Creemos en la transparencia, el compromiso y la excelencia. Nos esforzamos por ofrecer un servicio de transporte seguro, responsable y alineado con los más altos estándares laborales y medioambientales.
    </p>
  </div>
      </section>

      <!-- NUESTROS SERVICIOS -->
      <section id="servicios" class="bg-white py-12">
  <div class="mx-auto max-w-4xl text-center">
    <p class="text-4xl font-bold tracking-tight text-gray-900">
      Nuestro Servicio
    </p>
    <p class="mt-4 text-lg text-gray-700 text-justify">
      Nos especializamos en soluciones logísticas adaptadas a cada necesidad, basadas en experiencia, tecnología y relaciones de confianza.
    </p>
  </div>
  <div class="mt-8 grid grid-cols-1 gap-12 sm:grid-cols-2 lg:grid-cols-2 max-w-7xl mx-auto px-6 lg:px-8">
    <div v-for="(item, i) in services" :key="i" class="relative pl-16">
      <div class="absolute left-0 top-0 flex items-center justify-center h-12 w-12 rounded-md bg-indigo-600">
        <component :is="item.icon" class="h-6 w-6 text-white" aria-hidden="true" />
      </div>
      <h3 class="text-lg font-semibold text-gray-900">{{ item.name }}</h3>
      <p class="mt-2 text-lg text-gray-700 text-justify">{{ item.description }}</p>
    </div>
  </div>
      </section>

      <!-- COMPROMISO Y ALIANZAS (incluye Educación y Bienestar) -->
      <section id="compromiso" class="bg-gray-50 py-12">
    <div class="mx-auto max-w-4xl text-center">
      <h2 class="text-4xl font-bold tracking-tight text-gray-900">
        Compromiso y Alianzas
      </h2>
      <p class="mt-4 text-lg text-gray-700 text-justify">
        En Transportes SCAR trabajamos junto a nuestros clientes e instituciones estratégicas para cumplir con auditorías exigentes, fortalecer el cumplimiento normativo, mejorar continuamente nuestros procesos y promover la formación continua de nuestro equipo.
      </p>
    </div>

    <div class="mt-8 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 max-w-7xl mx-auto px-6 lg:px-8">
      <FlashCard
        v-for="(item, i) in items"
        :key="i"
        :title="item.title"
        :description="item.description"
        :image="item.image"
      />
    </div>
  </section>

      <!-- CTA SECTION -->
<section class="relative isolate mt-0 px-6 py-0 sm:py-16 lg:px-8 bg-gray-900">
  <svg
    class="absolute inset-0 -z-10 w-full h-full stroke-white/10 [mask-image:radial-gradient(100%_100%_at_top_right,white,transparent)]"
    aria-hidden="true"
  >
    <defs>
      <pattern
        id="1d4240dd-898f-445f-932d-e2872fd12de3"
        width="200"
        height="200"
        x="50%"
        y="0"
        patternUnits="userSpaceOnUse"
      >
        <path d="M.5 200V.5H200" fill="none" />
      </pattern>
    </defs>
    <svg x="50%" y="0" class="overflow-visible fill-gray-800/20">
      <path
        d="M-200 0h201v201h-201Z M600 0h201v201h-201Z M-400 600h201v201h-201Z M200 800h201v201h-201Z"
        stroke-width="0"
      />
    </svg>
    <rect width="100%" height="100%" stroke-width="0" fill="url(#1d4240dd-898f-445f-932d-e2872fd12de3)" />
  </svg>
  <div
    class="absolute inset-x-0 top-10 -z-10 flex transform-gpu justify-center overflow-hidden blur-3xl"
    aria-hidden="true"
  >
    <div
      class="aspect-[1108/632] w-[69.25rem] flex-none bg-gradient-to-r from-[#80caff] to-[#4f46e5] opacity-20"
      style="clip-path: polygon(73.6% 51.7%, 91.7% 11.8%, 100% 46.4%, 97.4% 82.2%, 92.5% 84.9%, 75.7% 64%, 55.3% 47.5%, 46.5% 49.4%, 45% 62.9%, 50.3% 87.2%, 21.3% 64.1%, 0.1% 100%, 5.4% 51.1%, 21.4% 63.9%, 58.9% 0.2%, 73.6% 51.7%)"
    ></div>
  </div>
  <div class="mx-auto max-w-2xl text-center">
    <h2 class="text-4xl font-bold tracking-tight text-white">
      Transportes SCAR: Liderando el transporte de carga en Chile
    </h2>
    <p class="mx-auto mt-6 max-w-xl text-lg text-gray-300">
      Con inversiones en tecnología avanzada y una estrategia de mejora continua, optimizamos procesos, reducimos costos operativos y garantizamos entregas puntuales con la máxima seguridad.
    </p>
    <div class="mt-10 flex items-center justify-center gap-x-6">
      <a
        href="#contacto"
        class="rounded-md bg-white px-3.5 py-2.5 text-sm font-semibold text-gray-900 shadow-sm hover:bg-gray-100 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-white"
        aria-label="Alianza Transportes"
      >
        Alianza Transportes
      </a>
      <Link
        :href="route('register')"
        class="text-sm font-semibold text-white"
        aria-label="Conduce con Nosotros"
      >
        Conduce con Nosotros <span aria-hidden="true">→</span>
      </Link>
    </div>
  </div>
</section>

      <!-- ESTADÍSTICAS Y COMPROMISO -->
      <section class="bg-gray-100 py-12">
  <div class="mx-auto max-w-4xl text-center">
    <p class="text-4xl font-bold tracking-tight text-gray-900">
      Confiado por cientos de clientes y colaboradores en todo Chile
    </p>
    <p class="mt-4 text-lg text-gray-700 text-justify">
      El mercado del transporte de carga en Chile crece con un 5.61% de alza anual. En Transportes SCAR no solo respondemos con eficiencia y costos competitivos, sino que además invertimos en el desarrollo de nuestro equipo. Creemos que un transporte seguro comienza con personas capacitadas, por eso ofrecemos programas de formación continua alineados con las últimas normativas.
    </p>
    <p class="mt-4 text-lg text-gray-700 text-justify">
      Nuestra cultura organizacional promueve el autocuidado, el respeto y la mejora constante. Nos importa el bienestar de quienes mueven a Chile, y eso se refleja en la confianza de nuestros clientes y en el compromiso de nuestros trabajadores.
    </p>
  </div>
  <dl class="mt-10 mx-auto max-w-7xl grid grid-cols-1 gap-x-8 gap-y-10 text-gray-900 sm:grid-cols-2 lg:grid-cols-4 px-6 lg:px-8">
    <div v-for="stat in stats" :key="stat.id" class="flex flex-col gap-y-3 border-l border-gray-300 pl-6">
      <dt class="text-sm font-semibold">{{ stat.name }}</dt>
      <dd class="order-first text-3xl font-bold tracking-tight">{{ stat.value }}</dd>
    </div>
  </dl>
      </section>



    </main>
    <!-- Footer SCAR -->
<footer class="bg-gray-900">
  <div class="mx-auto max-w-7xl px-6 pb-8 pt-12 sm:pt-24 lg:px-8 lg:pt-16">
    <div class="xl:grid xl:grid-cols-3 xl:gap-8">
      <img class="h-32" src="/img/logoscar.png" alt="Transportes SCAR" />
      <div class="mt-16 grid grid-cols-2 gap-8 xl:col-span-2 xl:mt-0">
        <div class="md:grid md:grid-cols-2 md:gap-8">
          <div>
            <h3 class="text-sm font-semibold text-white">SCAR</h3>
            <ul role="list" class="mt-6 space-y-4">
              <li>
                <a href="#sobre-nosotros" class="text-sm text-gray-400 hover:text-white">
                  Nuestra Historia
                </a>
              </li>
              <li>
                <a href="#servicios" class="text-sm text-gray-400 hover:text-white">
                  Servicios de Transporte
                </a>
              </li>
            </ul>
          </div>
          <div class="mt-10 md:mt-0">
            <h3 class="text-sm font-semibold text-white">Soporte</h3>
            <ul role="list" class="mt-6 space-y-4">
              <li>
                <a href="#compromiso" class="text-sm text-gray-400 hover:text-white">
                  Compromisos y Alianzas
                </a>
              </li>
              <li>
                <a href="#contacto" class="text-sm text-gray-400 hover:text-white">
                  Contáctanos
                </a>
              </li>
            </ul>
          </div>
        </div>
        <div class="md:grid md:grid-cols-2 md:gap-8">
          <div>
            <h3 class="text-sm font-semibold text-white">Clientes</h3>
            <ul role="list" class="mt-6 space-y-4">
              <li>
                <a href="#clientes" class="text-sm text-gray-400 hover:text-white">
                  Empresas que confían
                </a>
              </li>
              <li>
                <a href="#panorama-logistico" class="text-sm text-gray-400 hover:text-white">
                  Panorama Logístico
                </a>
              </li>
            </ul>
          </div>
          <div class="mt-10 md:mt-0">
            <h3 class="text-sm font-semibold text-white">Legal</h3>
            <ul role="list" class="mt-6 space-y-4">
              <li>
                <a href="#" class="text-sm text-gray-400 hover:text-white">
                  Términos y Condiciones
                </a>
              </li>
              <li>
                <a href="#" class="text-sm text-gray-400 hover:text-white">
                  Política de Privacidad
                </a>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>

    <!-- Newsletter -->
    <div class="mt-16 border-t border-white/10 pt-8 sm:mt-20 lg:mt-24 lg:flex lg:items-center lg:justify-between">
      <div>
        <h3 class="text-sm font-semibold text-white">Suscríbete al boletín</h3>
        <p class="mt-2 text-sm text-gray-300">
          Recibe noticias, actualizaciones y novedades de Transportes SCAR.
        </p>
      </div>
      <form class="mt-6 sm:flex sm:max-w-md lg:mt-0">
        <label for="email-address" class="sr-only">Correo electrónico</label>
        <input
          type="email"
          name="email-address"
          id="email-address"
          autocomplete="email"
          required
          class="w-full rounded-md bg-white/5 px-3 py-1.5 text-white placeholder:text-gray-500 outline outline-1 outline-white/10 focus:outline-2 focus:outline-indigo-500 sm:w-56 sm:text-sm"
          placeholder="Tu correo electrónico"
        />
        <div class="mt-4 sm:ml-4 sm:mt-0">
          <button
            type="submit"
            class="flex w-full items-center justify-center rounded-md bg-indigo-500 px-3 py-2 text-sm font-semibold text-white shadow hover:bg-indigo-400 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-500"
          >
            Suscribirse
          </button>
        </div>
      </form>
    </div>

    <!-- Social + Copyright -->
    <div class="mt-8 border-t border-white/10 pt-8 md:flex md:items-center md:justify-between">
      <div class="flex gap-x-6 md:order-2">
        <a
          v-for="item in footerSocial"
          :key="item.name"
          :href="item.href"
          class="text-gray-400 hover:text-gray-300"
          target="_blank"
          rel="noopener noreferrer"
        >
          <span class="sr-only">{{ item.name }}</span>
          <component :is="item.icon" class="size-6" aria-hidden="true" />
        </a>
      </div>
      <p class="mt-8 text-sm text-gray-400 md:order-1 md:mt-0">
        &copy; 2025 Transportes SCAR. Todos los derechos reservados.
      </p>
    </div>
  </div>
</footer>




  </div>
</template>

<script setup>
import { Head, Link } from '@inertiajs/vue3'
import { ref, defineComponent, h } from 'vue'
import { Dialog, DialogPanel, Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue'
import { Bars3Icon, MinusSmallIcon, PlusSmallIcon, XMarkIcon } from '@heroicons/vue/24/outline'
import {
  ArrowPathIcon,
  CloudArrowUpIcon,
  FingerPrintIcon,
  LockClosedIcon,
} from '@heroicons/vue/20/solid'

// Datos del Header
const navigation = [
  { name: 'Inicio', href: '#inicio' },
  { name: 'Sobre Nosotros', href: '#sobre-nosotros' },
  { name: 'Servicios', href: '#servicios' },
  { name: 'Clientes', href: '#clientes' },
  { name: 'Compromiso', href: '#compromiso' },
  { name: 'Contacto', href: '#contacto' },
]

// Datos para la sección Panorama Logístico
const panoramaItems = [
  {
    title: 'Economía y Logística Nacional',
    description:
      'Las fluctuaciones en el precio del combustible y los costos logísticos demandan estrategias eficientes en un mercado altamente competitivo.',
    link: 'https://www.bcentral.cl/web/banco-central/series-estadisticas',
  },
  {
    title: 'Normas y Cumplimiento',
    description:
      'Garantizamos el estricto cumplimiento de las regulaciones del transporte de carga mediante auditorías y controles internos rigurosos.',
    link: 'https://www.subcontrataley.cl',
  },
  {
    title: 'Sostenibilidad y Medio Ambiente',
    description:
      'Implementamos iniciativas verdes para reducir la huella de carbono y promover un futuro sostenible en el transporte.',
    link: 'https://mma.gob.cl',
  },
]

// Datos para la sección Servicios
const services = [
  {
    name: 'Cobertura Nacional',
    description:
      'Operamos de norte a sur de Chile, asegurando rutas seguras y eficientes en todo el territorio.',
    icon: CloudArrowUpIcon,
  },
  {
    name: 'Seguridad Operativa',
    description:
      'Contamos con controles estrictos y auditorías regulares para garantizar la seguridad en cada viaje.',
    icon: LockClosedIcon,
  },
  {
    name: 'Innovación Tecnológica',
    description:
      'Adoptamos sistemas digitales avanzados para optimizar procesos, gestionar fletes y mejorar la transparencia.',
    icon: ArrowPathIcon,
  },
  {
    name: 'Relaciones de Confianza',
    description:
      'Colaboramos con empresas e instituciones líderes para mantener estándares de excelencia en el sector.',
    icon: FingerPrintIcon,
  },
]

// Datos para la sección Estadísticas
const stats = [
  { id: 1, name: 'Clientes y Colaboradores', value: '+100' },
  { id: 2, name: 'Tasa de crecimiento anual del sector', value: '5.61%' },
  { id: 3, name: 'Colaboradores capacitados', value: '100%' },
  { id: 4, name: 'Cumplimiento en tiempos de entrega', value: '+95%' },
]

// Iconos del Footer (Instagram y X)
const footerSocial = [
{
    name: 'Instagram',
    href: '#',
    icon: defineComponent({
      render: () =>
        h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
          h('path', {
            'fill-rule': 'evenodd',
            d: 'M12.315 2c2.43 0 2.784.013 3.808.06 1.064.049 1.791.218 2.427.465a4.902 4.902 0 011.772 1.153 4.902 4.902 0 011.153 1.772c.247.636.416 1.363.465 2.427.048 1.067.06 1.407.06 4.123v.08c0 2.643-.012 2.987-.06 4.043-.049 1.064-.218 1.791-.465 2.427a4.902 4.902 0 01-1.153 1.772 4.902 4.902 0 01-1.772 1.153c-.636.247-1.363.416-2.427.465-1.067.048-1.407.06-4.123.06h-.08c-2.643 0-2.987-.012-4.043-.06-1.064-.049-1.791-.218-2.427-.465a4.902 4.902 0 01-1.772-1.153 4.902 4.902 0 01-1.153-1.772c-.247-.636-.416-1.363-.465-2.427-.047-1.024-.06-1.379-.06-3.808v-.63c0-2.43.013-2.784.06-3.808.049-1.064.218-1.791.465-2.427a4.902 4.902 0 011.153-1.772A4.902 4.902 0 015.45 2.525c.636-.247 1.363-.416 2.427-.465C8.901 2.013 9.256 2 11.685 2h.63zm-.081 1.802h-.468c-2.456 0-2.784.011-3.807.058-.975.045-1.504.207-1.857.344-.467.182-.8.398-1.15.748-.35.35-.566.683-.748 1.15-.137.353-.3.882-.344 1.857-.047 1.023-.058 1.351-.058 3.807v.468c0 2.456.011 2.784.058 3.807.045.975.207 1.504.344 1.857.182.466.399.8.748 1.15.35.35.683.566 1.15.748.353.137.882.3 1.857.344 1.054.048 1.37.058 4.041.058h.08c2.597 0 2.917-.01 3.96-.058.976-.045 1.505-.207 1.858-.344.466-.182.8-.398 1.15-.748.35-.35.566-.683.748-1.15.137-.353.3-.882.344-1.857.048-1.055.058-1.37.058-4.041v-.08c0-2.597-.01-2.917-.058-3.96-.045-.976-.207-1.505-.344-1.858a3.097 3.097 0 00-.748-1.15 3.098 3.098 0 00-1.15-.748c-.353-.137-.882-.3-1.857-.344-1.023-.047-1.351-.058-3.807-.058zM12 6.865a5.135 5.135 0 110 10.27 5.135 5.135 0 010-10.27zm0 1.802a3.333 3.333 0 100 6.666 3.333 3.333 0 000-6.666zm5.338-3.205a1.2 1.2 0 110 2.4 1.2 1.2 0 010-2.4z',
            'clip-rule': 'evenodd',
          }),
        ]),
    }),
  },
  {
    name: 'X',
    href: '#',
    icon: defineComponent({
      render: () =>
        h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
          h('path', {
            d: 'M13.6823 10.6218L20.2391 3H18.6854L12.9921 9.61788L8.44486 3H3.2002L10.0765 13.0074L3.2002 21H4.75404L10.7663 14.0113L15.5685 21H20.8131L13.6819 10.6218H13.6823ZM11.5541 13.0956L10.8574 12.0991L5.31391 4.16971H7.70053L12.1742 10.5689L12.8709 11.5655L18.6861 19.8835H16.2995L11.5541 13.096V13.0956Z',
          }),
        ]),
    }),
  },
]

// Flags de autenticación (Jetstream)
defineProps({
  canLogin: { type: Boolean },
  canRegister: { type: Boolean },
  laravelVersion: { type: String, required: true },
  phpVersion: { type: String, required: true },
})

// Estado para el menú móvil
const mobileMenuOpen = ref(false)
import FlashCard from '@/Components/FlashCard.vue'

const items = [
  {
    title: 'ACHS Virtual & Gestión',
    description:
      'Herramientas digitales de capacitación y gestión avanzada en seguridad y salud laboral, promoviendo el bienestar y cumplimiento normativo en toda la organización.',
    image: '/img/achs.png',
  },
  {
    title: 'Subcontralaley',
    description:
      'Sistema de monitoreo y gestión para asegurar el cumplimiento normativo de trabajadores y empresas colaboradoras.',
    image: '/img/subcontrataley.png',
  },
  {
    title: 'Maquinaria para Construcción',
    description:
      'Nos aliamos con empresas líderes en arriendo de maquinaria para asegurar operaciones eficientes y seguras.',
    image: '/img/santaema.jpeg',
  },
  {
    title: 'Alianza con Transportes',
    description:
      'Establecemos convenios con empresas de transporte para ampliar nuestra cobertura logística a lo largo del país.',
    image: '/img/al.jpeg',
  },
]
</script>




