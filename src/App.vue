<template>
    <div id="app">
        <div class="container">
            <layout>
                <template #header="slotProps">{{slotProps.user.name}}</template>
                <template>Main text</template>
                <template #footer>Footer text</template>
                <!-- test comment -->
            </layout>
        </div>
    </div>
</template>

<script>
import BaseLayout from '@/components/BaseLayout.vue';
export default {
	name: 'app',
	components: {
		layout: BaseLayout,
	},
	data() {
		return {
			headerData: {
				logo: 'logo',
				menu: 'About Catalog Contacts',
			},
		};
	},
};
</script>

<style>
.container {
	max-width: 1200px;
	margin: 0 auto;
	padding: 0 10px;
}
</style>