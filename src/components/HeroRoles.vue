<template>
    <div class="roles_container">
        <span v-for="role in roles" :key="role">
            <img class="roles_icon" :src="this.ROLES[role] " alt="a"><p> {{role}} </p>
        </span>
    </div>
</template>

<script>
import { ROLES } from '../utils/heroIcons'

export default {
    name: 'HeroRoles',
    data() {
        return {
            ROLES
        }
    },
    props: {
        roles: Array
    }
}
</script>

<style>
.roles_container {
    display: flex;
    justify-content: space-around;
}
.roles_icon {
    width: 32px;
}
</style>