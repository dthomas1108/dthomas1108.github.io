<template>
  <div class="container mx-auto px-6 py-20">
    <div class="max-w-2xl mx-auto">
      <h1 class="text-5xl font-bold mb-8 text-center">Get in Touch</h1>
      <p class="text-gray-400 text-center mb-12 text-lg">
        Have a project in mind or want to discuss opportunities? Feel free to reach out!
      </p>

      <form @submit.prevent="handleSubmit" class="space-y-6">
        <div>
          <label for="name" class="block text-sm font-medium mb-2">Name</label>
          <input
              v-model="form.name"
              type="text"
              id="name"
              required
              class="w-full px-4 py-3 bg-gray-900 border border-gray-800 rounded-lg focus:outline-none focus:border-green-500 transition-colors"
              placeholder="Your name"
          />
          <label for="email" class="block text-sm font-medium mb-2">Email</label>
          <input
              v-model="form.email"
              type="email"
              id="email"
              required
              class="w-full px-4 py-3 bg-gray-900 border border-gray-800 rounded-lg focus:outline-none focus:border-green-500 transition-colors"
              placeholder="your.email@example.com"
          />
        </div>

        <div>
          <label for="message" class="block text-sm font-medium mb-2">Message</label>
          <textarea
              v-model="form.message"
              id="message"
              required
              rows="6"
              class="w-full px-4 py-3 bg-gray-900 border border-gray-800 rounded-lg focus:outline-none focus:border-green-500 transition-colors resize-none"
              placeholder="Tell me about your project"
          ></textarea>
        </div>

        <button type="submit" :disabled="isSubmitting" class="w-full px-8 py-3 bg-green-500 hover:bg-green-600 disabled:bg-gray-700 text-black font-semibold rounded-lg transition-colors">
          {{ isSubmitting ? 'Sending...' : 'Send Message' }}
        </button>

        <p v-if="submitMessage" class="text-center" :class="submitSuccess ? 'text-green-500' : 'text-red-500'" >
          {{ submitMessage }}
        </p>
      </form>

      <div class="mt-16 grid md:grid-cols-2 gap-6">
        <a href="mailto:dylanthomas1108@gmail.com" class="p-6 border border-gray-800 rounded-lg hover:border-green-500 transition-colors text-center">
          <p class="text-gray-400 mb-2">Email</p>
          <p class="text-white">dylanthomas1108@gmail.com</p>
        </a>
        <a href="https://linkedin.com/in/yourprofile" target="_blank" class="p-6 border border-gray-800 rounded-lg hover:border-green-500 transition-colors text-center">
          <p class="text-gray-400 mb-2">LinkedIn</p>
          <p class="text-white">Connect with me →</p>
        </a>
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref } from 'vue';

const form = ref({
  name: '',
  email: '',
  message: ''
});

const isSubmitting = ref(false);
const submitMessage = ref('');
const submitSuccess = ref(false);

const handleSubmit = async () => {
  isSubmitting.value = true;
  submitMessage.value = '';

  try {
    const response = await fetch('https://formspree.io/f/xdkykkpe', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify(form.value)
    });

    if (!response.ok) {
      throw new Error('Failed to send');
    }

    console.log('Form submitted');
    submitMessage.value = 'Message sent successfully! I\'ll get back to you soon!'
    submitSuccess.value = true;

    form.value = {
      name: '',
      email: '',
      message: ''
    }
  } catch (error) {
    submitMessage.value = 'Something went wrong! Please try again';
    submitSuccess.value = false;
  } finally {
    isSubmitting.value = false;
  }
}
</script>