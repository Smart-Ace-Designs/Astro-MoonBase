<script setup lang="ts">
import { ref } from "vue";

const launched = ref<boolean>(false);
const toggleAnimation = () => {
  launched.value = !launched.value;
};
</script>

<template>
  <main class="min-h-screen bg-slate-800 text-white">
    <header class="hidden items-center md:flex">
      <div class="mx-auto flex w-full max-w-(--breakpoint-xl)">
        <p class="mx-auto my-8 text-4xl font-light uppercase">
          <span class="font-semibold text-yellow-600">Astro</span> |
          <span class="font-semibold text-[#41B883]">Vue</span> |
          <span class="font-semibold text-sky-400">Tailwind</span>
        </p>
      </div>
    </header>

    <section aria-labelledby="welcome-heading" class="flex h-[85vh] flex-col">
      <div class="mx-auto mt-32 min-h-44 md:mt-2">
        <img class="size-60 md:hidden" src="/favicon.svg" alt="Astro Logo" />
      </div>
      <div class="hidden items-center md:flex md:flex-1">
        <div class="mx-auto px-4 text-center">
          <h1 id="welcome-heading" class="text-[clamp(4.5rem,8vw,6rem)] font-semibold uppercase">
            Moon
            <span class="text-yellow-600">
              <span aria-hidden="true">{</span>
              <button
                type="button"
                aria-label="Toggle launch animation"
                :aria-pressed="launched"
                :class="launched ? 'translate-y-[-300%]' : 'translate-y-0'"
                class="inline-block cursor-pointer rounded-full transition-transform duration-2000 ease-out focus-visible:outline-2 focus-visible:outline-offset-4 motion-reduce:translate-y-0 motion-reduce:transition-none"
                @click="toggleAnimation"
              >
                <img class="size-[clamp(3.5rem,7vw,5rem)]" src="/favicon.svg" alt="Astro Logo" />
              </button>
              <span aria-hidden="true">}</span>
            </span>
            Base
          </h1>
          <p class="my-6 text-3xl font-light">Coding in a most <em>peculiar</em> way</p>
        </div>
      </div>
    </section>
  </main>
</template>
