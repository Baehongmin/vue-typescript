<template>
	<div class="home">
		<div class="text-center">
			<v-btn color="primary" @click="click">primary</v-btn>
		</div>
		<HelloWorld msg="Welcome to Your Vue.js App" />
	</div>
</template>

<script lang="ts">
// @ is an alias to /src
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from '@/components/HelloWorld.vue';

@Component({
	name: 'Home',
	components: {
		HelloWorld,
	},
})
export default class Home extends Vue {
	public click() {
		this.$router.push('About');
	}
}
</script>
