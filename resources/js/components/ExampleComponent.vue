<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Example Component</div>

                    <div class="card-body">
                        I'm an example component.
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import io from 'socket.io-client'
    export default {
        mounted() {
            var socket = io('http://local.realtime.com:3000');
            socket.on('news', function (data) {
                console.log(data);
                socket.emit('my other event', { my: 'data' });
            });
            console.log('Component mounted.')
        }
    }
</script>
