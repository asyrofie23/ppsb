<template>
  <div>
    <h1>Pendaftaran Peserta Didik Baru</h1>
    <form @submit.prevent="submitForm">
      <div>
        <label>Nama Lengkap:</label>
        <input v-model="form.nama" required />
      </div>
      <div>
        <label>Email:</label>
        <input v-model="form.email" type="email" required />
      </div>
      <div>
        <label>Asal Sekolah:</label>
        <input v-model="form.asalSekolah" required />
      </div>
      <button type="submit">Daftar</button>
    </form>
    <div v-if="submitted">
      <p>Pendaftaran berhasil! Data:</p>
      <pre>{{ form }}</pre>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const form = ref({
  nama: '',
  email: '',
  asalSekolah: ''
})
const submitted = ref(false)

function submitForm() {
  submitted.value = true
  // Di sini Anda bisa menambahkan logic untuk mengirim data ke backend/API
}
</script>