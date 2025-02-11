<template>
  <div class="min-h-screen flex items-center justify-center bg-gray-100">
    <div class="w-full max-w-md b p-6 rounded-lg">
      <h2 class="text-2xl font-bold text-center text-gray-700">Register</h2>
      <form @submit.prevent="handleRegister" class="mt-4 text-center">
        <div class="mb-4">
          <label class="block text-gray-600 text-left">Full Name</label>
          <input
            v-model="name"
            type="text"
            placeholder="Enter your full name"
            class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2"
            required />
        </div>

        <div class="mb-4">
          <label class="block text-gray-600 text-left">Email</label>
          <input
            v-model="email"
            type="email"
            placeholder="Enter your email"
            class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2"
            required />
        </div>

        <div class="mb-4">
          <label class="block text-gray-600 text-left">Password</label>
          <input
            v-model="password"
            type="password"
            placeholder="Create a password"
            class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2"
            required />
        </div>

        <button
          type="submit"
          class="w-[150px] bg-green-500 text-white py-2 rounded-lg hover:bg-green-600 transition">
          Register
        </button>
      </form>
      <p class="mt-4 text-sm text-center">
        Already have an account?
        <router-link to="/" class="text-blue-500 hover:underline"
          >Login</router-link
        >
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();
const name = ref("");
const email = ref("");
const password = ref("");

const handleRegister = () => {
  if (name.value && email.value && password.value) {
    alert("Registration successful!");
    router.push("/");
  } else {
    alert("Please fill in all fields.");
  }
};
</script>
