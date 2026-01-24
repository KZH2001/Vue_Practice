<template>
  <div>
    <h2>This is popup</h2>
    <input v-model.trim="name" type="text" />
    <button @click="$emit('close', name)">Close popup</button>
  </div>
</template>

<script>
export default {
  // name: "Popup",
  emits: ["close"],
  data() {
    return {
      name: "",
    };
  },
};
</script>
