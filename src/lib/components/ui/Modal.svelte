<script lang="ts">
  import { fade, scale } from 'svelte/transition';
  import { X } from 'lucide-svelte';

  interface Props {
    isOpen?: boolean;
    onClose?: () => void;
    title?: string;
    size?: 'sm' | 'md' | 'lg' | 'xl';
    children?: any;
  }

  let { isOpen = $bindable(false), onClose, title, size = 'md', children }: Props = $props();

  const sizes = {
    sm: 'max-w-md',
    md: 'max-w-lg',
    lg: 'max-w-2xl',
    xl: 'max-w-4xl',
  };

  $effect(() => {
    if (isOpen) {
      document.body.style.overflow = 'hidden';
    } else {
      document.body.style.overflow = 'unset';
    }

    return () => {
      document.body.style.overflow = 'unset';
    };
  });

  function handleClose() {
    isOpen = false;
    onClose?.();
  }
</script>

{#if isOpen}
  <div
    class="fixed inset-0 bg-black/60 backdrop-blur-sm z-50"
    transition:fade={{ duration: 200 }}
    onclick={handleClose}
    role="button"
    tabindex="0"
    onkeydown={(e) => e.key === 'Escape' && handleClose()}
  ></div>

  <div class="fixed inset-0 z-50 flex items-center justify-center p-4">
    <div
      class="relative bg-white dark:bg-gray-800 rounded-xl shadow-2xl w-full {sizes[size]}"
      transition:scale={{ duration: 200 }}
    >
      {#if title}
        <div class="flex items-center justify-between px-6 py-4 border-b border-gray-200 dark:border-gray-700">
          <h3 class="text-lg font-semibold text-gray-900 dark:text-white">{title}</h3>
          <button
            onclick={handleClose}
            class="text-gray-400 hover:text-gray-600 dark:hover:text-gray-300 transition-colors"
          >
            <X size={20} />
          </button>
        </div>
      {:else}
        <button
          onclick={handleClose}
          class="absolute top-4 right-4 text-gray-400 hover:text-gray-600 dark:hover:text-gray-300 transition-colors z-10"
        >
          <X size={20} />
        </button>
      {/if}

      <div class="px-6 py-4">
        {@render children?.()}
      </div>
    </div>
  </div>
{/if}
