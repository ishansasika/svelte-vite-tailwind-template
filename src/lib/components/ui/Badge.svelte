<script lang="ts">
  interface Props {
    variant?: 'default' | 'primary' | 'success' | 'warning' | 'danger' | 'info';
    class?: string;
    children?: any;
  }

  let { variant = 'default', class: className = '', children }: Props = $props();

  const baseStyles = 'inline-flex items-center px-2.5 py-0.5 rounded-full text-xs font-medium';

  const variants = {
    default: 'bg-gray-100 text-gray-800 dark:bg-gray-700 dark:text-gray-300',
    primary: 'bg-blue-100 text-blue-800 dark:bg-blue-900 dark:text-blue-300',
    success: 'bg-green-100 text-green-800 dark:bg-green-900 dark:text-green-300',
    warning: 'bg-yellow-100 text-yellow-800 dark:bg-yellow-900 dark:text-yellow-300',
    danger: 'bg-red-100 text-red-800 dark:bg-red-900 dark:text-red-300',
    info: 'bg-cyan-100 text-cyan-800 dark:bg-cyan-900 dark:text-cyan-300',
  };

  const badgeClasses = `${baseStyles} ${variants[variant]} ${className}`;
</script>

<span class={badgeClasses}>
  {@render children?.()}
</span>
