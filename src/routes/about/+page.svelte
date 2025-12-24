<script lang="ts">
  const values = [
    {
      icon: '🚀',
      title: 'Innovation',
      description: 'Pushing the boundaries of what\'s possible with modern web technologies'
    },
    {
      icon: '💡',
      title: 'Simplicity',
      description: 'Making complex things simple and accessible to all developers'
    },
    {
      icon: '🎯',
      title: 'Quality',
      description: 'Delivering exceptional code quality and user experiences'
    }
  ];

  const team = [
    {
      name: 'Alex Johnson',
      role: 'Lead Developer',
      image: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=400&h=400&fit=crop'
    },
    {
      name: 'Sarah Chen',
      role: 'UI/UX Designer',
      image: 'https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=400&h=400&fit=crop'
    },
    {
      name: 'Mike Williams',
      role: 'DevOps Engineer',
      image: 'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?w=400&h=400&fit=crop'
    }
  ];
</script>

<div>
  <!-- Hero Section -->
  <section class="bg-gradient-to-br from-blue-50 to-purple-50 dark:from-gray-900 dark:to-gray-800 py-20">
    <div class="container mx-auto px-4">
      <div class="max-w-3xl mx-auto text-center">
        <h1 class="text-5xl font-bold text-gray-900 dark:text-white mb-6">
          About SvelteKit
        </h1>
        <p class="text-xl text-gray-600 dark:text-gray-300">
          A modern Svelte template designed to help developers build amazing web
          applications faster and more efficiently.
        </p>
      </div>
    </div>
  </section>

  <!-- Mission Section -->
  <section class="py-20 bg-white dark:bg-gray-900">
    <div class="container mx-auto px-4">
      <div class="max-w-4xl mx-auto">
        <h2 class="text-4xl font-bold text-gray-900 dark:text-white mb-8 text-center">
          Our Mission
        </h2>
        <p class="text-lg text-gray-600 dark:text-gray-300 text-center mb-12">
          We believe that developers should spend more time building features and
          less time configuring tools. SvelteKit Template provides a rock-solid foundation
          with modern best practices, allowing you to focus on what matters most:
          creating exceptional user experiences.
        </p>

        <!-- Tech Stack -->
        <div class="bg-gradient-to-br from-blue-50 to-purple-50 dark:from-gray-800 dark:to-gray-700 p-8 rounded-xl">
          <h3 class="text-2xl font-semibold text-gray-900 dark:text-white mb-6">
            Built with Modern Technologies
          </h3>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <div class="flex items-start space-x-3">
              <span class="text-2xl">🟠</span>
              <div>
                <h4 class="font-semibold text-gray-900 dark:text-white">
                  Svelte 5
                </h4>
                <p class="text-gray-600 dark:text-gray-300 text-sm">
                  Latest Svelte with runes and enhanced reactivity
                </p>
              </div>
            </div>
            <div class="flex items-start space-x-3">
              <span class="text-2xl">📘</span>
              <div>
                <h4 class="font-semibold text-gray-900 dark:text-white">
                  TypeScript
                </h4>
                <p class="text-gray-600 dark:text-gray-300 text-sm">
                  Type safety and enhanced developer experience
                </p>
              </div>
            </div>
            <div class="flex items-start space-x-3">
              <span class="text-2xl">🎨</span>
              <div>
                <h4 class="font-semibold text-gray-900 dark:text-white">
                  Tailwind CSS
                </h4>
                <p class="text-gray-600 dark:text-gray-300 text-sm">
                  Utility-first CSS framework for rapid UI development
                </p>
              </div>
            </div>
            <div class="flex items-start space-x-3">
              <span class="text-2xl">🛣️</span>
              <div>
                <h4 class="font-semibold text-gray-900 dark:text-white">
                  SvelteKit
                </h4>
                <p class="text-gray-600 dark:text-gray-300 text-sm">
                  Powerful framework for building web applications
                </p>
              </div>
            </div>
            <div class="flex items-start space-x-3">
              <span class="text-2xl">⚡</span>
              <div>
                <h4 class="font-semibold text-gray-900 dark:text-white">
                  Vite
                </h4>
                <p class="text-gray-600 dark:text-gray-300 text-sm">
                  Next generation frontend tooling
                </p>
              </div>
            </div>
            <div class="flex items-start space-x-3">
              <span class="text-2xl">🔧</span>
              <div>
                <h4 class="font-semibold text-gray-900 dark:text-white">
                  Modern Build Tools
                </h4>
                <p class="text-gray-600 dark:text-gray-300 text-sm">
                  Optimized build process and development workflow
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Values Section -->
  <section class="py-20 bg-gray-50 dark:bg-gray-800">
    <div class="container mx-auto px-4">
      <h2 class="text-4xl font-bold text-gray-900 dark:text-white mb-12 text-center">
        Our Values
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-5xl mx-auto">
        {#each values as value}
          <div class="bg-white dark:bg-gray-900 p-8 rounded-xl text-center">
            <div class="text-5xl mb-4">{value.icon}</div>
            <h3 class="text-2xl font-semibold text-gray-900 dark:text-white mb-3">
              {value.title}
            </h3>
            <p class="text-gray-600 dark:text-gray-300">
              {value.description}
            </p>
          </div>
        {/each}
      </div>
    </div>
  </section>

  <!-- Team Section -->
  <section class="py-20 bg-white dark:bg-gray-900">
    <div class="container mx-auto px-4">
      <h2 class="text-4xl font-bold text-gray-900 dark:text-white mb-12 text-center">
        Meet Our Team
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-5xl mx-auto">
        {#each team as member}
          <div class="text-center group">
            <div class="relative mb-4 overflow-hidden rounded-xl">
              <img
                src={member.image}
                alt={member.name}
                class="w-full h-64 object-cover group-hover:scale-110 transition-transform duration-300"
              />
              <div class="absolute inset-0 bg-gradient-to-t from-black/50 to-transparent opacity-0 group-hover:opacity-100 transition-opacity"></div>
            </div>
            <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-1">
              {member.name}
            </h3>
            <p class="text-blue-600 dark:text-blue-400">{member.role}</p>
          </div>
        {/each}
      </div>
    </div>
  </section>
</div>
