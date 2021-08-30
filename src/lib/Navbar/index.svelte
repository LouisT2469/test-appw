<script>
    import { page } from "$app/stores";
    let url = $page.path.substring(1)
</script>

<nav>
    <ul class="nav-bar">
        <li><a class="nav-link {url == 'home' ? 'active' : ''}" href="/">HOME</a></li>
        <li><a class="nav-link {url == 'register' ? 'active' : ''}" href="/register">REGISTER</a></li>
        <li><a class="nav-link {url == 'login' ? 'active' : ''}" href="/login">LOGIN</a></li>
    </ul>
</nav>