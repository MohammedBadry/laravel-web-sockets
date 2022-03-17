<template>
    <div>
        {{ notification }}
    </div>
</template>

<script>
    export default {
        name: "HomeComponent",
        data() {
            return {
                notification: ""
            }
        },
        mounted() {
            window.Echo.channel('Notify').listen('NotificationTest', event => {
                this.notification = event.msg
            })
        }
    }
</script>
