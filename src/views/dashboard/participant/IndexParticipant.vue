<template>
  <b-container>
    <div class="bg-light text-dark mb-3 rounded shadow-sm header">
      <h3 class="text-left d-inline float-left">
        <i class="fa fa-users"></i>
        Daftar Peserta
      </h3>
    </div>
    <hr />
    <router-view/>
  </b-container>
</template>
<script>
export default {
  name: 'IndexParticipant',
  computed: {
  },
};
</script>
<style scoped>
.header {
  overflow: auto;
  min-width: 100%;
  padding: 30px;
}
</style>
