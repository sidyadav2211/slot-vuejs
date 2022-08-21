<template>
	<div>
		<h1>Manage Goals</h1>
		<input type="text" class="txt" ref="goal" />
		<button @click="setMyGoals">set Goal</button>
        <error-alert v-if="isInputValue">
            <h2>Input is invalid!!</h2>
            <p>Please enter something </p>
            <button @click="confirmMsg">okay</button>
        </error-alert>
	</div>
</template>

<script>
	import ErrorAlert from './ErrorAlert.vue';

	export default {
		components: {
			ErrorAlert,
		},
		data() {
			return {
				isInputValue: false,
			};
		},
		methods: {
			setMyGoals() {
				const inputValue = this.$refs.goal.value;
				if (inputValue === '') {
					this.isInputValue = true;
				}
			},
            confirmMsg(){
                this.isInputValue = false;
            }
		},
	};
</script>