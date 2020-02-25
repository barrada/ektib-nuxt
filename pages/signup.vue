<template>
	<div id="wrapper">
			<v-row>
				<v-col cols="12" class="text-center">
						<h1>Sign up</h1>
						
				</v-col>
			</v-row>
			<v-row>
				<v-col cols="3" class="mx-auto">
						<RegistrationForm/>
				</v-col>
			</v-row>
	</div>
</template>

<script>
import RegistrationForm from '@/components/RegistrationForm.vue'

export default {
components:{
	RegistrationForm
}
}
</script>

<style>

</style>