<template>
  <section class="py-20 relative">
    <div class="container mx-auto px-6 md:px-12">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-5xl font-bold mb-4">My <span class="tech-gradient">Projects</span></h2>
        <div class="w-20 h-1 bg-gradient-to-r from-[#00f6ff] to-[#915eff] mx-auto mb-6"></div>
        <p class="text-[#aaa6c3] max-w-2xl mx-auto">
          Explore my latest work. Each project represents a unique challenge and showcases different aspects of my technical skills.
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(project, index) in projects" :key="index" 
             class="tech-card overflow-hidden group">
          <div class="relative h-48 overflow-hidden">
            <img :src="project.image" :alt="project.title" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110" />
            <div class="absolute inset-0 bg-gradient-to-t from-[#050816] to-transparent opacity-70"></div>
          </div>
          
          <div class="p-6">
            <div class="flex justify-between items-center mb-3">
              <h3 class="text-xl font-bold">{{ project.title }}</h3>
              <span class="text-xs px-2 py-1 rounded-full bg-[#151030] text-[#00f6ff] border border-[#00f6ff]/30">
                {{ project.category }}
              </span>
            </div>
            
            <p class="text-[#aaa6c3] text-sm mb-4">{{ project.description }}</p>
            
            <div class="flex flex-wrap gap-2 mb-4">
              <span v-for="(tech, techIndex) in project.technologies" :key="techIndex"
                    class="text-xs px-2 py-1 rounded-full bg-[#151030] text-white">
                {{ tech }}
              </span>
            </div>
            
            <div class="flex space-x-3">
              <a href="#" class="text-[#00f6ff] hover:text-white transition-colors text-sm flex items-center">
                <span>Live Demo</span>
                <span class="ml-1">→</span>
              </a>
              <a href="#" class="text-[#915eff] hover:text-white transition-colors text-sm flex items-center">
                <span>Source Code</span>
                <span class="ml-1">→</span>
              </a>
            </div>
          </div>
        </div>
      </div>
      
      <div class="text-center mt-12">
        <button class="tech-button glow-effect">View All Projects</button>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const projects = [
  {
    title: 'AI Image Generator',
    category: 'Web App',
    description: 'A modern web application that uses AI to generate unique images based on text prompts.',
    image: 'https://images.unsplash.com/photo-1620712943543-bcc4688e7485?q=80&w=2065&auto=format&fit=crop',
    technologies: ['React', 'Node.js', 'OpenAI API', 'TailwindCSS']
  },
  {
    title: 'Crypto Dashboard',
    category: 'Finance',
    description: 'Real-time cryptocurrency tracking dashboard with advanced analytics and portfolio management.',
    image: 'https://images.unsplash.com/photo-1639762681057-408e52192e55?q=80&w=2232&auto=format&fit=crop',
    technologies: ['Vue.js', 'Express', 'Chart.js', 'WebSockets']
  },
  {
    title: 'Smart Home App',
    category: 'IoT',
    description: 'Mobile application for controlling smart home devices with voice commands and automation.',
    image: 'https://images.unsplash.com/photo-1558002038-1055e2dae1d7?q=80&w=2070&auto=format&fit=crop',
    technologies: ['React Native', 'Firebase', 'IoT', 'Redux']
  }
];
</script>