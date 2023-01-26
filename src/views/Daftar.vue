<template>
  <div>
    <Navbar />
    <div class="container">
      <div class="row mt-4">
        <div class="col">
          <h2>
            Daftar
            <strong>Peserta Didik</strong>
          </h2>
       <h5><b-form-group
        id="input-group-1"
        label="No Induk:"
        label-for="input-0"
       >
       <b-form-input
          id="input-1"
          v-model="form.induk"
          type="name"
          placeholder=""
          required
        ></b-form-input>
      </b-form-group>
       </h5>
        </div>
      </div>
  <div>
    <br>
    <br>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group
        id="input-group-1"
        label="Nama Lengkap:"
        label-for="input-1"
      >
        <b-form-input
          id="input-1"
          v-model="form.name"
          type="name"
          placeholder=""
          required
        ></b-form-input>
      </b-form-group>
        <br>
      <b-form-group id="input-group-2" label="Jenis Kelamin:" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.jk"
          placeholder=""
          required
        ></b-form-input>
      </b-form-group>
      <br>
      <b-form-group id="input-group-3" label="Nama Ayah:" label-for="input-3">
        <b-form-input
          id="input-3"
          v-model="form.ayah"
          placeholder=""
          required
        ></b-form-input>
      </b-form-group>
      <br>
      <b-form-group id="input-group-4" label="Nama Ibu:" label-for="input-4">
        <b-form-input
          id="input-4"
          v-model="form.ibu"
          placeholder=""
          required
        ></b-form-input>
      </b-form-group>
      <br>
      <router-link to="datadaftar" class="btn btn-primary me-2" type="submit" variant="primary">Daftar</router-link>
      <b-button type="reset" variant="danger">Batal</b-button>
    </b-form>
  </div>
  </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";

  export default {
  name: "Daftar",
  components: {
    Navbar,
  },
    data() {
      return {
        form: {
          email: '',
          name: '',
          food: null,
          checked: []
        },
        foods: [{ text: 'Select One', value: null }, 'Carrots', 'Beans', 'Tomatoes', 'Corn'],
        show: true
      }
    },
    methods: {
      onSubmit(event) {
        event.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(event) {
        event.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.form.name = ''
        this.form.food = null
        this.form.checked = []
        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
  }
</script>
