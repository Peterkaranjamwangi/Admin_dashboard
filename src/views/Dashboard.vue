<template>
  <div class="dashboard">
    <index />
  </div>
</template>

<script>
// @ is an alias to /src
import Index from '../components/Index.vue';

export default {
  name: "Dashboard",
  components: {
    Index,
  },
};
</script>
