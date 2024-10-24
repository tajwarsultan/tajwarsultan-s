<script lang="ts">
  import { onMount } from 'svelte';
  import { slide } from 'svelte/transition';
  import { Motion } from 'svelte-motion';
  import { Menu, X } from 'lucide-svelte';  // This should now work correctly

  let isOpen = false;
  let scrolled = false;

  const navItems = [
    { name: 'About', href: '#about' },
    { name: 'Skills', href: '#skills' },
    { name: 'Projects', href: '#projects' },
    { name: 'Experience', href: '#experience' },
    { name: 'Contact', href: '#contact' },
  ];

  onMount(() => {
    const handleScroll = () => {
      scrolled = window.scrollY > 50;
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });
</script>

<nav
  class="fixed w-full z-50 transition-all duration-300"
  class:bg-black={scrolled}
  class:bg-opacity-80={scrolled}
  class:backdrop-blur-sm={scrolled}
>
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between h-16">
      <Motion
        let:motion
        initial={{ opacity: 0, x: -20 }}
        animate={{ opacity: 1, x: 0 }}
        transition={{ duration: 0.5 }}
      >
        <div class="flex-shrink-0" use:motion>
          <a href="/" class="text-xl font-bold">Tajwar Sultan</a>
        </div>
      </Motion>

      <!-- Desktop Navigation -->
      <div class="hidden md:block">
        <div class="ml-10 flex items-baseline space-x-4">
          {#each navItems as item, index}
            <Motion
              let:motion
              initial={{ opacity: 0, y: -20 }}
              animate={{ opacity: 1, y: 0 }}
              transition={{ duration: 0.5, delay: index * 0.1 }}
            >
              <div use:motion>
                <a
                  href={item.href}
                  class="hover:text-blue-400 px-3 py-2 rounded-md text-sm font-medium transition-colors"
                >
                  {item.name}
                </a>
              </div>
            </Motion>
          {/each}
        </div>
      </div>

      <!-- Mobile menu button -->
      <div class="md:hidden">
        <button
          on:click={() => (isOpen = !isOpen)}
          class="inline-flex items-center justify-center p-2 rounded-md hover:text-blue-400 focus:outline-none"
        >
          {#if isOpen}
            <X size={24} />
          {:else}
            <Menu size={24} />
          {/if}
        </button>
      </div>
    </div>
  </div>

  <!-- Mobile menu -->
  {#if isOpen}
    <div
      transition:slide={{ duration: 300 }}
      class="md:hidden bg-black/90 backdrop-blur-sm"
    >
      <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
        {#each navItems as item}
          <a
            href={item.href}
            class="hover:text-blue-400 block px-3 py-2 rounded-md text-base font-medium"
            on:click={() => (isOpen = false)}
          >
            {item.name}
          </a>
        {/each}
      </div>
    </div>
  {/if}
</nav>