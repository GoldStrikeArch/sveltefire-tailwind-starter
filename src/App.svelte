<script>
  import { FirebaseApp, User } from "sveltefire";
  import firebase from "firebase/app";
  import "firebase/auth";
  import "firebase/storage"; //this line is causing an error "instance.INTERNAL is undefined"

  const firebaseConfig = {};
  firebase.initializeApp(firebaseConfig);
</script>

<FirebaseApp {firebase}>
  <main class="bg-red-700 text-center">
    <User let:auth let:user>
      <div slot="signed-out">Signed out</div>
    </User>
  </main>
</FirebaseApp>
