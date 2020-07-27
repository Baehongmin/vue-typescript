<template>
	<v-card>
		<v-card-title>
			Nutrition
			<v-spacer></v-spacer>
			<v-text-field
				v-model="search"
				append-icon="mdi-magnify"
				label="Search"
				single-line
				hide-details
			></v-text-field>
		</v-card-title>
		<v-data-table
			:headers="headers"
			:items="desserts"
			:search="search"
		></v-data-table>
	</v-card>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
@Component({
	name: 'Table',
})
export default class Table extends Vue {
	private headers = [
		{
			text: 'Dessert (100g serving)',
			align: 'start',
			sortable: false,
			value: 'name',
		},
		{ text: 'Calories', value: 'calories' },
		{ text: 'Fat (g)', value: 'fat' },
		{ text: 'Carbs (g)', value: 'carbs' },
		{ text: 'Protein (g)', value: 'protein' },
		{ text: 'Iron (%)', value: 'iron' },
	]
}
</script>
