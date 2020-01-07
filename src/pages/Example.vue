<template>
  <div class="wrapper-content wrapper-content--fixed">
    <section>
      <div class="container"> 
        <h1>Example Page</h1> 
        <br>
        <input type="text" v-model="message" >
        <br>
        <button class="btn btnPrimary" @click="setMessage">Change Message</button>
        <br>
        <br>
        <p> {{ getMessage }}</p>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      message: null
    }
  },
  // created () {
  //   this.message = this.$store.getters.getMessage
  // },
  computed: {
    getMessage () {
      return this.$store.getters.getMessage
    }
  },
  methods: {
    setMessage() {
      this.$store.dispatch('setMessage', this.message)
    }
  }
}
</script>