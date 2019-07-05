<template>
    <div id="app">
        <first-component v-show="showFirst" :handleClick="handleClick"></first-component>
        <second-component v-show="!showFirst" :handleClick="handleClick"></second-component>
    </div>
</template>

<script>
import FirstComponent from './components/FirstComponent.vue';
import SecondComponent from './components/SecondComponent.vue';

export default {
	name: 'app',
	components: {
		FirstComponent,
		SecondComponent,
	},
	data() {
		return {
			showFirst: true,
		};
	},
	methods: {
		handleClick(val) {
			this.showFirst = val;
		},
	},
};
</script>

<style>
.component > * {
	margin: 20px;
}

button {
	font-size: 22px;
}
</style>
 
