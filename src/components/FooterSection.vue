<template>
  <footer class="py-8 border-t border-[#151030]">
    <div class="container mx-auto px-6 md:px-12">
      <div class="flex flex-col md:flex-row justify-between items-center">
        <div class="mb-6 md:mb-0">
          <div class="text-2xl font-bold tech-gradient mb-2">DEV<span class="text-white">.TECH</span></div>
          <p class="text-[#aaa6c3] text-sm">Building the future, one line of code at a time.</p>
        </div>
        
        <div class="flex space-x-6">
          <a href="#" class="text-[#aaa6c3] hover:text-[#00f6ff] transition-colors">Home</a>
          <a href="#" class="text-[#aaa6c3] hover:text-[#00f6ff] transition-colors">About</a>
          <a href="#" class="text-[#aaa6c3] hover:text-[#00f6ff] transition-colors">Projects</a>
          <a href="#" class="text-[#aaa6c3] hover:text-[#00f6ff] transition-colors">Contact</a>
        </div>
      </div>
      
      <div class="mt-8 pt-8 border-t border-[#151030] flex flex-col md:flex-row justify-between items-center">
        <div class="text-[#aaa6c3] text-sm mb-4 md:mb-0">
          © {{ new Date().getFullYear() }} Alex Chen. All rights reserved.
        </div>
        
        <div class="flex space-x-4">
          <a href="#" class="text-[#aaa6c3] hover:text-[#00f6ff] transition-colors text-sm">Privacy Policy</a>
          <a href="#" class="text-[#aaa6c3] hover:text-[#00f6ff] transition-colors text-sm">Terms of Service</a>
        </div>
      </div>
    </div>
  </footer>
</template>