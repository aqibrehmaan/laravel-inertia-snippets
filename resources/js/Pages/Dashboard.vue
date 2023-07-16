<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import {Head, useForm} from "@inertiajs/vue3";
import toast from "@/Stores/toast";

const form = useForm({});

function submit() {
  form.post("/test");
}

function addToast() {
  toast.add({
    message: "Hello from dashboard",
  });
}
</script>

<template>
  <Head title="Dashboard" />

  <AuthenticatedLayout>
    <template #header>
      <h2 class="text-xl font-semibold leading-tight text-gray-800">
        Dashboard
      </h2>
    </template>

    <div class="py-12">
      <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
        <div class="overflow-hidden bg-white shadow-sm sm:rounded-lg">
          <form @submit.prevent="submit">
            <button>Submit</button>
          </form>

          <button @click="addToast">Add toast</button>
        </div>
      </div>
    </div>
  </AuthenticatedLayout>
</template>
