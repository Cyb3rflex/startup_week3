<template>
  <div class="min-h-screen flex items-center justify-center">
    <div class="w-full max-w-md p-6">
      <h2 class="text-2xl font-bold text-black-700">Welcome back</h2>
      <p class="py-4 text-black">
        Hi, my name is Eventful Moments, i am a bucket.. no, not the bucket of
        water but i store awesome moments you will like to have in coming years.
      </p>
      <form @submit.prevent="handleLogin" class="mt-4 text-center">
        <div class="mb-4">
          <label class="block text-gray-600 text-left">Email</label>
          <input
            v-model="email"
            type="email"
            placeholder="Enter your email"
            class="w-full px-3 py-2 border rounded-lg"
            required />
        </div>

        <div class="mb-4">
          <label class="block text-gray-600 text-left">Password</label>
          <input
            v-model="password"
            type="password"
            placeholder="Enter your password"
            class="w-full px-3 py-2 border rounded-lg focus:ring-blue-400"
            required />
        </div>

        <button
          type="submit"
          class="w-[150px] bg-blue-700 text-white py-2 rounded-lg hover:bg-blue-600 transition">
          Login
        </button>
      </form>
      <p class="mt-4 text-sm text-center">
        Don't have an account?
        <router-link to="/register" class="text-blue-500 hover:underline"
          >Register</router-link
        >
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();
const email = ref("");
const password = ref("");

const handleLogin = () => {
  if (email.value && password.value) {
    alert("Login successful!");
    router.push("/LoginForm");
  } else {
    alert("Please enter valid credentials.");
  }
};
</script>
