<template>
  <div class="justify-content-center text-center">
    <b-row class="justify-content-center">
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group
        id="input-group-1"
        label-for="input-1"
        description="Sľubujeme, že Váš email bude u nás v bezpečí."
      >
        <b-form-input
          id="input-1"
          v-model="form.email"
          type="email"
          required
          placeholder="Váš email"
          autofocus
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.name"
          required
          placeholder="Vaše meno"
        ></b-form-input>
      </b-form-group>
      
      <b-form-group id="input-group-3"  label-for="input-3">
        <b-form-textarea
          id="input-3"
          v-model="form.message"
          required
          placeholder="Vaša správa"
                rows="6"
      max-rows="8"
        ></b-form-textarea>
      </b-form-group>

      <b-button type="submit" variant="primary">Odoslať</b-button>
    </b-form>
    </b-row>
  </div>
</template>

<script>
  export default {
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
      onSubmit(evt) {
        evt.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(evt) {
        evt.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.form.name = ''
        this.form.message = ''
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

<style lang="stylus" scoped>

</style>