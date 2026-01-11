<script lang="ts">
  import { fade, scale } from 'svelte/transition';
  import { Home, ArrowLeft } from 'lucide-svelte';
  import Button from '$lib/components/ui/Button.svelte';
  import { page } from '$app/stores';

  function goBack() {
    window.history.back();
  }
</script>

<svelte:head>
  <title>404 - Page Not Found</title>
</svelte:head>

<div
  class="min-h-screen bg-gradient-to-br from-blue-50 via-white to-purple-50 dark:from-gray-900 dark:via-gray-800 dark:to-gray-900 flex items-center justify-center px-4"
  in:fade={{ duration: 300 }}
>
  <div class="max-w-2xl w-full text-center">
    <div>
      <h1
        class="text-9xl font-bold bg-gradient-to-r from-blue-600 to-purple-600 bg-clip-text text-transparent mb-4"
        in:scale={{ duration: 500, delay: 200 }}
      >
        404
      </h1>

      <h2
        class="text-3xl md:text-4xl font-bold text-gray-900 dark:text-white mb-4"
        in:fade={{ delay: 300 }}
      >
        Page Not Found
      </h2>

      <p class="text-lg text-gray-600 dark:text-gray-400 mb-8" in:fade={{ delay: 400 }}>
        Oops! The page you're looking for doesn't exist. It might have been moved or deleted.
      </p>

      <div class="flex flex-col sm:flex-row gap-4 justify-center" in:fade={{ delay: 500 }}>
        <a href="/">
          <Button size="lg">
            {#snippet children()}
              <Home class="mr-2" size={20} />
              Go Home
            {/snippet}
          </Button>
        </a>
        <Button variant="outline" size="lg" onclick={goBack}>
          {#snippet children()}
            <ArrowLeft class="mr-2" size={20} />
            Go Back
          {/snippet}
        </Button>
      </div>

      <div class="mt-16" in:fade={{ delay: 600 }}>
        <svg
          class="w-full max-w-md mx-auto"
          viewBox="0 0 400 300"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <circle cx="200" cy="150" r="100" class="fill-blue-100 dark:fill-blue-900/20" />
          <path
            d="M150 120 L170 140 L150 160"
            class="stroke-blue-600 dark:stroke-blue-400"
            stroke-width="8"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <path
            d="M250 120 L230 140 L250 160"
            class="stroke-purple-600 dark:stroke-purple-400"
            stroke-width="8"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </div>
    </div>
  </div>
</div>
