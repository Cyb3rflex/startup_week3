<script setup>
import { useForm, useField } from "vee-validate";
import * as yup from "yup";

const schema = yup.object({
  email: yup.string().email("Invalid email").required("Email is required"),
  password: yup
    .string()
    .min(6, "Password must be at least 6 characters")
    .required("Password is required"),
});

const { handleSubmit } = useForm({ validationSchema: schema });
const { value: email, errorMessage: emailError } = useField("email");
const { value: password, errorMessage: passwordError } = useField("password");

const onSubmit = handleSubmit((values) => {
  console.log("Form Submitted:", values);
});
</script>

<template>
  <div class="login-container">
    <h2 class="header">Welcome back,</h2>
    <p>Hi, my name is Eventful Moments...</p>

    <form @submit.prevent="onSubmit">
      <label>Email</label>
      <input v-model="email" type="email" placeholder="Enter your email" />
      <span class="error">{{ emailError }}</span>

      <label>Password</label>
      <input
        v-model="password"
        type="password"
        placeholder="Enter your password" />
      <span class="error">{{ passwordError }}</span>

      <button type="submit">Login</button>
    </form>
  </div>
</template>

<style scoped>
.login-container {
  max-width: 400px;
  margin: auto;
  text-align: center;
  padding: 20px;
  border: 1px solid red;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.header {
  background: teal;
  color: white;
  padding: 10px;
  margin-bottom: 10px;
}

input {
  width: 100%;
  padding: 10px;
  margin: 5px 0;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  background: blue;
  color: white;
  padding: 10px;
  width: 100%;
  border: none;
  cursor: pointer;
  border-radius: 4px;
}

.error {
  color: red;
  font-size: 12px;
}
</style>
