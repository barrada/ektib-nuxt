<template>
  <div id="wrapper">
		<Login />
	</div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'
import Login from '~/components/Login.vue'

export default {
  components: {
    Login,
    Logo,
    VuetifyLogo
  }
}
</script>
