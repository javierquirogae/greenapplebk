<template>
  <div>
    <!-- Header Section -->
    <header class="bg-lime-500 text-white p-6 sticky top-0 z-50">
      <div class="flex justify-between items-center">
        <div>
          <h1 class="text-3xl font-bold">Green Apple Bookkeeping</h1>
          <p>Growing yor business one transaction at a time.</p>
        </div>
        <nav>
          <ul class="flex space-x-6">
            <li><a href="#home" class="hover:text-lime-300">Home</a></li>
            <li><a href="#services" class="hover:text-lime-300">Services</a></li>
            <li><a href="#about" class="hover:text-lime-300">About Us</a></li>
            <li><a href="#contact" class="hover:text-lime-300">Contact</a></li>
          </ul>
        </nav>
      </div>
    </header>

    <!-- Home Section -->
    <section id="home" class="text-center py-16">
      <h2 class="text-4xl font-semibold text-lime-500">Welcome to Green Apple Bookkeeping</h2>
      <p class="text-lg text-lime-500 mt-4">
        We provide expert bookkeeping services for small businesses, startups, and individuals.
      </p>
      <div class="flex justify-center items-center">
        <img
          src="https://javierquirogae.github.io/pics/pics/GA_LOGO.png"
          alt="logo"
          class="w-1/4"
        />
      </div>
      <button
        @click="contactUs"
        class="bg-lime-500 text-white px-6 py-3 mt-6 rounded-lg hover:bg-lime-600 transition"
      >
        Get in Touch
      </button>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-16 px-4 text-center">
      <h2 class="text-4xl font-semibold text-lime-500 mb-8">Our Services</h2>
      <div class="grid grid-cols-1 gap-8">
        <div class="group bg-white p-6 rounded-lg shadow-md relative">
          <h3 class="text-2xl font-semibold text-lime-500 cursor-pointer">Monthly Bookkeeping</h3>
          <p class="text-lime-500 mt-4 hidden group-hover:block">
            Accurate and timely monthly bookkeeping to keep your business finances organized.
          </p>
        </div>

        <div class="group bg-white p-6 rounded-lg shadow-md relative">
          <h3 class="text-2xl font-semibold text-lime-500 cursor-pointer">Tax Preparation</h3>
          <p class="text-lime-500 mt-4 hidden group-hover:block">
            We handle tax filing for both individuals and small businesses to ensure you stay
            compliant.
          </p>
        </div>

        <div class="group bg-white p-6 rounded-lg shadow-md relative">
          <h3 class="text-2xl font-semibold text-lime-500 cursor-pointer">Financial Reporting</h3>
          <p class="text-lime-500 mt-4 hidden group-hover:block">
            Get detailed financial reports to make informed decisions about your business's future.
          </p>
        </div>

        <div class="group bg-white p-6 rounded-lg shadow-md relative">
          <h3 class="text-2xl font-semibold text-lime-500 cursor-pointer">Consulting & Advisory</h3>
          <p class="text-lime-500 mt-4 hidden group-hover:block">
            Our expert consultants provide personalized financial advice to help you grow and manage
            your business.
          </p>
        </div>
      </div>
    </section>

    <!-- About Us Section -->
    <section id="about" class="py-16 text-center">
      <h2 class="text-4xl font-semibold text-lime-500 mb-6">About Us</h2>
      <p class="text-lg text-lime-500 justify-center items-center">
        Green Apple Bookkeeping was founded to simplify financial processes for small businesses and
        individuals. Our team of experienced bookkeepers and financial experts ensures that you can
        focus on growing your business while we take care of your books.
      </p>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-16 px-4 text-center">
      <h2 class="text-4xl font-semibold text-lime-500 mb-8">Contact Us</h2>
      <form @submit.prevent="submitForm" class="max-w-lg mx-auto space-y-6">
        <div>
          <label for="name" class="block text-lime-500">Name:</label>
          <input
            type="text"
            v-model="form.name"
            id="name"
            class="w-full px-4 py-2 mt-2 border border-lime-300 rounded-md focus:outline-none focus:ring-2 focus:ring-green-500"
            required
          />
        </div>
        <div>
          <label for="email" class="block text-lime-500">Email:</label>
          <input
            type="email"
            v-model="form.email"
            id="email"
            class="w-full px-4 py-2 mt-2 border border-lime-300 rounded-md focus:outline-none focus:ring-2 focus:ring-green-500"
            required
          />
        </div>
        <div>
          <label for="message" class="block text-lime-500">Message:</label>
          <textarea
            v-model="form.message"
            id="message"
            class="w-full px-4 py-2 mt-2 border border-lime-300 rounded-md focus:outline-none focus:ring-2 focus:ring-green-500"
            required
          ></textarea>
        </div>
        <button
          type="submit"
          class="bg-lime-500 text-white px-6 py-3 mt-6 rounded-lg hover:bg-lime-700 transition"
        >
          Submit
        </button>
      </form>
    </section>

    <!-- Footer Section -->
    <footer class="bg-lime-500 text-white text-center py-4">
      <p>&copy; 2025 Green Apple Bookkeeping LLC. All Rights Reserved.</p>
    </footer>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

interface Form {
  name: string
  email: string
  message: string
}

export default defineComponent({
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: '',
      } as Form,
    }
  },
  methods: {
    submitForm() {
      // Handle form submission, e.g., send the data to your backend
      alert(`Thank you, ${this.form.name}. We will get back to you soon!`)
      this.resetForm()
    },
    resetForm() {
      this.form.name = ''
      this.form.email = ''
      this.form.message = ''
    },
    contactUs() {
      document.querySelector('#contact')?.scrollIntoView({ behavior: 'smooth' })
    },
  },
})
</script>

<style scoped>
/* No custom styles needed as Tailwind CSS handles all styling */
</style>
