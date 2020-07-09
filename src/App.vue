<template>
	<v-app>
		<v-app-bar app clipped-left color="red" dense>
			<v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
			<v-icon class="mx-4" large>
				mdi-telegram
			</v-icon>
			<v-toolbar-title class="mr-12 align-center">
				<span class="title">HongTube</span>
			</v-toolbar-title>
			<v-spacer></v-spacer>
			<v-row align="center" style="max-width: 650px">
				<v-text-field
					:append-icon-cb="() => {}"
					placeholder="Search..."
					single-line
					append-icon="mdi-magnify"
					color="white"
					hide-details
				></v-text-field>
			</v-row>
		</v-app-bar>

		<v-main>
			<router-view />
		</v-main>
	</v-app>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
@Component({
	name: 'App',
})
export default class App extends Vue {
	private drawer = null;
}
</script>
