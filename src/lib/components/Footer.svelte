<script lang="ts">
  import { Motion } from 'svelte-motion';
  import { Github, Linkedin, Mail, Twitter } from 'lucide-svelte';

  const currentYear = new Date().getFullYear();

  const socialLinks = [
    {
      name: 'GitHub',
      href: 'https://github.com/yourusername',
      icon: Github,
    },
    {
      name: 'LinkedIn',
      href: 'https://linkedin.com/in/yourusername',
      icon: Linkedin,
    },
    {
      name: 'Email',
      href: 'mailto:your-email@example.com',
      icon: Mail,
    },
    {
      name: 'Twitter',
      href: 'https://twitter.com/yourusername',
      icon: Twitter,
    },
  ];

  const footerNavigation = {
    main: [
      { name: 'About', href: '#about' },
      { name: 'Skills', href: '#skills' },
      { name: 'Projects', href: '#projects' },
      { name: 'Experience', href: '#experience' },
      { name: 'Contact', href: '#contact' },
    ],
  };
</script>

<footer class="bg-black/50 backdrop-blur-sm mt-20">
  <div class="max-w-7xl mx-auto py-12 px-4 sm:px-6 lg:px-8">
    <Motion
      let:motion
      initial={{ opacity: 0, y: 20 }}
      whileInView={{ opacity: 1, y: 0 }}
      transition={{ duration: 0.5 }}
    >
      <nav use:motion class="-mx-5 -my-2 flex flex-wrap justify-center" aria-label="Footer">
        {#each footerNavigation.main as item}
          <div class="px-5 py-2">
            <a
              href={item.href}
              class="text-gray-400 hover:text-blue-400 transition-colors"
            >
              {item.name}
            </a>
          </div>
        {/each}
      </nav>
    </Motion>

    <Motion
      let:motion
      initial={{ opacity: 0, y: 20 }}
      whileInView={{ opacity: 1, y: 0 }}
      transition={{ duration: 0.5, delay: 0.2 }}
    >
      <div use:motion class="mt-8 flex justify-center space-x-6">
        {#each socialLinks as item}
          <a
            href={item.href}
            class="text-gray-400 hover:text-blue-400 transition-colors"
            target="_blank"
            rel="noopener noreferrer"
          >
            <span class="sr-only">{item.name}</span>
            <svelte:component this={item.icon} size={20} />
          </a>
        {/each}
      </div>
    </Motion>

    <Motion
      let:motion
      initial={{ opacity: 0, y: 20 }}
      whileInView={{ opacity: 1, y: 0 }}
      transition={{ duration: 0.5, delay: 0.4 }}
    >
      <div use:motion class="mt-8 text-center">
        <div class="flex flex-col sm:flex-row items-center justify-center space-y-2 sm:space-y-0 sm:space-x-4">
          <p class="text-gray-400 text-sm">
            © {currentYear} Tajwar Sultan. All rights reserved.
          </p>
          <div class="flex space-x-4">
            <a
              href="/privacy"
              class="text-gray-400 hover:text-blue-400 text-sm transition-colors"
            >
              Privacy Policy
            </a>
            <a
              href="/terms"
              class="text-gray-400 hover:text-blue-400 text-sm transition-colors"
            >
              Terms of Service
            </a>
          </div>
        </div>
      </div>
    </Motion>

    <Motion
      let:motion
      initial={{ opacity: 0, y: 20 }}
      whileInView={{ opacity: 1, y: 0 }}
      transition={{ duration: 0.5, delay: 0.6 }}
    >
      <div use:motion class="mt-8 text-center">
        <p class="text-gray-400 text-sm">
          Built with
          <span class="text-red-500">❤</span>
          using SvelteKit, TypeScript, and Tailwind CSS
        </p>
      </div>
    </Motion>
  </div>
</footer>