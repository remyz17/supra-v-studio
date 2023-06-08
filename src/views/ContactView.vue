<script setup>
import VInput from '@/components/form/VInput.vue'
import VTextarea from '@/components/form/VTextarea.vue'
import { BuildingOffice2Icon, EnvelopeIcon, PhoneIcon } from '@heroicons/vue/24/outline'
</script>

<template>
  <div class="relative isolate pt-14">
    <div class="mx-auto grid max-w-7xl grid-cols-1 lg:grid-cols-2">
      <div class="relative px-6 pb-20 pt-24 sm:pt-32 lg:static lg:px-8 lg:py-48">
        <div class="mx-auto max-w-xl lg:mx-0 lg:max-w-lg">
          <div
            class="absolute inset-y-0 left-0 -z-10 w-full overflow-hidden ring-1 ring-white/5 lg:w-1/2"
          >
            <svg
              class="absolute inset-0 h-full w-full stroke-gray-700 [mask-image:radial-gradient(100%_100%_at_top_right,white,transparent)]"
              aria-hidden="true"
            >
              <defs>
                <pattern
                  id="54f88622-e7f8-4f1d-aaf9-c2f5e46dd1f2"
                  width="200"
                  height="200"
                  x="100%"
                  y="-1"
                  patternUnits="userSpaceOnUse"
                >
                  <path d="M130 200V.5M.5 .5H200" fill="none" />
                </pattern>
              </defs>
              <svg x="100%" y="-1" class="overflow-visible fill-gray-800/20">
                <path d="M-470.5 0h201v201h-201Z" stroke-width="0" />
              </svg>
              <rect
                width="100%"
                height="100%"
                stroke-width="0"
                fill="url(#54f88622-e7f8-4f1d-aaf9-c2f5e46dd1f2)"
              />
            </svg>
            <div
              class="absolute -left-56 top-[calc(100%-13rem)] transform-gpu blur-3xl lg:left-[max(-14rem,calc(100%-59rem))] lg:top-[calc(50%-7rem)]"
              aria-hidden="true"
            >
              <div
                class="aspect-[1155/678] w-[72.1875rem] bg-gradient-to-br from-[#ff80b5] to-[#9089fc] opacity-20"
                style="
                  clip-path: polygon(
                    74.1% 56.1%,
                    100% 38.6%,
                    97.5% 73.3%,
                    85.5% 100%,
                    80.7% 98.2%,
                    72.5% 67.7%,
                    60.2% 37.8%,
                    52.4% 32.2%,
                    47.5% 41.9%,
                    45.2% 65.8%,
                    27.5% 23.5%,
                    0.1% 35.4%,
                    17.9% 0.1%,
                    27.6% 23.5%,
                    76.1% 2.6%,
                    74.1% 56.1%
                  );
                "
              />
            </div>
          </div>
          <h2 class="text-3xl font-bold tracking-tight text-white">Contactez-nous</h2>
          <p class="mt-6 text-lg leading-8 text-gray-300">
            Proin volutpat consequat porttitor cras nullam gravida at. Orci molestie a eu arcu. Sed
            ut tincidunt integer elementum id sem. Arcu sed malesuada et magna.
          </p>
          <dl class="mt-10 space-y-4 text-base leading-7 text-gray-300">
            <div class="flex gap-x-4">
              <dt class="flex-none">
                <span class="sr-only">Address</span>
                <BuildingOffice2Icon class="h-7 w-6 text-gray-400" aria-hidden="true" />
              </dt>
              <dd>13 COURS D’HERBOUVILLE <br />69004 - LYON</dd>
            </div>
            <div class="flex gap-x-4">
              <dt class="flex-none">
                <span class="sr-only">Telephone</span>
                <PhoneIcon class="h-7 w-6 text-gray-400" aria-hidden="true" />
              </dt>
              <dd>
                <a class="hover:text-white" href="tel:+1 (555) 234-5678">+1 (555) 234-5678</a>
              </dd>
            </div>
            <div class="flex gap-x-4">
              <dt class="flex-none">
                <span class="sr-only">Email</span>
                <EnvelopeIcon class="h-7 w-6 text-gray-400" aria-hidden="true" />
              </dt>
              <dd>
                <a class="hover:text-white" href="info@supra-v-studio.fr">info@supra-v-studio.fr</a>
              </dd>
            </div>
          </dl>
        </div>
      </div>
      <form action="#" method="POST" class="px-6 pb-24 pt-20 sm:pb-32 lg:px-8 lg:py-48">
        <div class="mx-auto max-w-xl lg:mr-0 lg:max-w-lg">
          <div class="grid grid-cols-1 gap-x-8 gap-y-6 sm:grid-cols-2">
            <div>
              <VInput identifier="firstname" label="Prénom" type="text" />
            </div>
            <div>
              <VInput identifier="lastname" label="Nom" type="text" />
            </div>
            <div class="sm:col-span-2">
              <VInput identifier="email" label="Email" type="email" />
            </div>
            <div class="sm:col-span-2">
              <VInput
                identifier="phone"
                label="Numéro de téléphone"
                type="text"
                placeholder="+41 00 000 00 00"
              />
            </div>
            <div class="sm:col-span-2">
              <VInput identifier="subject" label="Sujet" type="text" />
            </div>
            <div class="sm:col-span-2">
              <VTextarea identifier="message" label="Message" :rows="4" />
            </div>
          </div>
          <div class="mt-8 flex justify-end">
            <button type="submit" class="button-primary">Envoyer</button>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>
