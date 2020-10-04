<script>
  import { FirebaseApp, User } from "sveltefire";
  import firebase from "firebase/app";
  import "firebase/auth";
  import "firebase/storage"; //this line is causing an error "instance.INTERNAL is undefined"
  import Login from "./components/Login.svelte";

  const firebaseConfig = {};
  firebase.initializeApp(firebaseConfig);
</script>

<FirebaseApp {firebase}>
  <main>
    <User let:auth let:user>
      <div slot="signed-out">
        <Login {auth} />
      </div>
    </User>
  </main>
</FirebaseApp>
