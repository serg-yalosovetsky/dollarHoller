<script lang="ts">
    import * as sock from 'websocket';
    let token = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNjkyNzU2NDE0LCJqdGkiOiI2N2VkZTkzMjRkNzY0YjY4OTNkNTI2N2I2YWVmNjlmNyIsInVzZXJfaWQiOjc4fQ.oJHKxtpqXwLo5NAsRYuyqb4FTbOVe5cOLOPTvyz78As';
    const headers = {
        Authorization: "Bearer " + token
    };
    console.log(headers);

    const wsclient = new sock.w3cwebsocket(
        'wss://' + 'zeem.xyz:4000'+ '/?companion=2' ,
        '',
        '',
        headers,
        null
    );
    wsclient.onerror = function () {
        console.log('Connection Error');
    };

    wsclient.onopen = function () {
        console.log('W3C WebSocket Client Connected');
    };
    function send() {
        wsclient.send(JSON.stringify({
            "type": "message",
            "text": "hello"
        }));
    }
    wsclient.onclose = function () {
        console.log('W3C WebSocket Client Disconnected');
    };

    wsclient.onmessage = function (e) {
        // Occasionally, the Direct Line service sends an empty message as a liveness ping
        // Ignore these messages
        console.log('Received: ' + e.data);
    };

</script>


sign up

<button on:click={send}>send</button>
