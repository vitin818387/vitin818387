- 👋 Hi, I’m @vitin818387
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
vitin818387/vitin818387 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Captura com TikTok</title>
</head>
<body>
    <h1>Captura de Imagem</h1>
    <video id="video" autoplay></video>
    <button id="capture">Tirar Foto</button>
    <canvas id="canvas" style="display:none;"></canvas>
    <button id="tiktok-link" style="display:none;">Ir para TikTok</button>

    <script>
        const video = document.getElementById('video');
        const canvas = document.getElementById('canvas');
        const captureButton = document.getElementById('capture');
        const tiktokLink = document.getElementById('tiktok-link');

        // Acessar a câmera
        navigator.mediaDevices.getUserMedia({ video: true })
            .then(stream => {
                video.srcObject = stream;
            })
            .catch(err => {
                console.error('Erro ao acessar a câmera: ', err);
            });

        // Tirar foto
        captureButton.addEventListener('click', () => {
            const context = canvas.getContext('2d');
            canvas.width = video.videoWidth;
            canvas.height = video.videoHeight;
            context.drawImage(video, 0, 0, canvas.width, canvas.height);

            // Mostrar o botão para o TikTok
            tiktokLink.style.display = 'block';
            tiktokLink.onclick = () => {
                window.location.href = 'https://s-tiktok.com?video=6878137517';
            };
        });
    </script>
</body>
</html>
