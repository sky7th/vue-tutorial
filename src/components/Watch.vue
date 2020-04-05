<template>
  <div id="app">    
    <input v-model="firstname" />
    <input v-model="lastname"/>

    <h2>full name</h2>
    <span>{{ fullname }}</span>
    <span></span>
  </div>  
</template>

<script>

export default {
  name: 'app',
  data () {
    return {
      firstname: '',
      lastname: ''
    }
  },
  // watch: {
  //   firstname (val) {
  //     this.fullname = `${val + " " + this.lastname}`
  //   },
  //   lastname (val) {
  //     this.fullname = `${this.firstname} ${val}`
  //   }
  // }
  computed: {
    fullname () {
      return `${this.firstname} ${this.lastname}`
    }
  }
}
</script>