<template>
  <div class="container mx-auto px-6 py-20">
    <div class="max-w-4xl mx-auto">
      <h1 class="text-5xl font-bold mb-12">Experience</h1>

      <section class="mb-16">
        <h2 class="text-3xl font-bold mb-8">Work & Internships</h2>
        <div class="space-y-8">
          <div
              v-for="(job, index) in workExperience"
              :key="index"
              class="border-border-gray-800 rounded-lg p-6 hover:border-green-500 transition-colors"
          >
            <div class="flex justify-between items-start mb-4">
              <div>
                <h3 class="text-2xl font-semibold mb-1">{{ job.title }}</h3>
                <p class="text-gray-400">{{ job.company }}</p>
              </div>
              <span class="text-gray-500">{{ job.period }}</span>
            </div>
            <ul class="space-y-2 text-gray-400">
              <li v-for="(achievement, i) in job.achievements" :key="i">
                • {{ achievement }}
              </li>
            </ul>

            <div class="flex flex-wrap gap-2 mt-4">
              <span
                  v-for="tech in job.technologies"
                  :key="tech"
                  class="px-3 py-1 text-sm bg-gray-900 border border-gray-800 rounded-full"
              >
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </section>

      <section>
        <h2 class="text-3xl font-bold mb-8">Featured Projects</h2>
        <div class="grid gap-6">
          <div
              v-for="(project, index) in projects"
              :key="index"
              class="border border-gray-800 rounded-lg overflow-hidden hover:border-green-500 transition-all group"
          >
            <div class="aspect-video bg-gray-900 flex items-center justify-center border-b border-gray-800">
              <span class="text-gray-600">Project Preview</span>
            </div>

            <div class="p-6">
              <h3 class="text-xl font-semibold mb-2 group-hover:text-green-500 transition-colors">
                {{ project.title }}
              </h3>
              <p class="text-gray-400 mb-4">{{ project.description }}</p>
              <div class="flex flex-wrap gap-2 mb-4">
                <span
                    v-for="tech in project.technologies"
                    :key="tech"
                    class="px-3 py-1 text-sm bg-gray-900 border border-gray-800 rounded-full"
                >
                  {{ tech }}
                </span>
              </div>

              <div class="flex gap-4">
                <a
                    v-if="project.liveUrl"
                    :href="project.liveUrl"
                    target="_blank"
                    class="text-green-500 hover:text-green-400 transition-colors"
                >
                  Live Demo →
                </a>
              </div>

            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>
<script setup>
const workExperience = [
  {
    title: 'Software Engineering Intern -> Part Time Full-Stack Software Engineer',
    company: 'Stram Entertainment',
    period: '2025 - Present',
    achievements: [
        'Developed and maintained features for production web applications',
        'Collaborated with cross-functional teams to deliver projects',
        'Played with the implementation of automated testing',
        'Created AI Integrations for internal tools improving team productivity',
        'Established multiple new projects within the company'
    ],
    technologies: ['Vue.js', 'Nuxt', 'TailwindCSS', 'PHP', 'JavaScript', 'PostgreSQL', 'Vercel']
  },
  {
    title: 'Web Developer',
    company: 'Freelance',
    period: '2020 - Present',
    achievements: [
      'Built responsive websites for multiple clients',
      'Managed full project lifecycle from requirements to deployment',
      'Implemented SEO best practices increasing organic traffic',
      'Maintained client relationships and provided ongoing support'
    ],
    technologies: ['Vue.js', 'Nuxt', 'Tailwind CSS', 'Vercel', 'MongoDB', 'Discord.js', 'Telegram API']
  }
];

const projects = [
  {
    title: 'Discord & Telegram Bots',
    description: 'Custom community management bots featuring moderation systems, automated roles, and AI-powered engagement tools. Discord bots included custom commands and AutoMod capabilities, while Telegram bots leveraged OpenAI for automated polling and scheduled messaging.',
    technologies: ['Node.js', 'Discord.js', 'Telegram Bot API', 'OpenAI API'],
    liveUrl: 'https://versatech.gitbook.io/versatix',
    githubUrl: null
  },
  {
    title: 'AI Powered Support/Chat Application',
    description: 'Real-time chat application with AI powered responses for sports handicapping e-commerce. Features intent detection, entity extraction, and a multi-stage RAG pipeline with vector database integration to provide personalised package recommendations based on handicapper performance data.',
    technologies: ['HTML/CSS/JS', 'OpenAI API', 'Pinecone', 'Docker', 'RAG Pipeline'],
    liveUrl: null,
    githubUrl: null
  },
  {
    title: 'Broke By Design Website & Drivers Hub',
    description: 'Virtual Trucking Company website with real-time data visualisation and driver/community management system.',
    technologies: ['Nuxt', 'Vue', 'TailwindCSS', 'Supabase'],
    liveUrl: 'https://www.brokebydesign.net/',
    githubUrl: null
  }
];
</script>