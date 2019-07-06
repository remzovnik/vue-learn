<template>
    <div id="app">
        <ul class="tabs">
            <li>
                <button
                    type="button"
                    :class="['tab', {'active': currentTest == 'TransitionTest' }]"
                    @click="currentTest = 'TransitionTest'"
                >Transition</button>
            </li>
            <li>
                <button
                    type="button"
                    :class="['tab', {'active': currentTest == 'AnimationTest' }]"
                    @click="currentTest = 'AnimationTest'"
                >Animation</button>
            </li>
            <li>
                <button
                    type="button"
                    :class="['tab', {'active': currentTest == 'SwitchTest' }]"
                    @click="currentTest = 'SwitchTest'"
                >Switch</button>
            </li>
        </ul>
        <ul class="content">
            <li>
                <component :is="currentTest"></component>
            </li>
        </ul>
    </div>
</template>

<script>
import TransitionTest from '@/components/TransitionTest.vue';
import AnimationTest from '@/components/AnimationTest.vue';
import SwitchTest from '@/components/SwitchTest.vue';

export default {
	name: 'app',
	components: {
		TransitionTest,
		AnimationTest,
		SwitchTest,
	},
	data() {
		return {
			currentTest: 'TransitionTest',
		};
	},
};
</script>

<style>
.tabs {
	margin: 0 0 30px;
	padding: 0;
	list-style: none;
	display: flex;
}
.tab {
	width: 150px;
	height: 40px;
	margin-right: 5px;
	border: none;
	border-bottom: 2px solid palegreen;
}
.tab.active {
	background: palegreen;
}
.content {
	margin: 0;
	padding: 0;
	list-style: none;
}
.toggler {
	width: 150px;
	height: 30px;
	margin-bottom: 50px;
}

.block {
	width: 150px;
	height: 150px;
}
</style>