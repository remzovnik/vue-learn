<template>
    <div>
        <header>
            <slot name="header" :user="user"></slot>
        </header>
        <main>
            <slot></slot>
        </main>
        <footer>
            <slot name="footer"></slot>
        </footer>
    </div>
</template>
			
<script>
export default {
	name: 'BaseLayout',
	data() {
		return {
			user: {
				name: 'Vasya',
				surname: 'Pupkin',
			},
		};
	},
};
</script>

<style>
header {
	margin-bottom: 20px;
	padding: 20px;
	background: lightgreen;
}
main {
	margin-bottom: 20px;
	padding: 20px;
	background: papayawhip;
}
footer {
	padding: 20px;
	background: slateblue;
}
</style>