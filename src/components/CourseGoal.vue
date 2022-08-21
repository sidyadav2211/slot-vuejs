<template>
    <div>
        <ul>
            <li v-for="goal in goalList" :key="goal">
                <slot :item="goal.name" :hours="goal.time"></slot>
            </li>
        </ul>
    </div>

</template>

<script>
export default {
    data() {
        return{
            goalList:[{name:'Vuejs',time:'10 hours'},{name:'Reactjs',time:'14 hours'}]
        }
    },
}
</script>