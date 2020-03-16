<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld :msg="msg" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld
  },
  data() {
    return {
      msg: ''
    }
  },
  methods: {
    getMessage() {
      this.$axios.get('http://localhost/api')
        .then(response => {
          this.msg = response.data.message
        })
    }
  },
  created() {
    this.getMessage()
  }
};
</script>
