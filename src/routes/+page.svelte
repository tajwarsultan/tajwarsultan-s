<script lang="ts">
  import { Motion } from 'svelte-motion';
  import { ArrowRight } from 'lucide-svelte';
</script>

<section class="min-h-screen flex items-center justify-center px-4">
  <div class="max-w-4xl mx-auto text-center">
    <Motion
      let:motion
      initial={{ opacity: 0, y: 20 }}
      animate={{ opacity: 1, y: 0 }}
      transition={{ duration: 0.8 }}
    >
      <h1
        use:motion
        class="text-4xl sm:text-6xl font-bold pb-6 bg-clip-text text-transparent bg-gradient-to-r from-blue-400 to-purple-600"
      >
        Full Stack Developer & Project Manager
      </h1>
    </Motion>

    <Motion
      let:motion
      initial={{ opacity: 0 }}
      animate={{ opacity: 1 }}
      transition={{ delay: 0.2, duration: 0.8 }}
    >
      <p use:motion class="text-xl text-gray-300 mb-8">
        Building modern web experiences with cutting-edge technologies
      </p>
    </Motion>

    <Motion
      let:motion
      initial={{ opacity: 0, y: 20 }}
      animate={{ opacity: 1, y: 0 }}
      transition={{ delay: 0.4, duration: 0.8 }}
    >
      <div use:motion class="flex flex-wrap justify-center gap-4">
        <button
          class="group bg-blue-600 hover:bg-blue-700 text-white px-6 py-3 rounded-lg font-medium transition-colors flex items-center"
          on:click={() => document.getElementById('contact')?.scrollIntoView({ behavior: 'smooth' })}
        >
          Get in Touch
          <ArrowRight class="ml-2 transition-transform group-hover:translate-x-1" />
        </button>

        <div class="flex gap-4">
          <a
            href="https://www.upwork.com/freelancers/~01e869dbdc49f3cc26"
            target="_blank"
            rel="noopener noreferrer"
            class="p-3 rounded-lg border border-gray-700 hover:border-blue-400 hover:text-blue-400 transition-colors"
          >
            <img src="https://www.vectorlogo.zone/logos/upwork/upwork-icon.svg" alt="" width="25px">
          </a>

          <a
            href="https://www.fiverr.com/tajwarsultan123?public_mode=true"
            target="_blank"
            rel="noopener noreferrer"
            class="p-3 rounded-lg border border-gray-700 hover:border-blue-400 hover:text-blue-400 transition-colors"
          >
            <img src="https://www.vectorlogo.zone/logos/fiverr/fiverr-icon.svg" alt="" width="25px">
          </a>

          <a
            href="https://github.com/tajwarsultan"
            target="_blank"
            rel="noopener noreferrer"
            class="p-3 rounded-lg border border-gray-700 hover:border-blue-400 hover:text-blue-400 transition-colors"
          >
            <img src="https://www.vectorlogo.zone/logos/github/github-tile.svg" alt="" width="25px">
          </a>

          <a
            href="https://www.linkedin.com/in/tajwar-sultan/"
            target="_blank"
            rel="noopener noreferrer"
            class="p-3 rounded-lg border border-gray-700 hover:border-blue-400 hover:text-blue-400 transition-colors"
          >
            <img src="https://www.vectorlogo.zone/logos/linkedin/linkedin-tile.svg" alt="" width="25px">
          </a>
          <a
            href="mailto:tajwar.sultan00@gmail.com"
            class="p-3 rounded-lg border border-gray-700 hover:border-blue-400 hover:text-blue-400 transition-colors"
          >
            <img src="https://www.vectorlogo.zone/logos/gmail/gmail-icon.svg" alt="" width="25px">
          </a>
        </div>
      </div>
    </Motion>
  </div>
</section>