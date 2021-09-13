<template>
	<form @submit.prevent="submitNewUserData">
		<div>
			<label>Name</label>
			<input type="text" v-model="userName" />
		</div>
		<div>
			<label>Age</label>
			<input type="text" v-model="userAge" />
		</div>
		<button>Add User</button>
	</form>
</template>

<script>
export default {
	data() {
		return {
			userName: '',
			userAge: '',
		};
	},
	methods: {
		submitNewUserData() {
			const newUser = {
				name: this.userName,
				age: this.userAge,
			};

			this.$emit('onSubmitUser', newUser);
		},
	},
};
</script>
