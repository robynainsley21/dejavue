<template>
  <h1>Friends</h1>
  <div class="container">
    <div v-if="!friends.length" class="spinner-border" role="status">
      <span class="visually-hidden">Loading...</span>
    </div>
    <div v-else>
      <div class="row g-3 spacing">
      <CardComp :class="{
        male: friend.gender.toLowerCase() == 'male',
        female: friend.gender.toLowerCase() == 'female'
      }" v-for="friend in friends" :key="friend.id">
        <template #cardHeader>
          <img class="image" :src="friend.profile" :alt="friend.firstName" loading="lazy">
        </template>
        <template #cardBody>
          <p>{{ friend.firstName }} {{ friend.lastName }}</p>
          <p>{{ friend.gender }}</p>
          <p>{{ friend.contact }}</p>
        </template>
      </CardComp>
    </div>
    </div>
  </div>
</template>

<script>
import CardComp from './CardComp.vue';

export default {
  name: 'FriendsComp',
  data() {
    return {
      friends: [
        {
          id: 1,
          firstName: "Keenan",
          lastName: "Theron",
          gender: 'Male',
          profile: "https://robynainsley21.github.io/images/images/profile-Image.png",
          contact: '123 456 7890'
        },
        {
          id: 2,
          firstName: "Keasha",
          lastName: "Williams",
          gender: 'Female',
          profile: "https://robynainsley21.github.io/images/images/profile-Image.png",
          contact: '123 456 7890'
        },
        {
          id: 3,
          firstName: "Jadee",
          lastName: "Paulse",
          gender: 'Female',
          profile: "https://robynainsley21.github.io/images/images/profile-Image.png",
          contact: '123 456 7890'
        }
      ]
    }
  },
  components: {
    CardComp
  }
}
</script>

<style scoped>
.male {
  border: 3px solid gold;
}

.female {
  border: 3px solid pink;
}

.spacing {
  margin: 1rem;
}

.image {
  width: 7rem;
  aspect-ratio: 1;
}

.row {
  width: 20rem;
  margin: auto;
}
</style>