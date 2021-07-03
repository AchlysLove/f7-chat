<template>
  <f7-page no-toolbar no-navbar no-swipeback login-screen>
    <f7-login-screen-title>Framework7</f7-login-screen-title>
    <f7-list form>
      <f7-list-input
          label="Username"
          type="text"
          placeholder="Your username"
          :value="username"
          @input="username = $event.target.value"
      ></f7-list-input>
    </f7-list>
    <f7-list>
      <f7-list-button @click="signIn">Sign In</f7-list-button>
    </f7-list>
  </f7-page>
</template>

<script>
import { f7 } from 'framework7-vue'

export default {
  name: 'login',
  components: {},
  filters: {},
  props: {
    f7router: Object,
  },
  data () {
    return {
      username: '',
      password: ''
    }
  },
  computed: {},
  watch: {},
  beforeCreate () {},
  created () {},
  beforeMount () {},
  mounted () {},
  beforeUpdate () {},
  updated () {},
  activated () {},
  deactivated () {},
  beforeDestroy () {},
  destroyed () {},
  methods: {
    signIn () {
      // if (this.username.trim())
      // console.log(this.username.trim())
      if (this.username.trim().length > 0) {
        console.log('valid username', this.username)
        this.f7router.navigate('/chat/', {
          props: {
            username: this.username,
          }
        })
      }
    }
  }
}
</script>

<style scoped lang='scss'>

</style>
