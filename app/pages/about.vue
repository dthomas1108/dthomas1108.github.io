<template>
<div class="container mx-auto px-6 py-20">
  <div class="max-w-4xl mx-auto">
    <h1 class="text-5xl font-bold mb-8">About Me</h1>

    <div class="space-y-6 text-gray-400 text-lg mb-12">
      <p>
        I'm a 4th year Software Engineering student with a passion for creating
        clean, easily maintainable solutions for complex problems. My journey in software development
        began during COVID-19 when I had lots of free time and a curiosity about how web apps and other similar things work.
        That curiosity then evolved into a commitment to building elegant yet impactful applications.
      </p>
      <p>
        Throughout my studies and industry experience, I've bettered my knowledge
        in full-stack development, with a particular focus on modern web technologies
        and AI integrations. I enjoy working on projects that challenge me to learn
        new things. The thrill after solving a complex problem is addictive!
      </p>
    </div>

    <section class="mb-16">
      <h2 class="text-3xl font-bold mb-6">Education</h2>
      <div class="border border-gray-800 rounded-lg p-6 hover:border-green-500 transition-colors">
        <div class="flex justify-between items-start mb-2">
          <h3 class="text-xl font-semibold">Software Engineering</h3>
          <span class="text-gray-500">Expected 2026</span>
        </div>
        <p class="text-gray-400 mb-4">Bachelor of Engineering</p>
        <div class="space-y-2 text-gray-400">
          <ul>
            <li>• Dean's Honours List recipient years 23/24 & 24/25</li>
            <li>• Focus on Full-Stack Development and AI/ML</li>
          </ul>
        </div>
      </div>
    </section>

    <section class="mb-16">
      <h2 class="text-3xl font-bold mb-6">Skills &amp; Technologies</h2>
      <div class="grid md:grid-cols-2 gap-6">
        <div
            v-for="(category, index) in skills"
            :key="index"
            class="border border-gray-800 rounded-lg p-6"
        >
          <h3 class="text-xl font-semibold mb-4 text-green-500">
            {{ category.name }}
          </h3>
          <div class="flex flex-wrap gap-2">
            <span
                v-for="skill in category.items"
                :key="skill"
                class="px-3 py-1 text-sm bg-gray-900 border border-gray-800 rounded-full text-gray-400"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </section>

  </div>
</div>
</template>
<script setup>
const skills = [
  {
    name: 'Frontend',
    items: ['Vue.js', 'Nuxt', 'React', 'Tailwind CSS', 'JavaScript', 'TypeScript']
  },
  {
    name: 'Backend',
    items: ['Node.js', 'Express', 'Python', 'PostgreSQL', 'MongoDB', 'REST APIs']
  },
  {
    name: 'Tools & Platforms',
    items: ['Git', 'Docker', 'AWS', 'Vercel', 'GitHub Actions', 'Linux']
  },
  {
    name: 'AI & ML',
    items: ['TensorFlow', 'OpenAI API', 'Natural Language Processing', 'Data Analysis']
  }
];
</script>