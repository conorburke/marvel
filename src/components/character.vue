<template>
  <div>
    <ul v-for="character in characters">
      <li>
        <h2>{{ character.name }}</h2>
      </li>
      <li>
        <!-- <img src="http://7bna.net/images/wolverine-images/wolverine-images-30.jpg"  /> -->
        <img v-bind:src="character.url" />
      </li>
    </ul>
    <!-- <h1>{{ msg }}</h1>
    <img src="../assets/logan.jpg" /> -->
  </div>
</template>

<script>
  import Firebase from 'firebase';
  // import toastr from 'toastr';

  const config = {
    apiKey: 'AIzaSyDPW7LuPk9nsZsgU_JrpJMXVaha7yOCgm8',
    authDomain: 'marvel-afa59.firebaseapp.com',
    databaseURL: 'https://marvel-afa59.firebaseio.com',
    projectId: 'marvel-afa59',
    storageBucket: 'marvel-afa59.appspot.com',
    messagingSenderId: '288768387483'
  };

  const app = Firebase.initializeApp(config);
  const db = app.database();

  const charRef = db.ref('characters');

  export default {
    name: 'character',
    firebase: {
      characters: charRef
    },
    data() {
      return {
        msg: 'Logan!'
      };
    }
  };
</script>

<style scoped>
</style>
