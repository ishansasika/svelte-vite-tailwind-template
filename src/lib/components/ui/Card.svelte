<script lang="ts">
  import { fade, scale } from 'svelte/transition';

  interface Props {
    hover?: boolean;
    class?: string;
    children?: any;
  }

  let { hover = false, class: className = '', children }: Props = $props();

  const baseStyles = 'bg-white dark:bg-gray-800 rounded-xl shadow-lg overflow-hidden';
  const hoverStyles = hover
    ? 'transition-all duration-300 hover:shadow-2xl hover:-translate-y-1'
    : '';

  const cardClasses = `${baseStyles} ${hoverStyles} ${className}`;
</script>

<div class={cardClasses} transition:scale={{ duration: 300 }}>
  {@render children?.()}
</div>
