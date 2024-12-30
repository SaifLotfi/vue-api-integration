<template>
  <div class="flex flex-col items-center justify-center min-h-screen">
    <div class="mx-auto w-full max-w-md">
      <v-img class="mx-auto my-6" max-width="228"
        src="https://cdn.vuetifyjs.com/docs/images/logos/vuetify-logo-v3-slim-text-light.svg"></v-img>

      <v-card class="mx-auto pa-12 pb-8" elevation="8" max-width="448" rounded="lg">
        <div class="text-subtitle-1 text-medium-emphasis">Email</div>

        <v-text-field density="compact" placeholder="Email address" prepend-inner-icon="mdi-email-outline"
          variant="outlined"></v-text-field>

        <div class="text-subtitle-1 text-medium-emphasis">Username</div>

        <v-text-field density="compact" placeholder="Username" variant="outlined"
          prepend-inner-icon="mdi-email-outline"></v-text-field>

        <div class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-space-between">
          Password
        </div>

        <v-text-field :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'" :type="visible ? 'text' : 'password'"
          density="compact" placeholder="Enter your password" prepend-inner-icon="mdi-lock-outline" variant="outlined"
          @click:append-inner="visible = !visible"></v-text-field>

        <v-select v-model="select" :items="roles" :rules="[v => !!v || 'Role is required']" label="Role"
          required></v-select>

        <v-btn class="mb-8" color="blue" size="large" variant="tonal" block>
          Register
        </v-btn>
      </v-card>
    </div>
  </div>
</template>

<script setup>
const roles = ['ADMIN', 'USER']
</script>
