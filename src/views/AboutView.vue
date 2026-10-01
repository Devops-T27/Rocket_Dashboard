<template>
    <div>
        <SideBar>
            <NavBar /><br><br><br>
            <div class="min-h-screen flex justify-center bg-gray-100 py-8">
              <div class="w-full max-w-4xl">
                <!-- Intro Section -->
                <div class="mb-8 p-8 bg-white shadow-sm flex flex-col sm:flex-row items-center gap-6">
                  <img :src="rocketImage" alt="Rocket" class="w-32 h-32 object-contain">
                  <div>
                    <h2 class="text-2xl font-semibold mb-2">About Rocket <small>TM</small></h2>
                    <p class="text-gray-700">
                      Rocket is a dashboard for monitoring your routes and APIs in one place.
                      It gives you a quick overview of activity through charts and summaries,
                      so you can spot trends and issues at a glance.
                    </p>
                  </div>
                </div>

                <!-- Features Section -->
                <div class="mb-8 p-8 bg-white shadow-sm">
                  <h2 class="text-xl font-semibold mb-4">Features</h2>
                  <div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
                    <div v-for="feature in features" :key="feature.title" class="p-4 border border-gray-200 rounded-lg">
                      <h3 class="font-medium text-gray-900 mb-1">{{ feature.title }}</h3>
                      <p class="text-sm text-gray-600">{{ feature.description }}</p>
                    </div>
                  </div>
                </div>

                <!-- Tech Stack Section -->
                <div class="mb-8 p-8 bg-white shadow-sm">
                  <h2 class="text-xl font-semibold mb-4">Built With</h2>
                  <div class="flex flex-wrap gap-2">
                    <span v-for="tech in techStack" :key="tech" class="bg-blue-100 text-blue-800 text-sm font-medium px-3 py-1 rounded-full">{{ tech }}</span>
                  </div>
                </div>
              </div>
            </div>
        </SideBar>
    </div>
</template>

<script setup>
import NavBar from './components/NavbarView.vue';
import SideBar from './components/SidebarView.vue';
import rocketImage from '@/assets/rocket.png';

const features = [
  { title: 'Dashboard', description: 'Charts and summaries of your activity at a glance.' },
  { title: 'Routes & APIs', description: 'Keep track of the routes and APIs you manage.' },
  { title: 'Profile', description: 'Manage your account details, password and avatar.' },
];

const techStack = ['Vue 3', 'Vue Router', 'Tailwind CSS', 'Flowbite', 'Chart.js'];
</script>
