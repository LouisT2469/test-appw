<script>
    import { sdk } from "../../appwrite";

    let email, password;
    let status = false;

    function login() {
        let promise = sdk.account.createSession(email, password);

        promise.then(
            function (response) {
                console.log(response); // Success
                console.log("Success");
                status=true
            },
            function (error) {
                console.log(error); // Failure
                console.log("Failure");
            }
        );
    }
</script>

<div class="p-10 card bg-base-200 w-80 object-center mt-10">
    {#if status}
        <div class="alert alert-success">
            <div class="flex-1">
                <img
                    src="https://img.icons8.com/ios-filled/50/000000/checkmark--v1.png"
                    alt="Haken"
                    class="w-6 h-6 mx-2"
                />
                <!-- svelte-ignore a11y-label-has-associated-control -->
                <label>Eingeloggt!</label>
            </div>
        </div>
    {/if}

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

    <button class="btn btn-outline mt-5" on:click={login}>Login</button>
</div>
