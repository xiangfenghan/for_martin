<template>
    <div>
        <b-navbar toggleable="lg" type="dark" variant="dark">
            <b-navbar-brand href="#">
                <img src="https://picsum.photos/30/30" alt="logo">
                <span>Tintin</span>
            </b-navbar-brand>

            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
            <b-collapse id="nav-collapse" is-nav>
                <!-- Right aligned nav items -->
                <b-navbar-nav class="ml-auto" right>
                    <b-nav-item href="#">Projects</b-nav-item>
                    <b-nav-item href="#">Manage Roles</b-nav-item>
                    <b-nav-item href="#">Create new role</b-nav-item>
                    <b-nav-item href="#">tintin@audioz.com</b-nav-item>
                </b-navbar-nav>
            </b-collapse>
        </b-navbar>
    </div>
</template>

<script>
export default {
    name: "Nav"
}
</script>

<style scoped>
    .navbar-brand img,
    .navbar-brand span {
        display: inline-block;
        vertical-align: middle;
    }

    .navbar-brand span {
        margin: 0 0 0 10px;
    }
</style>