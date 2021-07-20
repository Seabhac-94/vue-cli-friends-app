<template>
<section>
    <header>
        <h1>My Friends</h1>
    </header>    
    <ul>
        <friend-contact
        v-for="friend in friends"
        :key="friend.id"
        :name="friend.name"
        :id="friend.id"
        :phone-number="friend.phone"
        :email-address="friend.email"
        :is-favourite="friend.isFavourite"
        @toggle-favourite="toggleFavouriteStatus"
        ></friend-contact>
    </ul>
</section>
</template>

<script>
export default {
    data() {
        return {
            friends: [
                {
                    id: "manuel",
                    name: "Manuel Lorenz",
                    phone: "0123 45689 90",
                    email: "manuel@localhost.com",
                    isFavourite: true
                },
                {
                    id: "julie",
                    name: "Julie Jones",
                    phone: "0987 12345 78",
                    email: "julie@localhost.com",
                    isFavourite: false
                }
            ]
        }
    },
    methods: {
        toggleFavouriteStatus(friendId) {
            const identifedFriend = this.friends.find(friend => friend.id === friendId);
            identifedFriend.isFavourite = !identifedFriend.isFavourite
        }
    } 
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Jost&display=swap');
</style>