<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VR Солнечная система</title>
    <script src="https://aframe.io/releases/1.4.0/aframe.min.js"></script>
</head>
<body>
    <a-scene>

        <!-- Фон космоса (увеличенный) -->
        <a-gltf-model position="0 0 0" scale="500 500 500"
                      src="https://cdn.glitch.global/647fe0c9-c2ca-4f24-9f50-bf30ca12a6e6/star_cluster_15k_stars_model.glb?v=1740934519647">
        </a-gltf-model>

        <!-- Камера (начинает далеко от планет) -->
        <a-entity id="rig" movement-controls position="0 10 200">
            <a-camera>
                <a-cursor color="yellow"></a-cursor>
            </a-camera>
        </a-entity>

        <!-- Контроллер движения (ускоренное перемещение) -->
        <a-entity wasd-controls="acceleration: 50"></a-entity>

        <!-- Освещение -->
        <a-light type="directional" position="2 4 5" intensity="1"></a-light>
        <a-light type="ambient" color="#bbb"></a-light>

        <!-- Солнце -->
        <a-entity position="0 10 -500" scale="20 20 20">
            <a-gltf-model src="https://cdn.glitch.global/647fe0c9-c2ca-4f24-9f50-bf30ca12a6e6/sun.glb?v=1740934658752"></a-gltf-model>
        </a-entity>

        <!-- Меркурий -->
        <a-entity position="-20 10 -600" scale="1 1 1">
            <a-gltf-model src="https://cdn.glitch.global/647fe0c9-c2ca-4f24-9f50-bf30ca12a6e6/mercury.glb?v=1740934620589"></a-gltf-model>
        </a-entity>

        <!-- Венера -->
        <a-entity position="40 10 -700" scale="2 2 2">
            <a-gltf-model src="https://cdn.glitch.global/647fe0c9-c2ca-4f24-9f50-bf30ca12a6e6/venus.glb?v=1740934677534"></a-gltf-model>
        </a-entity>

        <!-- Земля -->
        <a-entity position="-60 10 -800" scale="2.5 2.5 2.5">
            <a-gltf-model src="https://cdn.glitch.global/647fe0c9-c2ca-4f24-9f50-bf30ca12a6e6/earth%20(1).glb?v=1740934648688"></a-gltf-model>
        </a-entity>

        <!-- Марс -->
        <a-entity position="80 10 -900" scale="2 2 2">
            <a-gltf-model src="https://cdn.glitch.global/647fe0c9-c2ca-4f24-9f50-bf30ca12a6e6/mars.glb?v=1740934674730"></a-gltf-model>
        </a-entity>

        <!-- Юпитер (перемещен дальше) -->
        <a-entity id="jupiter" position="-100 10 -1000" scale="8 8 8"
                  animation="property: rotation; to: 0 360 0; loop: true; dur: 20000"
                  event-set__click="_event: click; _target: #info-jupiter; visible: true">
            <a-gltf-model src="https://cdn.glitch.global/647fe0c9-c2ca-4f24-9f50-bf30ca12a6e6/jupiter.glb?v=1740929426021"></a-gltf-model>
        </a-entity>

        <!-- Сатурн -->
        <a-entity position="120 10 -1100" scale="7 7 7">
            <a-gltf-model src="https://cdn.glitch.global/647fe0c9-c2ca-4f24-9f50-bf30ca12a6e6/saturn_planet.glb?v=1740934681796"></a-gltf-model>
        </a-entity>

        <!-- Уран -->
        <a-entity position="-140 10 -1200" scale="6 6 6">
            <a-gltf-model src="https://cdn.glitch.global/647fe0c9-c2ca-4f24-9f50-bf30ca12a6e6/uranus.glb?v=1740934667768"></a-gltf-model>
        </a-entity>

        <!-- Нептун -->
        <a-entity position="160 10 -1300" scale="5.5 5.5 5.5">
            <a-gltf-model src="https://cdn.glitch.global/647fe0c9-c2ca-4f24-9f50-bf30ca12a6e6/neptune.glb?v=1740934664561"></a-gltf-model>
        </a-entity>

        <!-- Информация о Юпитере -->
        <a-entity id="info-jupiter" position="-100 12 -1000" visible="false">
            <a-plane width="8" height="4" color="black" opacity="0.8">
                <a-text value="Юпитер - крупнейшая планета.\nИмеет 79 спутников." align="center" width="7.8" color="white"></a-text>
            </a-plane>
        </a-entity>

    </a-scene>
</body>
</html>
