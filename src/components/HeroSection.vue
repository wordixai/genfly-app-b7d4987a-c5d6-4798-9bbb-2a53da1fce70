<template>
  <section class="relative h-screen flex items-center">
    <div class="container mx-auto px-6 md:px-12 relative z-10">
      <div class="flex flex-col md:flex-row items-center">
        <div class="md:w-1/2 mb-12 md:mb-0">
          <div class="glitch-wrapper">
            <h1 class="text-4xl md:text-6xl font-bold mb-4 glitch" data-text="Hello, I'm">
              Hello, I'm
            </h1>
          </div>
          <h2 class="text-5xl md:text-7xl font-bold mb-6 tech-gradient">Alex Chen</h2>
          <div class="typewriter mb-8">
            <p class="text-xl md:text-2xl text-[#aaa6c3]">
              <span ref="typewriterText"></span>
              <span class="cursor">|</span>
            </p>
          </div>
          <div class="flex space-x-4">
            <button class="tech-button glow-effect">View Projects</button>
            <button class="border border-[#00f6ff] bg-transparent text-white font-medium py-2 px-6 rounded hover:bg-[#00f6ff]/10 transition-all">
              Contact Me
            </button>
          </div>
        </div>
        <div class="md:w-1/2 flex justify-center">
          <div class="relative w-64 h-64 md:w-80 md:h-80">
            <div class="absolute inset-0 rounded-full bg-gradient-to-r from-[#00f6ff] to-[#915eff] opacity-20 blur-xl animate-pulse"></div>
            <div class="absolute inset-4 rounded-full bg-[#151030] flex items-center justify-center">
              <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?q=80&w=1974&auto=format&fit=crop&ixlib=rb-4.0.3" 
                   alt="Profile" 
                   class="rounded-full w-full h-full object-cover border-2 border-[#00f6ff]/50" />
            </div>
          </div>
        </div>
      </div>
      
      <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 flex flex-col items-center">
        <div class="text-sm text-[#aaa6c3] mb-2">Scroll Down</div>
        <div class="w-6 h-10 border-2 border-[#aaa6c3] rounded-full flex justify-center">
          <div class="w-1.5 h-1.5 bg-[#00f6ff] rounded-full mt-2 animate-bounce"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';

const typewriterText = ref<HTMLElement | null>(null);
const phrases = [
  "Full-Stack Developer",
  "UI/UX Designer",
  "Tech Enthusiast",
  "Problem Solver"
];

let currentPhraseIndex = 0;
let currentCharIndex = 0;
let isDeleting = false;
let typingSpeed = 100;
let pauseEnd = 1500;
let timer: number;

const typeWriter = () => {
  const currentPhrase = phrases[currentPhraseIndex];
  
  if (!typewriterText.value) return;
  
  if (isDeleting) {
    // Deleting text
    typewriterText.value.textContent = currentPhrase.substring(0, currentCharIndex - 1);
    currentCharIndex--;
    typingSpeed = 50;
  } else {
    // Typing text
    typewriterText.value.textContent = currentPhrase.substring(0, currentCharIndex + 1);
    currentCharIndex++;
    typingSpeed = 100;
  }
  
  // If word is complete, start deleting after pause
  if (!isDeleting && currentCharIndex === currentPhrase.length) {
    isDeleting = true;
    typingSpeed = pauseEnd;
  }
  
  // If deletion is complete, move to next word
  if (isDeleting && currentCharIndex === 0) {
    isDeleting = false;
    currentPhraseIndex = (currentPhraseIndex + 1) % phrases.length;
  }
  
  timer = setTimeout(typeWriter, typingSpeed);
};

onMounted(() => {
  typeWriter();
});

onUnmounted(() => {
  clearTimeout(timer);
});
</script>

<style scoped>
.glitch-wrapper {
  position: relative;
  display: inline-block;
}

.glitch {
  position: relative;
  color: white;
}

.glitch::before,
.glitch::after {
  content: attr(data-text);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.glitch::before {
  left: 2px;
  text-shadow: -2px 0 #00f6ff;
  clip: rect(24px, 550px, 90px, 0);
  animation: glitch-anim-1 2s infinite linear alternate-reverse;
}

.glitch::after {
  left: -2px;
  text-shadow: -2px 0 #915eff;
  clip: rect(85px, 550px, 140px, 0);
  animation: glitch-anim-2 2s infinite linear alternate-reverse;
}

@keyframes glitch-anim-1 {
  0% {
    clip: rect(24px, 550px, 90px, 0);
  }
  20% {
    clip: rect(125px, 550px, 140px, 0);
  }
  40% {
    clip: rect(24px, 550px, 90px, 0);
  }
  60% {
    clip: rect(125px, 550px, 140px, 0);
  }
  80% {
    clip: rect(24px, 550px, 90px, 0);
  }
  100% {
    clip: rect(125px, 550px, 140px, 0);
  }
}

@keyframes glitch-anim-2 {
  0% {
    clip: rect(85px, 550px, 140px, 0);
  }
  20% {
    clip: rect(24px, 550px, 90px, 0);
  }
  40% {
    clip: rect(85px, 550px, 140px, 0);
  }
  60% {
    clip: rect(24px, 550px, 90px, 0);
  }
  80% {
    clip: rect(85px, 550px, 140px, 0);
  }
  100% {
    clip: rect(24px, 550px, 90px, 0);
  }
}

.cursor {
  display: inline-block;
  width: 2px;
  animation: blink 1s infinite;
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}
</style>