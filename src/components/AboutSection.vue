<template>
  <section class="py-20 relative">
    <div class="container mx-auto px-6 md:px-12">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-5xl font-bold mb-4">About <span class="tech-gradient">Me</span></h2>
        <div class="w-20 h-1 bg-gradient-to-r from-[#00f6ff] to-[#915eff] mx-auto"></div>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
        <div class="tech-card p-6 md:p-8 glow-effect">
          <h3 class="text-2xl font-bold mb-4 tech-gradient">My Background</h3>
          <p class="text-[#aaa6c3] mb-4">
            I'm a passionate full-stack developer with over 5 years of experience building modern web applications. 
            My journey in tech started when I built my first website at the age of 15, and I've been hooked ever since.
          </p>
          <p class="text-[#aaa6c3]">
            I specialize in creating intuitive, responsive, and performant applications using the latest technologies. 
            My approach combines technical expertise with creative problem-solving to deliver exceptional user experiences.
          </p>
        </div>
        
        <div>
          <div class="grid grid-cols-2 gap-4">
            <div v-for="(skill, index) in skills" :key="index" 
                 class="tech-card p-4 flex flex-col items-center justify-center">
              <div class="w-16 h-16 rounded-full bg-[#151030] flex items-center justify-center mb-3">
                <div class="text-[#00f6ff] text-2xl">{{ skill.icon }}</div>
              </div>
              <h4 class="text-lg font-medium mb-1">{{ skill.name }}</h4>
              <div class="w-full bg-[#151030] h-2 rounded-full">
                <div class="h-full rounded-full bg-gradient-to-r from-[#00f6ff] to-[#915eff]"
                     :style="{ width: `${skill.level}%` }"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="mt-20">
        <h3 class="text-2xl md:text-3xl font-bold mb-8 text-center">My <span class="tech-gradient">Journey</span></h3>
        
        <div class="relative">
          <!-- Timeline Line -->
          <div class="absolute left-1/2 transform -translate-x-1/2 h-full w-1 bg-gradient-to-b from-[#00f6ff] to-[#915eff]"></div>
          
          <!-- Timeline Items -->
          <div class="space-y-12">
            <div v-for="(item, index) in timeline" :key="index" 
                 class="relative flex items-center"
                 :class="{ 'flex-row-reverse': index % 2 !== 0 }">
              <!-- Timeline Dot -->
              <div class="absolute left-1/2 transform -translate-x-1/2 w-4 h-4 rounded-full bg-[#00f6ff]"></div>
              
              <!-- Content -->
              <div class="w-5/12"></div>
              <div class="w-5/12 tech-card p-6">
                <div class="text-sm text-[#00f6ff] mb-1">{{ item.year }}</div>
                <h4 class="text-xl font-bold mb-2">{{ item.title }}</h4>
                <p class="text-[#aaa6c3]">{{ item.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const skills = [
  { name: 'Frontend', level: 90, icon: '⚛️' },
  { name: 'Backend', level: 85, icon: '🖥️' },
  { name: 'UI/UX', level: 80, icon: '🎨' },
  { name: 'DevOps', level: 75, icon: '🚀' }
];

const timeline = [
  {
    year: '2018',
    title: 'Started Coding Journey',
    description: 'Began learning web development and built my first portfolio website using HTML, CSS, and JavaScript.'
  },
  {
    year: '2019',
    title: 'First Tech Job',
    description: 'Joined a startup as a junior developer, working on frontend applications using React.'
  },
  {
    year: '2020',
    title: 'Expanded to Full-Stack',
    description: 'Learned Node.js and Express to become a full-stack developer, building complete web applications.'
  },
  {
    year: '2022',
    title: 'Senior Developer',
    description: 'Promoted to senior developer, leading a team and architecting large-scale applications.'
  }
];
</script>