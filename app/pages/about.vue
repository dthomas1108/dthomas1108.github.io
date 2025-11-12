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
          <h3 class="text-xl font-semibold">BEng (Hons) Software Design for AI & Cloud Computing</h3>
          <span class="text-gray-500">Expected 2026</span>
        </div>
        <p class="text-gray-400 mb-4">Bachelor of Engineering</p>
        <div class="space-y-2 text-gray-400">
          <ul>
            <li>• Dean's Honours List recipient years 23/24 & 24/25</li>
            <li>• Focus on Full-Stack Development and AI/ML</li>
            <li>• On track to receive a 2.1 Hons degree</li>
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

    <section>
      <h2 class="text-3xl font-bold mb-6">Interests</h2>
      <div class="grid md:grid-cols-3 gap-4">
        <div
            v-for="(interest, index) in interests"
            :key="index"
            class="p-4 border border-gray-800 rounded-lg text-center hover:border-gray-500 transition-colors"
        >
          <p class="text-gray-400">{{ interest }}</p>
        </div>
      </div>
    </section>

    <div class="mt-12 text-center">
      <a href="/Dylan-Thomas-CV.pdf" download class="inline-block px-8 py-3 bg-green-500 hover:bg-green-600 text-black font-semibold rounded-lg transition-colors">
        Download CV
      </a>
    </div>
  </div>
</div>
</template>
<script setup>
const skills = [
  {
    name: 'Frontend',
    items: [
      'Vue.js',
      'Nuxt',
      'JavaScript',
      'HTML',
      'CSS',
      'TailwindCSS',
      'Bootstrap',
      'Chart.js'
    ]
  },
  {
    name: 'Backend',
    items: [
      'Node.js',
      'Express',
      'Python',
      'Java',
      'Spring Boot',
      'REST APIs',
      'MongoDB',
      'PostgreSQL',
      'MySQL',
      'PHP',
    ]
  },
  {
    name: 'AI & Automation',
    items: [
      'OpenAI API',
      'Playwright',
      'Puppeteer',
      'Pinecone'
    ]
  },
  {
    name: 'Tools & Platforms',
    items: [
      'Git',
      'Docker',
      'Vercel',
      'Coolify',
      'Postman'
    ]
  },
  {
    name: 'Other / CMS',
    items: [
      'Notion',
      'Asana',
      'WordPress',
    ]
  }
];

const interests = [
    'Artificial Intelligence',
    'Machine Learning',
    'Full-Stack Development',
    'Cloud Architecture',
    'Data Visualization',
    'Sports Analytics',
    'Gaming & Simulation',
    'API Development',
    'Database Design'
];
</script>