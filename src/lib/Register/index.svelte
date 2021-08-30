<script>
    import { sdk } from "../../appwrite";

    let email, password, username;
    let status=false

    function register() {
        let promise = sdk.account.create(email, password , username);

        promise.then(
            function (response) {
                console.log(response); // Success
                console.log("Success")
                status=true
            },
            function (error) {
                console.log(error); // Failure
                console.log("Failure")
            }
        );
    }
</script>

<div class="p-10 card bg-base-200 w-80 object-center mt-10">

    {#if status}
        
<div class="alert alert-success">
    <div class="flex-1">
        <img src="https://img.icons8.com/ios-filled/50/000000/checkmark--v1.png" alt="Haken" class="w-6 h-6 mx-2"/>
      <!-- svelte-ignore a11y-label-has-associated-control -->
      <label>Registriert!</label>
    </div>
  </div>
    {/if}

    <div class="form-control">
        <!-- svelte-ignore a11y-label-has-associated-control -->
        <label class="label">
            <span class="label-text">Benutzername</span>
        </label>
        <input
            type="text"
            placeholder="Benutzername"
            class="input"
            bind:value={username}
        />
    </div>

    <div class="form-control">
        <!-- svelte-ignore a11y-label-has-associated-control -->
        <label class="label">
            <span class="label-text">Email</span>
        </label>
        <input
            type="email"
            placeholder="Email"
            class="input"
            bind:value={email}
        />
    </div>

    <div class="form-control">
        <!-- svelte-ignore a11y-label-has-associated-control -->
        <label class="label">
            <span class="label-text">Passwort</span>
        </label>
        <input
            type="password"
            placeholder="Passwort"
            class="input"
            bind:value={password}
        />
    </div>

    <button class="btn btn-outline mt-5" on:click={register}
        >Registrieren</button
    >

</div>
