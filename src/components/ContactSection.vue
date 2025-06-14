<template>
  <section class="py-20 relative">
    <div class="container mx-auto px-6 md:px-12">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-5xl font-bold mb-4">Get In <span class="tech-gradient">Touch</span></h2>
        <div class="w-20 h-1 bg-gradient-to-r from-[#00f6ff] to-[#915eff] mx-auto mb-6"></div>
        <p class="text-[#aaa6c3] max-w-2xl mx-auto">
          Have a project in mind or want to collaborate? Feel free to reach out!
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
        <div class="tech-card p-8 glow-effect">
          <h3 class="text-2xl font-bold mb-6 tech-gradient">Contact Information</h3>
          
          <div class="space-y-6">
            <div class="flex items-start">
              <div class="w-12 h-12 rounded-full bg-[#151030] flex items-center justify-center mr-4">
                <div class="text-[#00f6ff]">📧</div>
              </div>
              <div>
                <h4 class="text-lg font-medium mb-1">Email</h4>
                <p class="text-[#aaa6c3]">contact@alexchen.tech</p>
              </div>
            </div>
            
            <div class="flex items-start">
              <div class="w-12 h-12 rounded-full bg-[#151030] flex items-center justify-center mr-4">
                <div class="text-[#00f6ff]">📱</div>
              </div>
              <div>
                <h4 class="text-lg font-medium mb-1">Phone</h4>
                <p class="text-[#aaa6c3]">+1 (555) 123-4567</p>
              </div>
            </div>
            
            <div class="flex items-start">
              <div class="w-12 h-12 rounded-full bg-[#151030] flex items-center justify-center mr-4">
                <div class="text-[#00f6ff]">📍</div>
              </div>
              <div>
                <h4 class="text-lg font-medium mb-1">Location</h4>
                <p class="text-[#aaa6c3]">San Francisco, CA</p>
              </div>
            </div>
          </div>
          
          <div class="mt-8">
            <h4 class="text-lg font-medium mb-4">Connect with me</h4>
            <div class="flex space-x-4">
              <a href="#" class="w-10 h-10 rounded-full bg-[#151030] flex items-center justify-center text-[#00f6ff] hover:bg-[#00f6ff] hover:text-[#151030] transition-colors">
                <span>🐦</span>
              </a>
              <a href="#" class="w-10 h-10 rounded-full bg-[#151030] flex items-center justify-center text-[#00f6ff] hover:bg-[#00f6ff] hover:text-[#151030] transition-colors">
                <span>💼</span>
              </a>
              <a href="#" class="w-10 h-10 rounded-full bg-[#151030] flex items-center justify-center text-[#00f6ff] hover:bg-[#00f6ff] hover:text-[#151030] transition-colors">
                <span>🐱</span>
              </a>
              <a href="#" class="w-10 h-10 rounded-full bg-[#151030] flex items-center justify-center text-[#00f6ff] hover:bg-[#00f6ff] hover:text-[#151030] transition-colors">
                <span>📸</span>
              </a>
            </div>
          </div>
        </div>
        
        <div class="tech-card p-8">
          <h3 class="text-2xl font-bold mb-6">Send Me a Message</h3>
          
          <form @submit.prevent="handleSubmit" class="space-y-6">
            <div>
              <label for="name" class="block text-sm font-medium mb-2">Your Name</label>
              <input 
                type="text" 
                id="name" 
                v-model="form.name"
                class="w-full bg-[#151030] border border-[#aaa6c3]/30 rounded-md px-4 py-2 text-white focus:outline-none focus:border-[#00f6ff]"
                placeholder="John Doe"
              />
            </div>
            
            <div>
              <label for="email" class="block text-sm font-medium mb-2">Your Email</label>
              <input 
                type="email" 
                id="email" 
                v-model="form.email"
                class="w-full bg-[#151030] border border-[#aaa6c3]/30 rounded-md px-4 py-2 text-white focus:outline-none focus:border-[#00f6ff]"
                placeholder="john@example.com"
              />
            </div>
            
            <div>
              <label for="message" class="block text-sm font-medium mb-2">Your Message</label>
              <textarea 
                id="message" 
                v-model="form.message"
                rows="5"
                class="w-full bg-[#151030] border border-[#aaa6c3]/30 rounded-md px-4 py-2 text-white focus:outline-none focus:border-[#00f6ff]"
                placeholder="Hello, I'd like to talk about..."
              ></textarea>
            </div>
            
            <button type="submit" class="tech-button w-full">Send Message</button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { reactive } from 'vue';

const form = reactive({
  name: '',
  email: '',
  message: ''
});

const handleSubmit = () => {
  console.log('Form submitted:', form);
  // Here you would typically send the form data to a server
  alert('Message sent successfully!');
  
  // Reset form
  form.name = '';
  form.email = '';
  form.message = '';
};
</script>