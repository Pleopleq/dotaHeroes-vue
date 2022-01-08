<template>
    <div class="roles_container">
        <span v-for="role in roles" :key="role">
            <img class="roles_icon" :src="this.ROLES[role] " alt="a"><p> {{role}} </p>
        </span>
    </div>
</template>

<script>
const CarryIcon = require('../assets/img/Carry.png')
const DisablerIcon = require('../assets/img/Disabler.png')
const DurableIcon = require('../assets/img/Durable.png')
const EscapeIcon = require('../assets/img/Escape.png')
const InitiatorIcon = require('../assets/img/Initiator.png')
const JunglerIcon = require('../assets/img/Jungler.png')
const NukerIcon = require('../assets/img/Nuker.png')
const PusherIcon = require('../assets/img/Pusher.png')
const SupportIcon = require('../assets/img/Support.png')
export default {
    name: 'HeroRoles',
    data() {
        return {
            ROLES : {
            Carry: CarryIcon,
            Disabler: DisablerIcon,
            Durable : DurableIcon,
            Escape: EscapeIcon,
            Initiator : InitiatorIcon,
            Jungler : JunglerIcon,
            Nuker : NukerIcon,
            Pusher : PusherIcon,
            Support : SupportIcon
            }
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