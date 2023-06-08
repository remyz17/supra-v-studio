<script setup>
import { Dialog, DialogPanel, TransitionChild, TransitionRoot } from '@headlessui/vue'
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/24/outline'
import { ref } from 'vue'

const navigation = [
  { name: 'Home', href: '/' },
  { name: 'Tarifs', href: '#' },
  { name: 'Label', href: '#' },
  { name: 'Book', href: '#' },
  { name: 'Contact', href: '/contact' }
]

const mobileMenuOpen = ref(false)

const closeMenu = () => (mobileMenuOpen.value = false)
</script>

<template>
  <header class="fixed backdrop-filter backdrop-blur-sm inset-x-0 top-0 z-50 shadow">
    <nav class="flex items-center justify-between p-6 lg:px-8" aria-label="Global">
      <div class="flex lg:flex-1">
        <router-link to="/" class="-m-1.5 p-1.5">
          <img class="h-8 w-auto" src="@/assets/images/logo.png" alt="" />
        </router-link>
      </div>
      <div class="flex lg:hidden">
        <button
          type="button"
          class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-neutral-400"
          @click="mobileMenuOpen = true"
        >
          <span class="sr-only">Open main menu</span>
          <Bars3Icon class="h-6 w-6" aria-hidden="true" />
        </button>
      </div>
      <div class="hidden lg:flex lg:gap-x-12">
        <router-link
          v-for="item in navigation"
          :key="item.name"
          :to="item.href"
          class="text-sm font-semibold leading-6 text-white border-b-2 border-transparent hover:border-fuchsia-300 transition-all"
          exact-active-class="border-fuchsia-300"
          >{{ item.name }}</router-link
        >
      </div>
      <div class="hidden lg:flex lg:flex-1 lg:justify-end">
        <router-link to="#" class="text-sm font-semibold leading-6 text-white"
          >Log in <span aria-hidden="true">&rarr;</span></router-link
        >
      </div>
    </nav>
    <TransitionRoot as="template" :show="mobileMenuOpen">
      <Dialog as="div" class="relative z-50 lg:hidden" @close="closeMenu()">
        <TransitionChild
          as="template"
          enter="ease-in-out duration-500"
          enter-from="opacity-0"
          enter-to="opacity-100"
          leave="ease-in-out duration-500"
          leave-from="opacity-100"
          leave-to="opacity-0"
        >
          <div class="fixed inset-0 bg-gray-900/80 transition-opacity" />
        </TransitionChild>

        <div class="fixed inset-0 overflow-hidden">
          <div class="absolute inset-0 overflow-hidden">
            <div class="pointer-events-none fixed inset-y-0 right-0 flex max-w-full">
              <TransitionChild
                as="template"
                enter="transform transition ease-out sm:ease-in-out duration-300 sm:duration-500"
                enter-from="opacity-0 sm:translate-x-full"
                enter-to="opacity-100 sm:translate-x-0"
                leave="transform transition ease-in sm:ease-in-out duration-300 sm:duration-500"
                leave-from="opacity-100 sm:translate-x-0"
                leave-to="opacity-0 sm:translate-x-full"
              >
                <DialogPanel class="pointer-events-auto w-screen sm:max-w-md">
                  <div
                    class="flex h-full flex-col overflow-y-auto bg-neutral-900 px-6 py-6 shadow-xl"
                  >
                    <div class="flex items-center justify-between">
                      <router-link to="/" class="-m-1.5 p-1.5">
                        <img class="h-8 w-auto" src="@/assets/images/logo.png" alt="" />
                      </router-link>
                      <button
                        type="button"
                        class="-m-2.5 rounded-md p-2.5 text-neutral-400"
                        @click="closeMenu()"
                      >
                        <XMarkIcon class="h-6 w-6" aria-hidden="true" />
                      </button>
                    </div>
                    <div class="mt-6 flow-root">
                      <div class="-my-6 divide-y divide-neutral-500/25">
                        <div class="space-y-2 py-6">
                          <router-link
                            v-for="item in navigation"
                            :key="item.name"
                            :to="item.href"
                            custom
                            v-slot="{ href, navigate }"
                          >
                            <a
                              :href="href"
                              class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-neutral-800"
                              @click.prevent="navigate(), closeMenu()"
                              >{{ item.name }}</a
                            >
                          </router-link>
                        </div>
                        <div class="py-6">
                          <router-link
                            to="#"
                            class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-white hover:bg-neutral-800"
                            >Log in</router-link
                          >
                        </div>
                      </div>
                    </div>
                  </div>
                </DialogPanel>
              </TransitionChild>
            </div>
          </div>
        </div>
      </Dialog>
    </TransitionRoot>
    <!-- <TransitionRoot as="template" :show="mobileMenuOpen">
      <Dialog as="div" class="relative z-50 lg:hidden" @close="closeMenu()" :open="mobileMenuOpen">
        <TransitionChild
          as="template"
          enter="transition-opacity ease-linear duration-300"
          enter-from="opacity-0"
          enter-to="opacity-100"
          leave="transition-opacity ease-linear duration-300"
          leave-from="opacity-100"
          leave-to="opacity-0"
        >
          <div class="fixed inset-0 bg-neutral-900/80" />
        </TransitionChild>
        <div class="fixed inset-0 flex">
          <TransitionChild
            as="template"
            enter="transition ease-out sm:ease-in-out duration-300 sm:duration-500 sm:transform"
            enter-from="opacity-0 sm:translate-x-full"
            enter-to="opacity-100 sm:translate-x-0"
            leave="transition ease-in sm:ease-in-out duration-300 sm:duration-500 sm:transform"
            leave-from="opacity-100 sm:translate-x-0"
            leave-to="opacity-0 sm:translate-x-full"
          >
            <DialogPanel
              class="fixed inset-y-0 right-0 z-50 w-full overflow-y-auto bg-neutral-900 px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-white/10"
            >
              <div class="flex items-center justify-between">
                <router-link to="/" class="-m-1.5 p-1.5">
                  <img class="h-8 w-auto" src="@/assets/images/logo.png" alt="" />
                </router-link>
                <button
                  type="button"
                  class="-m-2.5 rounded-md p-2.5 text-neutral-400"
                  @click="closeMenu()"
                >
                  <XMarkIcon class="h-6 w-6" aria-hidden="true" />
                </button>
              </div>
              <div class="mt-6 flow-root">
                <div class="-my-6 divide-y divide-neutral-500/25">
                  <div class="space-y-2 py-6">
                    <router-link
                      v-for="item in navigation"
                      :key="item.name"
                      :to="item.href"
                      custom
                      v-slot="{ href, navigate }"
                    >
                      <a
                        :href="href"
                        class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-white hover:bg-neutral-800"
                        @click.prevent="navigate(), closeMenu()"
                        >{{ item.name }}</a
                      >
                    </router-link>
                  </div>
                  <div class="py-6">
                    <router-link
                      to="#"
                      class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-white hover:bg-neutral-800"
                      >Log in</router-link
                    >
                  </div>
                </div>
              </div>
            </DialogPanel>
          </TransitionChild>
        </div>
      </Dialog>
    </TransitionRoot> -->
  </header>
</template>
