<script lang="ts">
  import { page } from '$app/stores';

  let isMenuOpen = $state(false);

  const navLinks = [
    { path: '/', label: 'Home' },
    { path: '/about', label: 'About' },
    { path: '/services', label: 'Services' },
    { path: '/contact', label: 'Contact' },
  ];

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }

  function closeMenu() {
    isMenuOpen = false;
  }

  $effect(() => {
    // Close menu when route changes
    $page.url.pathname;
    isMenuOpen = false;
  });
</script>

<header class="bg-white dark:bg-gray-900 shadow-md sticky top-0 z-50">
  <nav class="container mx-auto px-4 py-4">
    <div class="flex justify-between items-center">
      <!-- Logo -->
      <a href="/" class="flex items-center space-x-2">
        <div class="w-10 h-10 bg-gradient-to-br from-blue-500 to-purple-600 rounded-lg flex items-center justify-center">
          <span class="text-white font-bold text-xl">S</span>
        </div>
        <span class="text-xl font-bold text-gray-900 dark:text-white">
          SvelteKit
        </span>
      </a>

      <!-- Desktop Navigation -->
      <ul class="hidden md:flex items-center space-x-8">
        {#each navLinks as link}
          <li>
            <a
              href={link.path}
              class="font-medium transition-colors {$page.url.pathname === link.path
                ? 'text-blue-600 dark:text-blue-400'
                : 'text-gray-700 dark:text-gray-300 hover:text-blue-600 dark:hover:text-blue-400'}"
            >
              {link.label}
            </a>
          </li>
        {/each}
      </ul>

      <!-- GitHub Link & CTA Button -->
      <div class="hidden md:flex items-center space-x-4">
        <a
          href="https://github.com/ishansasika/svelte-vite-tailwind-template"
          target="_blank"
          rel="noopener noreferrer"
          class="text-gray-700 dark:text-gray-300 hover:text-blue-600 dark:hover:text-blue-400 transition-colors"
          aria-label="View source on GitHub"
        >
          <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
            <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
          </svg>
        </a>
        <a
          href="/contact"
          class="px-6 py-2 bg-gradient-to-r from-blue-500 to-purple-600 text-white rounded-lg font-medium hover:shadow-lg transition-shadow"
        >
          Get Started
        </a>
      </div>

      <!-- Mobile Menu Button -->
      <button
        onclick={toggleMenu}
        class="md:hidden text-gray-700 dark:text-gray-300"
        aria-label="Toggle menu"
      >
        <svg
          class="w-6 h-6"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
        >
          {#if isMenuOpen}
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            />
          {:else}
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
          {/if}
        </svg>
      </button>
    </div>

    <!-- Mobile Menu -->
    {#if isMenuOpen}
      <div class="md:hidden mt-4 pb-4">
        <ul class="space-y-4">
          {#each navLinks as link}
            <li>
              <a
                href={link.path}
                onclick={closeMenu}
                class="block font-medium transition-colors {$page.url.pathname === link.path
                  ? 'text-blue-600 dark:text-blue-400'
                  : 'text-gray-700 dark:text-gray-300'}"
              >
                {link.label}
              </a>
            </li>
          {/each}
          <li>
            <a
              href="https://github.com/ishansasika/svelte-vite-tailwind-template"
              target="_blank"
              rel="noopener noreferrer"
              onclick={closeMenu}
              class="flex items-center space-x-2 font-medium text-gray-700 dark:text-gray-300"
            >
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
              </svg>
              <span>View Source Code</span>
            </a>
          </li>
          <li>
            <a
              href="/contact"
              onclick={closeMenu}
              class="block px-6 py-2 bg-gradient-to-r from-blue-500 to-purple-600 text-white rounded-lg font-medium text-center"
            >
              Get Started
            </a>
          </li>
        </ul>
      </div>
    {/if}
  </nav>
</header>
