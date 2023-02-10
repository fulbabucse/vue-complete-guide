<template>
  <div class="mt-10 max-w-screen-xl mx-auto">
    <friend-contact
      v-for="friend in friends"
      :key="friend.id"
      :id="friend.id"
      :name="friend.name"
      :phone="friend.phone"
      :email="friend.email"
      :isFavorite="friend.isFavorite"
      @toggle-favorite="toggleFavoriteStatus"
    ></friend-contact>
  </div>
</template>

<script>
export default {
  data() {
    return {
      friends: [
        {
          id: "01",
          name: "Fahim Islam",
          phone: "124545",
          email: "fahim@islam.com",
          isFavorite: true,
        },
        {
          id: "02",
          name: "Fulbabu",
          phone: "5454545",
          email: "ful@babu.com",
          isFavorite: false,
        },
      ],
    };
  },
  methods: {
    toggleFavoriteStatus(friendId) {
      let identified = this.friends.find((friend) => friend.id === friendId);
      identified.isFavorite = !identified.isFavorite;
    },
  },
};
</script>
