<script lang="ts">
  interface Service {
    title: string;
    description: string;
    features: string[];
    color: 'blue' | 'purple' | 'pink' | 'green' | 'indigo' | 'yellow';
  }

  const services: Service[] = [
    {
      title: 'Web Development',
      description: 'Build modern, responsive websites and web applications with cutting-edge technologies.',
      features: [
        'Responsive Design',
        'Progressive Web Apps',
        'Single Page Applications',
        'API Integration'
      ],
      color: 'blue'
    },
    {
      title: 'Mobile Development',
      description: 'Create native and cross-platform mobile applications for iOS and Android.',
      features: [
        'Native iOS & Android',
        'Cross-platform Solutions',
        'App Store Optimization',
        'Push Notifications'
      ],
      color: 'purple'
    },
    {
      title: 'UI/UX Design',
      description: 'Design beautiful, intuitive user interfaces and experiences that users love.',
      features: [
        'User Research',
        'Wireframing',
        'Prototyping',
        'Usability Testing'
      ],
      color: 'pink'
    },
    {
      title: 'Cloud Solutions',
      description: 'Deploy and manage scalable applications on cloud platforms.',
      features: [
        'AWS & Azure',
        'Serverless Architecture',
        'Container Orchestration',
        'CI/CD Pipelines'
      ],
      color: 'green'
    },
    {
      title: 'E-Commerce',
      description: 'Launch and grow your online store with powerful e-commerce solutions.',
      features: [
        'Shopping Cart',
        'Payment Integration',
        'Inventory Management',
        'Analytics & Reporting'
      ],
      color: 'indigo'
    },
    {
      title: 'Consulting',
      description: 'Get expert advice on technology strategy and digital transformation.',
      features: [
        'Tech Stack Selection',
        'Architecture Review',
        'Performance Optimization',
        'Security Audit'
      ],
      color: 'yellow'
    }
  ];

  function getColorClasses(color: Service['color']) {
    const colorMap = {
      blue: {
        bg: 'bg-blue-600',
        text: 'text-blue-600',
        hover: 'hover:bg-blue-700'
      },
      purple: {
        bg: 'bg-purple-600',
        text: 'text-purple-600',
        hover: 'hover:bg-purple-700'
      },
      pink: {
        bg: 'bg-pink-600',
        text: 'text-pink-600',
        hover: 'hover:bg-pink-700'
      },
      green: {
        bg: 'bg-green-600',
        text: 'text-green-600',
        hover: 'hover:bg-green-700'
      },
      indigo: {
        bg: 'bg-indigo-600',
        text: 'text-indigo-600',
        hover: 'hover:bg-indigo-700'
      },
      yellow: {
        bg: 'bg-yellow-500',
        text: 'text-yellow-600',
        hover: 'hover:bg-yellow-600'
      }
    };
    return colorMap[color];
  }
</script>

<div>
  <!-- Hero Section -->
  <section class="bg-gradient-to-br from-blue-50 to-purple-50 dark:from-gray-900 dark:to-gray-800 py-20">
    <div class="container mx-auto px-4">
      <div class="max-w-3xl mx-auto text-center">
        <h1 class="text-5xl font-bold text-gray-900 dark:text-white mb-6">
          Our Services
        </h1>
        <p class="text-xl text-gray-600 dark:text-gray-300">
          Comprehensive solutions to bring your digital vision to life
        </p>
      </div>
    </div>
  </section>

  <!-- Services Grid -->
  <section class="py-20 bg-white dark:bg-gray-900">
    <div class="container mx-auto px-4">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        {#each services as service}
          <div
            class="bg-white dark:bg-gray-800 rounded-xl shadow-lg hover:shadow-2xl transition-shadow p-8 border border-gray-200 dark:border-gray-700"
          >
            <div
              class="w-16 h-16 rounded-lg flex items-center justify-center text-white mb-6 {getColorClasses(service.color).bg}"
            >
              <span class="text-3xl font-bold">{service.title.charAt(0)}</span>
            </div>
            <h3 class="text-2xl font-bold text-gray-900 dark:text-white mb-4">
              {service.title}
            </h3>
            <p class="text-gray-600 dark:text-gray-300 mb-6">
              {service.description}
            </p>
            <ul class="space-y-2 mb-6">
              {#each service.features as feature}
                <li
                  class="flex items-center text-gray-600 dark:text-gray-300"
                >
                  <svg
                    class="w-5 h-5 mr-2 {getColorClasses(service.color).text}"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M5 13l4 4L19 7"
                    />
                  </svg>
                  {feature}
                </li>
              {/each}
            </ul>
            <a
              href="/contact"
              class="block text-center px-6 py-3 text-white rounded-lg font-semibold transition-colors {getColorClasses(service.color).bg} {getColorClasses(service.color).hover}"
            >
              Learn More
            </a>
          </div>
        {/each}
      </div>
    </div>
  </section>

  <!-- CTA Section -->
  <section class="py-20 bg-gradient-to-r from-blue-600 to-purple-600">
    <div class="container mx-auto px-4 text-center">
      <h2 class="text-4xl font-bold text-white mb-6">
        Ready to Start Your Project?
      </h2>
      <p class="text-xl text-blue-100 mb-8">
        Let's discuss how we can help you achieve your goals
      </p>
      <a
        href="/contact"
        class="inline-block px-8 py-4 bg-white text-blue-600 rounded-lg font-semibold hover:bg-gray-100 transition-colors"
      >
        Contact Us Today
      </a>
    </div>
  </section>
</div>
