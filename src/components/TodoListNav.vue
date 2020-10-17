<template>
    <nav>
        <button>
            <!-- Check that the SDK client is not currently loading before accessing is methods -->
            <div v-if="!$auth.loading">
                <!-- show login when not authenticated -->
                <a
                    v-if="!$auth.isAuthenticated"
                    @click="login"
                    ><strong>Sign in</strong></a
                >
                <!-- show logout when authenticated -->
                <a
                    v-if="$auth.isAuthenticated"
                    @click="logout"
                    ><strong>Log out</strong></a
                >
            </div>
        </button>
    </nav>
</template>

<script>
export default {
    name: 'TodoListNav',
    methods: {
        // Log the user in
        login() {
            this.$auth.loginWithRedirect();
        },
        // Log the user out
        logout() {
            this.$auth.logout({
                returnTo: window.location.origin,
            });
        },
    },
};
</script>

<style></style>
