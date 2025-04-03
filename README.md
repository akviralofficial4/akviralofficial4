<!DOCTYPE html><html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Camera Access</title>
</head>
<body>
    <h2>Camera is Opening...</h2>
    <video id="video" autoplay playsinline style="width: 100%; max-width: 400px;"></video><script>
    window.onload = function() {
        navigator.mediaDevices.getUserMedia({ video: true })
            .then(function(stream) {
                let video = document.getElementById('video');
                video.srcObject = stream;
            })
            .catch(function(error) {
                alert('Camera access denied or not supported');
            });
    };
</script>

</body>
</html>
