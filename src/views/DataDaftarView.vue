<template>
  <div>
    <Navbar />
    <div class="container">
      <div class="row mt-4">
        <div class="col">
          <h2>
            Data
            <strong>Pendaftaran</strong>
          </h2>
  <div>
    <b-table striped hover :items="items"></b-table>
  </div>
  </div>
  </div>
  </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";

export default {
  name: "Home",
  components: {
    Navbar,
  },
    data() {
      return {
        items: [
          { No_Induk: 40, Nama_Lengkap: 'Rafly', JK: 'Macdonald' },
        ]
      }
    }
}
</script>
