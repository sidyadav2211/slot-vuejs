<template>
	<div>
		<the-header></the-header>
		<!-- <badge-list></badge-list>
		<user-info
			:full-name="activeUser.name"
			:info-text="activeUser.description"
			:role="activeUser.role"
		></user-info>
    <course-goal>
      <template #default="slotProps">
        <h2>{{slotProps.item}}</h2>
        <p>{{slotProps.hours}}</p>
       
      </template>
    </course-goal> -->

		<button @click="setGoals('active-goal')">Active Goals</button>
		<button @click="setGoals('manage-goal')">Manage Goals</button>
    
		<!-- <active-goal v-if="setHandelGoal === 'active-goal'"></active-goal>
		<manage-goal v-if="setHandelGoal === 'manage-goal'"></manage-goal> -->

    <!-- Handle Dynamic Components -->
    <keep-alive>
    <component :is="setHandelGoal"></component>
    </keep-alive>
	</div>
</template>

<script>
	// import BadgeList from './components/BadgeList.vue';
	// import UserInfo from './components/UserInfo.vue';
	import TheHeader from './components/TheHeader.vue';
	// import CourseGoal from './components/CourseGoal.vue';
	import ActiveGoal from './components/ActiveGoals.vue';
	import ManageGoal from './components/ManageGoal.vue';
	export default {
		components: {
			// BadgeList,
			// UserInfo,
			TheHeader,
			// CourseGoal,
			ManageGoal,
			ActiveGoal,
		},
		data() {
			return {
				// activeUser: {
				// 	name: 'Maximilian Schwarzmüller',
				// 	description: 'Site owner and admin',
				// 	role: 'admin',
				// },
				setHandelGoal: 'active-goal',
			};
		},
		methods: {
			setGoals(val) {
				this.setHandelGoal = val;
			},
		},
	};
</script>

<style>
	html {
		font-family: sans-serif;
	}

	body {
		margin: 0;
	}
</style>