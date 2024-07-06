<script setup>
import { ref, onMounted } from "vue";
const supabase = useSupabaseClient();

const responseData = ref(null);

onMounted(async () => {
  try {
    const response = await fetch(
      "https://api.ipdata.co/?api-key=9753efd4aae96e16d5783e4d1a3309bf1632cb8b4fedd26d1cec46dd"
    );
    responseData.value = await response.json();
  } catch (error) {
    console.error("Error fetching data:", error);
  }

  const { data, error } = await supabase
    .from("ip_visiters_record")
    .insert([
      { user_object: responseData.value, ip_address: responseData.value?.ip },
    ]);

  if (data) {
    console.log("Data:", data);
  } else if (error) {
    if (error?.details.includes("already exists")) {
      const { data, error } = await supabase
        .from("ip_visiters_record")
        .update({ user_object: responseData.value })
        .eq("ip_address", responseData.value?.ip)
        .select();
    } else {
      console.error("Error:", error);
    }
  }
});
</script>

<template>
  <div class="p-5 md:p-10">
    <div class="my-5 text-xl font-bold text-center w-full">
      We Are Saving your Information 😄 that you have visited this site.
    </div>
    <pre v-if="responseData">{{ responseData }}</pre>
    <p v-else>Loading...</p>
  </div>
</template>
