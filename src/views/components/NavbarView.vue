<template>
  <nav class="bg-white shadow fixed top-0 w-[84%] z-20">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-16">
        <!-- Left part: Dashboard Name -->
        <div class="flex items-center">
          <h1 class="text-xl font-semibold text-gray-600 font-bold">Rockets</h1>
        </div>

        <!-- Right part: Avatar with dropdown, notifications, and messages -->
        <div class="flex items-center space-x-4">
          <!-- Avatar with dropdown -->
          

          <!-- Notification and Messages Icons -->
          <button class="text-gray-500 hover:text-gray-700 focus:outline-none">
            <span class="sr-only">View notifications</span>
            <!-- Notification Bell Icon -->
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
              <path stroke-linecap="round" stroke-linejoin="round" d="M14.857 17.082a23.848 23.848 0 0 0 5.454-1.31A8.967 8.967 0 0 1 18 9.75V9A6 6 0 0 0 6 9v.75a8.967 8.967 0 0 1-2.312 6.022c1.733.64 3.56 1.085 5.455 1.31m5.714 0a24.255 24.255 0 0 1-5.714 0m5.714 0a3 3 0 1 1-5.714 0M3.124 7.5A8.969 8.969 0 0 1 5.292 3m13.416 0a8.969 8.969 0 0 1 2.168 4.5" />
            </svg>

          </button>
          <button class="text-gray-500 hover:text-gray-700 focus:outline-none">
            <span class="sr-only">View messages</span>
            <!-- Messages Icon -->
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
              <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 0 1-2.25 2.25h-15a2.25 2.25 0 0 1-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25m19.5 0v.243a2.25 2.25 0 0 1-1.07 1.916l-7.5 4.615a2.25 2.25 0 0 1-2.36 0L3.32 8.91a2.25 2.25 0 0 1-1.07-1.916V6.75" />
            </svg>

          </button>
          <div class="relative">
            <button id="dropdownDefaultButton" data-dropdown-toggle="dropdown" class="focus:outline-none">
              <img class="h-8 w-8 rounded-full" src="../../assets/logo.png" alt="Avatar">
            </button>
            <!-- Dropdown menu, show/hide based on dropdown state. -->
              <div id="dropdown" class="z-10 hidden bg-white divide-y divide-gray-100 rounded-lg shadow w-44 dark:bg-gray-700">
                  <ul class="py-2 text-sm text-gray-700 dark:text-gray-200" aria-labelledby="dropdownDefaultButton">
                    <li>
                      <router-link to="/profile">
                        <a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Profile</a>
                      </router-link>
                    </li>
                    <li>
                      <a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Settings</a>
                    </li>
                    <li>
                      <a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Signout</a>
                    </li>
                    
                  </ul>
              </div>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
</script>

<style scoped>
/* Add any specific styles for Navbar */
</style>
