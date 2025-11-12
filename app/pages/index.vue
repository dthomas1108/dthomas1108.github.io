<template>
  <div class="container mx-auto px-4">
    <section class="min-h-[80vh] flex items-center justify-center">
      <div class="max-w-4xl mx-auto text-center justify-center">
<!--        <img-->
<!--            src="/img/Dylan.png"-->
<!--            alt="Dylan Thomas"-->
<!--            class="w-32 h-32 mx-auto mb-6 rounded-full shadow-lg z-50"-->
<!--        />-->

        <h1 class="text-6xl md:text-8xl font-bold">
          Dylan Thomas
        </h1>
        <p class="text-xl md:text-2xl text-gray-400 max-w-2xl mx-auto my-3">
          Full-stack developer building things which sometimes works!
        </p>

        <div class="flex gap-4 justify-center">
          <NuxtLink
              to="/experience"
              class="px-8 py-3 bg-green-500 hover:bg-green-600 text-black font-semibold rounded-lg transition-colors"
          >
            View Work
          </NuxtLink>
          <NuxtLink
              to="/contact"
              class="px-8 py-3 border border-gray-700 hover:border-white text-white rounded-lg transition-colors"
          >
            Get in Touch
          </NuxtLink>
        </div>
      </div>
    </section>

    <section class="py-20">
      <h2 class="text-4xl font-bold mb-12 text-center">Expertise</h2>
      <div class="grid md:grid-cols-3 gap-8 max-w-5xl mx-auto">
        <div
            v-for="(item, index) in expertise"
            :key="index"
            class="p-8 border border-gray-800 rounded-lg hover:border-green-500 transition-all group"
        >
          <h3 class="text-xl font-semibold mb-4 group-hover:text-green-500 transition-colors">
            {{ item.title }}
          </h3>
          <p class="text-gray-400">
            {{ item.description }}
          </p>
        </div>
      </div>
    </section>

    <section class="py-20">
      <h2 class="text-4xl font-bold mb-12 text-center">Featured Projects</h2>
      <div class="grid md:grid-cols-2 gap-8 max-w-6xl mx-auto">
        <div
            v-for="(project, index) in featuredProjects"
            :key="index"
            class="group cursor-pointer"
        >
          <div class="aspect-video bg-gray-900 rounded-lg mb-4 overflow-hidden border border-gray-800 group-hover:border-green-500 transition-all">
            <div class="w-full h-full flex items-center justify-center text-gray-600">
              Project Screenshot
            </div>
          </div>
          <h3 class="text-xl font-semibold mb-2 group-hover:text-green-500 transition-colors">
            {{ project.title }}
          </h3>
          <p class="text-gray-400 mb-4">
            {{ project.description }}
          </p>
          <div class="flex flex-wrap gap-2">
            <span
                v-for="tech in project.technologies"
                :key="tech"
                class="px-3 py-1 text-sm bg-gray-900 border border-gray-800 rounded-full"
            >
              {{ tech }}
            </span>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script setup>
const expertise = [
  {
    title: 'Full Stack Development',
    description: 'Building web applications with modern frameworks and technologies'
  },
  {
    title: 'AI Integration',
    description: 'Implementing AI powered features to improve user experience'
  },
  {
    title: 'Software Architecture',
    description: 'Designing maintainable, efficient systems with clean architecture and design patterns'
  }
];

const featuredProjects = [
  {
    title: 'Discord & Telegram Bots',
    description: 'Designed smart Discord and Telegram bots with Node.js that handle automation, data storage, and interactive community features.',
    technologies: ['Node.js', 'Discord.js', 'MongoDB', 'PostgreSQL']
  },
  {
    title: 'AI Support/Chatbot',
    description: 'Real-time chat application with AI-powered responses, intent detection and entity extraction using a multi-stage RAG pipeline.',
    technologies: ['JavaScript', 'OpenAI', 'Pinecone', 'Docker']
  },
  {
    title: 'Broke By Design Drivers Hub',
    description: 'Real-time data visualisation and driver/community management system for a virtual trucking community.',
    technologies: ['Nuxt', 'Vue', 'TailwindCSS', 'Supabase']
  }
];
</script>