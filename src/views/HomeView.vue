<script setup>
import {
  ArrowPathIcon,
  CheckIcon,
  CloudArrowUpIcon,
  FingerPrintIcon,
  LockClosedIcon
} from '@heroicons/vue/20/solid'

const tiers = [
  {
    name: 'Enregistrement',
    id: 'tier-freelancer',
    href: '#',
    price: '40€',
    priceSuffix: "l'heure",
    description: 'Description complète.',
    features: ['peut etre des features', 'peut etre des features', 'peut etre des features'],
    mostPopular: false
  },
  {
    name: 'Mixage',
    id: 'tier-startup',
    href: '#',
    price: '50€',
    priceSuffix: 'par son',
    description: 'Description complète.',
    features: ['peut etre des features', 'peut etre des features', 'peut etre des features'],
    mostPopular: true
  },
  {
    name: 'Mastering',
    id: 'tier-enterprise',
    href: '#',
    price: '50€',
    priceSuffix: 'par son',
    description: 'Description complète.',
    features: ['peut etre des features', 'peut etre des features', 'peut etre des features'],
    mostPopular: false
  }
]

const features = [
  {
    name: 'ENREGISTREMENT',
    description:
      "Nos ingénieurs du son s'occupent de vos enregistrements vocaux selon vos besoins.",
    icon: CloudArrowUpIcon
  },
  {
    name: 'MIXAGE / MASTER',
    description:
      'Offrez à votre morceau une qualité professionnelle grâce au mixage et au mastering de vos titres.',
    icon: LockClosedIcon
  },
  {
    name: 'VIDEO',
    description:
      'Nous réalisons toutes vos prises de vues. En intérieur, extérieur de nuit, en mouvement.',
    icon: ArrowPathIcon
  },
  {
    name: 'BEATMAKING',
    description:
      "Réalisez votre beat sur-mesure et bénéficiez d'un accompagnement par différents beatmakers.",
    icon: FingerPrintIcon
  }
]
</script>

<template>
  <div>
    <div class="relative isolate overflow-hidden pt-14 bg-neutral-900">
      <img
        src="@/assets/images/home.jpeg"
        alt=""
        class="absolute inset-0 -z-10 h-full w-full object-cover mix-blend-multiply"
      />
      <div
        class="absolute inset-x-0 -top-40 -z-10 transform-gpu overflow-hidden blur-3xl sm:-top-80"
        aria-hidden="true"
      >
        <div
          class="relative left-[calc(50%-11rem)] aspect-[1155/678] w-[36.125rem] -translate-x-1/2 rotate-[30deg] bg-gradient-to-tr from-[#ff80b5] to-[#9089fc] opacity-20 sm:left-[calc(50%-30rem)] sm:w-[72.1875rem]"
          style="
            clip-path: polygon(
              74.1% 44.1%,
              100% 61.6%,
              97.5% 26.9%,
              85.5% 0.1%,
              80.7% 2%,
              72.5% 32.5%,
              60.2% 62.4%,
              52.4% 68.1%,
              47.5% 58.3%,
              45.2% 34.5%,
              27.5% 76.7%,
              0.1% 64.9%,
              17.9% 100%,
              27.6% 76.8%,
              76.1% 97.7%,
              74.1% 44.1%
            );
          "
        />
      </div>
      <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-56">
        <div class="mb-8 flex justify-center">
          <img src="@/assets/images/logo.png" alt="" class="h-40" />
        </div>
        <div class="text-center">
          <h1>
            Votre studio 100%<br />
            RAP et R’n’B
          </h1>
          <p class="mt-6 leading">
            13 COURS D’HERBOUVILLE<br />
            69004 - LYON
          </p>
          <div class="mt-10 flex items-center justify-center gap-x-6">
            <button href="#" class="button-primary">Nous contactez</button>
            <a href="#">En savoir plus <span aria-hidden="true">→</span></a>
          </div>
        </div>
      </div>
      <div
        class="absolute inset-x-0 top-[calc(100%-13rem)] -z-10 transform-gpu overflow-hidden blur-3xl sm:top-[calc(100%-30rem)]"
        aria-hidden="true"
      >
        <div
          class="relative left-[calc(50%+3rem)] aspect-[1155/678] w-[36.125rem] -translate-x-1/2 bg-gradient-to-tr from-[#ff80b5] to-[#9089fc] opacity-20 sm:left-[calc(50%+36rem)] sm:w-[72.1875rem]"
          style="
            clip-path: polygon(
              74.1% 44.1%,
              100% 61.6%,
              97.5% 26.9%,
              85.5% 0.1%,
              80.7% 2%,
              72.5% 32.5%,
              60.2% 62.4%,
              52.4% 68.1%,
              47.5% 58.3%,
              45.2% 34.5%,
              27.5% 76.7%,
              0.1% 64.9%,
              17.9% 100%,
              27.6% 76.8%,
              76.1% 97.7%,
              74.1% 44.1%
            );
          "
        />
      </div>
    </div>

    <section>
      <div class="mx-auto max-w-4xl lg:text-center">
        <h2 class="tooltip">Projet</h2>
        <h2 class="mt-2">
          Notre equipe ous accompagne<br />
          dans tout vos projets
        </h2>
        <p class="mt-6 leading">
          Tout commence par une idée. Peut-être voulez-vous donner une nouvelle dimension à un
          passe-temps. Ou peut-être avez-vous un projet créatif que vous souhaitez partager avec le
          monde entier. Quel que soit votre cas, de l’enregistrement au mixage, de la vidéo au
          beatmaking, nous vous proposons une prestation complète qui s’adapte à votre univers
          artistique.
        </p>
      </div>
      <div class="mx-auto mt-16 max-w-2xl sm:mt-20 lg:mt-24 lg:max-w-4xl">
        <dl
          class="grid max-w-xl grid-cols-1 gap-x-8 gap-y-10 lg:max-w-none lg:grid-cols-2 lg:gap-y-16"
        >
          <div v-for="feature in features" :key="feature.name" class="relative pl-16">
            <dt class="text-base font-semibold leading-7 text-white">
              <div
                class="absolute left-0 top-0 flex h-10 w-10 items-center justify-center rounded-lg"
              >
                <component :is="feature.icon" class="h-6 w-6 text-fuchsia-300" aria-hidden="true" />
              </div>
              {{ feature.name }}
            </dt>
            <dd class="mt-2 text-base leading-7 text-neutral-300 text-justify">
              {{ feature.description }}
            </dd>
          </div>
        </dl>
      </div>
    </section>

    <section>
      <div class="mx-auto max-w-4xl text-center">
        <p class="tooltip">Pricing</p>
        <h2>Nos principaux tarifs</h2>
      </div>
      <p class="mx-auto mt-6 max-w-2xl text-center leading">un truc a dire surement</p>
      <div
        class="isolate mx-auto mt-10 grid max-w-md grid-cols-1 gap-8 lg:mx-0 lg:max-w-none lg:grid-cols-3"
      >
        <div
          v-for="tier in tiers"
          :key="tier.id"
          :class="[
            tier.mostPopular ? 'bg-white/5 ring-2 ring-fuchsia-500' : 'ring-1 ring-white/10',
            'rounded-3xl p-8 xl:p-10'
          ]"
        >
          <div class="flex items-center justify-between gap-x-4">
            <h3 :id="tier.id" class="text-lg font-semibold leading-8 text-white">
              {{ tier.name }}
            </h3>
            <p
              v-if="tier.mostPopular"
              class="rounded-full bg-fuchsia-500 py-1 px-2.5 text-xs font-semibold leading-5 text-white"
            >
              Most popular
            </p>
          </div>
          <p class="mt-4 text-sm leading-6 text-neutral-300">
            {{ tier.description }}
          </p>
          <p class="mt-6 flex items-baseline gap-x-1">
            <span class="text-4xl font-bold tracking-tight text-white">{{ tier.price }}</span>
            <span class="text-sm font-semibold leading-6 text-neutral-300">
              /{{ tier.priceSuffix }}</span
            >
          </p>
          <a
            :href="tier.href"
            :aria-describedby="tier.id"
            :class="[
              tier.mostPopular
                ? 'bg-fuchsia-500 text-white shadow-sm hover:bg-fuchsia-400 focus-visible:outline-fuchsia-500'
                : 'bg-white/10 text-white hover:bg-white/20 focus-visible:outline-white',
              'mt-6 block rounded-md py-2 px-3 text-center text-sm leading-6 font-semibold focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2'
            ]"
            >Buy plan</a
          >
          <ul role="list" class="mt-8 space-y-3 text-sm leading-6 text-neutral-300 xl:mt-10">
            <li v-for="feature in tier.features" :key="feature" class="flex gap-x-3">
              <CheckIcon class="h-6 w-5 flex-none text-white" aria-hidden="true" />
              {{ feature }}
            </li>
          </ul>
        </div>
      </div>
    </section>
  </div>
</template>
