<template>
	<div class="about">
		<div class="text-center">
			<v-btn color="primary" @click="click">primary</v-btn>
		</div>
		<h1>This is an about page</h1>
		<div class="text-center">
			<v-fab-transition>
				<v-btn v-show="!hidden" color="pink" fab dark small absolute left>
					<v-icon>mdi-plus</v-icon>
				</v-btn>
			</v-fab-transition>
			<v-btn color="error" @click="hidden = !hidden">+버튼생성기</v-btn>
			<v-btn color="primary" @click="click">primary</v-btn>
		</div>
		<v-card class="mx-auto" color="#DE667D" dark max-width="400">
			<v-card-title>
				<v-icon large left>
					mdi-compass-rose
				</v-icon>
				<span class="title font-weight-light">Private SNS</span>
			</v-card-title>

			<v-card-text class="headline font-weight-bold">
				"Seize the day."
			</v-card-text>

			<v-card-actions>
				<v-list-item class="grow">
					<v-list-item-avatar color="grey darken-3">
						<v-img
							class="elevation-6"
							src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortFlat&accessoriesType=Blank&hairColor=Brown&facialHairType=Blank&clotheType=Hoodie&clotheColor=Heather&eyeType=Default&eyebrowType=UpDown&mouthType=Tongue&skinColor=Light"
						></v-img>
					</v-list-item-avatar>

					<v-list-item-content>
						<v-list-item-title>Hong Bae</v-list-item-title>
					</v-list-item-content>

					<v-row align="center" justify="end">
						<v-icon class="mr-1">mdi-heart</v-icon>
						<span class="subheading mr-2">35868</span>
						<span class="mr-1">·</span>
						<v-icon class="mr-1">mdi-share-variant</v-icon>
						<span class="subheading">124</span>
					</v-row>
				</v-list-item>
			</v-card-actions>
		</v-card>

		<br />
		<v-card max-width="400" class="mx-auto">
			<v-app-bar dark color="pink">
				<v-app-bar-nav-icon></v-app-bar-nav-icon>

				<v-toolbar-title>My Music</v-toolbar-title>

				<v-spacer></v-spacer>

				<v-btn icon>
					<v-icon>mdi-magnify</v-icon>
				</v-btn>
			</v-app-bar>

			<v-container>
				<v-row dense>
					<v-col cols="12">
						<v-card color="#385F73" dark>
							<v-card-title class="headline">Unlimited music now</v-card-title>

							<v-card-subtitle
								>Listen to your favorite artists and albums whenever and
								wherever, online and offline.</v-card-subtitle
							>

							<v-card-actions>
								<v-btn text>Listen Now</v-btn>
							</v-card-actions>
						</v-card>
					</v-col>

					<v-col v-for="(item, i) in items" :key="i" cols="12">
						<v-card :color="item.color" dark>
							<div class="d-flex flex-no-wrap justify-space-between">
								<div>
									<v-card-title
										class="headline"
										v-text="item.title"
									></v-card-title>

									<v-card-subtitle v-text="item.artist"></v-card-subtitle>
								</div>

								<v-avatar class="ma-3" size="125" tile>
									<v-img :src="item.src"></v-img>
								</v-avatar>
							</div>
						</v-card>
					</v-col>
				</v-row>
			</v-container>
		</v-card>
	</div>
</template>
<script lang="ts">
// @ is an alias to /src
import { Component, Vue } from 'vue-property-decorator'

@Component({
	name: 'About',
})
export default class Home extends Vue {
	private hidden = true
	private items = [
		{
			color: '#1F7087',
			src: 'https://cdn.vuetifyjs.com/images/cards/foster.jpg',
			title: 'Supermodel',
			artist: 'Foster the People',
		},
		{
			color: '#952175',
			src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
			title: 'Halcyon Days',
			artist: 'Ellie Goulding',
		},
	]
	public click() {
		this.$router.push('/')
	}
}
</script>
