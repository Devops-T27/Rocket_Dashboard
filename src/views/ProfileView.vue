<template>
    <div>
        <SideBar>
            <NavBar /><br><br><br>
            <div class="min-h-screen flex justify-center items-center bg-gray-100">
              <div class="w-full max-w-4xl">
                <!-- Edit Profile Section -->
                <div class="mb-8 p-8 bg-white shadow-sm">
                  <h2 class="text-xl font-semibold mb-2">Edit Profile</h2>
                  <form @submit.prevent="submitProfile">
                    <div class="mb-4">
                      <label for="firstname" class="block text-gray-700">First Name</label>
                      <input v-model="firstName" type="text" id="firstname" name="firstname" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 " placeholder="John" required />
                    </div>
                    <div class="mb-4">
                      <label for="lastname" class="block text-gray-700">Last Name</label>
                      <input v-model="lastName" type="text" id="lastname" name="lastname" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 " placeholder="John" required />
                    </div>
                    <div class="mb-4">
                      <label for="email" class="block text-gray-700">Email</label>
                      <input v-model="email" type="email" id="email" name="email" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 " placeholder="John" required />
                    </div>
                    <div class="mb-4">
                      <label for="phone" class="block text-gray-700">Phone</label>
                      <input v-model="phone" type="text" id="phone" name="phone" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 " placeholder="John" required />
                    </div>
                    <button type="submit" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">Update</button>
                  </form>
                </div>

                <!-- Change Password Section -->
                <div class="mb-8 bg-white shadow-sm p-8">
                  <h2 class="text-xl font-semibold mb-2">Change Password</h2>
                  <form @submit.prevent="submitPassword">
                    <div class="mb-4">
                      <label for="currentPassword" class="block text-gray-700">Current Password</label>
                      <input type="password" id="currentPassword" name="currentPassword" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 " />
                    </div>
                    <div class="mb-4">
                      <label for="newPassword" class="block text-gray-700">New Password</label>
                      <input type="password" id="newPassword" name="newPassword" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 " />
                    </div>
                    <div class="mb-4">
                      <label for="confirmPassword" class="block text-gray-700">Confirm Password</label>
                      <input type="password" id="confirmPassword" name="confirmPassword" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 " />
                    </div>
                    <button type="submit" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">Change Password</button>
                  </form>
                </div>

                <!-- Change Avatar Section -->
                <div class="mb-8 bg-white shadow-sm p-8 font-bold">
                  <h2 class="text-xl font-semibold mb-2">Change Avatar</h2>
                  <div class="flex flex-col items-center">
                    <div class="relative">
                      <img :src="imageUrl" alt="Profile Picture" class="w-32 h-32 rounded-full object-cover border-2 border-gray-300">
                      <input type="file" @change="onFileChange" class="absolute inset-0 opacity-0 cursor-pointer">
                    </div>
                    <button @click="uploadImage" class="mt-4 px-4 py-2 bg-blue-600 text-white rounded">Update Profile Picture</button>
                  </div>
                </div>
    <!-- Delete Account Section -->
                <div class="mb-8 bg-white shadow-sm p-8">
                  <h2 class="text-xl font-semibold mb-2">Delete Account</h2>
                  <form @submit.prevent="submitAvatar">
                    <div class="mb-4">
                      <div id="alert-additional-content-2" class="p-4 mb-4 text-red-800 border border-red-300 rounded-lg bg-red-50 " role="alert">
                  <div class="flex items-center">
                    <svg class="flex-shrink-0 w-4 h-4 me-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
                      <path d="M10 .5a9.5 9.5 0 1 0 9.5 9.5A9.51 9.51 0 0 0 10 .5ZM9.5 4a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3ZM12 15H8a1 1 0 0 1 0-2h1v-3H8a1 1 0 0 1 0-2h2a1 1 0 0 1 1 1v4h1a1 1 0 0 1 0 2Z"/>
                    </svg>
                    <span class="sr-only">Info</span>
                    <h3 class="text-lg font-medium">This is a danger alert</h3>
                  </div>
                  <div class="mt-2 mb-4 text-sm">
                    More info about this info danger goes here. This example text is going to run a bit longer so that you can see how spacing within an alert works with this kind of content.
                  </div>
                  <div class="flex">
                    <button type="button" class="text-white bg-red-800 hover:bg-red-900 focus:ring-4 focus:outline-none focus:ring-red-300 font-medium rounded-lg text-xs px-3 py-1.5 me-2 text-center inline-flex items-center ">
                      <svg class="me-2 h-3 w-3" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 14">
                        <path d="M10 0C4.612 0 0 5.336 0 7c0 1.742 3.546 7 10 7 6.454 0 10-5.258 10-7 0-1.664-4.612-7-10-7Zm0 10a3 3 0 1 1 0-6 3 3 0 0 1 0 6Z"/>
                      </svg>
                      View more
                    </button>
                    <button type="button" class="text-red-800 bg-transparent border border-red-800 hover:bg-red-900 hover:text-white focus:ring-4 focus:outline-none focus:ring-red-300 font-medium rounded-lg text-xs px-3 py-1.5 text-center  " data-dismiss-target="#alert-additional-content-2" aria-label="Close">
                      Dismiss
                    </button>
                  </div>
                </div>
            </div>
          <button type="submit" class="text-white bg-red-700 hover:bg-red-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center">Delete This Account</button>
        </form>
      </div>
    </div>
  </div>
        </SideBar>
    </div>
    
</template>
  
<script setup>
import { ref } from 'vue';
import NavBar from './components/NavbarView.vue';
import SideBar from './components/SidebarView.vue';
import defaultImage from '@/assets/logo.png';
const activeSection = 'editProfile';
//change activeSection to use ref
const imageUrl = ref(defaultImage); // default image
const selectedFile = ref(null);

const onFileChange = (event) => {
  const file = event.target.files[0];
  if (file) {
    selectedFile.value = file;
    imageUrl.value = URL.createObjectURL(file);
  }
};

const uploadImage = () => {
  if (selectedFile.value) {
    const formData = new FormData();
    formData.append('file', selectedFile.value);

    // Assuming you have an API endpoint to handle the file upload
    fetch('YOUR_API_ENDPOINT', {
      method: 'POST',
      body: formData,
    })
      .then(response => response.json())
      .then(data => {
        console.log('Success:', data);
        // Handle success (e.g., update the imageUrl with the uploaded image URL)
      })
      .catch((error) => {
        console.error('Error:', error);
      });
  }
};
</script>

<style scoped>
/* Add any custom styles here if needed */
input[type="file"] {
  width: 128px;
  height: 128px;
  cursor: pointer;
  opacity: 0;
  position: absolute;
  top: 0;
  left: 0;
}
</style>
