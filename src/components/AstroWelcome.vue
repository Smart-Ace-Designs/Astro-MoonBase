<script setup lang="ts">
import { ref } from "vue";

const launched = ref<boolean>(false);
const toggleAnimation = (event: MouseEvent) => {
  const button = event.currentTarget as HTMLButtonElement;
  const [addClass, removeClass] = launched.value
    ? [
        "animate-[descend_2s_ease-out_forwards]",
        "animate-[rise_2s_ease-out_forwards]",
      ]
    : [
        "animate-[rise_2s_ease-out_forwards]",
        "animate-[descend_2s_ease-out_forwards]",
      ];

  button.classList.add(addClass);
  button.classList.remove(removeClass);

  launched.value = !launched.value;
};
</script>

<template>
  <div
    role="region"
    aria-label="Welcome section"
    class="min-h-screen bg-slate-800 text-white"
  >
    <section aria-label="Hero section" class="hidden items-center md:flex">
      <div class="mx-auto flex w-full max-w-(--breakpoint-xl)">
        <h1 class="mx-auto my-8 text-4xl font-light uppercase">
          <span class="font-semibold text-yellow-600">Astro</span> |
          <span class="font-semibold text-[#41B883]">Vue</span> |
          <span class="font-semibold text-sky-400">Tailwind</span>
        </h1>
      </div>
    </section>

    <section aria-label="Content section" class="flex h-[85vh] flex-col">
      <div class="mx-auto mt-32 min-h-44 md:mt-2">
        <img
          class="size-60 scheme-light md:hidden"
          src="/favicon.svg"
          alt="Astro Logo"
        />
      </div>
      <div class="hidden items-center md:flex md:flex-1">
        <div class="mx-auto text-center">
          <h2 class="text-[clamp(4.5rem,8vw,6rem)] font-semibold uppercase">
            Moon
            <span class="text-yellow-600">
              {
              <span class="inline-block">
                <button
                  id="launch-button"
                  aria-label="Launch animation"
                  class="cursor-pointer rounded-full focus:outline-none"
                  @click="toggleAnimation"
                >
                  <img
                    class="size-[clamp(3.5rem,7vw,5rem)] scheme-light"
                    src="/favicon.svg"
                    alt="Astro Logo"
                  />
                </button>
              </span>
              }
            </span>
            Base
          </h2>
          <p class="my-6 text-3xl font-light">
            Coding in a most <em>peculiar</em> way
          </p>
        </div>
      </div>
    </section>
  </div>
</template>

<style>
@keyframes rise {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-300%);
  }
}

@keyframes descend {
  0% {
    transform: translateY(-300%);
  }
  100% {
    transform: translateY(0);
  }
}
</style>
