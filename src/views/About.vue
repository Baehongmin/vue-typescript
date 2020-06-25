<template>
	<div class="about">
		<div class="text-center">
			<v-btn color="primary" @click="click">primary</v-btn>
		</div>
		<h1>This is an about page</h1>
	</div>
</template>
<script lang="ts">
// @ is an alias to /src
import { Component, Vue } from 'vue-property-decorator';

@Component({
	name: 'About',
})
export default class Home extends Vue {
	public click() {
		this.$router.push('/');
	}
}
</script>
