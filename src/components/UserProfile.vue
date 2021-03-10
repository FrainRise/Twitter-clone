<template>
    <div class="user-profile">
        <div class="user-profile__user-panel">
            <h1 class="user-profile__username">
                {{ user.username }}
            </h1>
            <div class="user-profile__follower-count" style="margin: 50px 0">
                <strong>Followers: {{ followers }}</strong>
            </div>
        </div>
        <button class="btn-follow" @click="followUser">
            Follow
        </button>
    </div>
</template>

<script>
export default {
    name: 'UserProfile',
    data() {
        return {
        followers: 0,
        user: {
            id: 1,
            username: 'FrainRisen',
            firstName: 'Andrew',
            lastName: 'Kovalenko',
            email: 'an.kava@gmail.com',
            isAdmin: true
            }
        }
    },
    watch: {
        followers(newFollower, oldFollower) {
            if(oldFollower < newFollower){
                console.log(`${this.user.username} has gained a follower!`)
            }
        }
    },
    computed: {
        fullName() {
            return `${this.user.firstName} ${this.user.lastName}`
        }
    },
    methods: {
        followUser() {
            this.followers += 1;
        } 
    },
    mounted() {
        this.followUser();
        console.log('Component was mounted ')
    },
}
</script>

<style>

</style>