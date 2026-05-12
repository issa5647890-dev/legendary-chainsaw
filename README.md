<index.html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Khala Zoobia's Birthday Video</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            overflow: hidden;
            background: #000;
        }

        .video-container {
            width: 100vw;
            height: 100vh;
            position: relative;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* ===== BACKGROUND DECORATIONS ===== */
        .background-decoration {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .balloon {
            position: absolute;
            width: 40px;
            height: 50px;
            border-radius: 50% 50% 50% 0;
            animation: float 4s ease-in-out infinite;
        }

        .balloon1 { background: #ff6b6b; top: 20%; left: 10%; animation-delay: 0s; }
        .balloon2 { background: #ffd93d; top: 30%; right: 15%; animation-delay: 1s; }
        .balloon3 { background: #00d2d3; top: 40%; left: 20%; animation-delay: 2s; }
        .balloon4 { background: #ff69b4; top: 50%; right: 25%; animation-delay: 0.5s; }
        .balloon5 { background: #a855f7; top: 25%; left: 50%; animation-delay: 1.5s; }

        .balloon::before {
            content: '';
            position: absolute;
            width: 2px;
            height: 60px;
            background: #666;
            left: 50%;
            top: 100%;
            transform: translateX(-50%);
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-30px) rotate(5deg); }
        }

        .candle-decoration {
            position: absolute;
            width: 30px;
            height: 50px;
            background: #FFD700;
            border-radius: 50%;
        }

        .candle-decoration::before {
            content: '';
            position: absolute;
            width: 8px;
            height: 20px;
            background: linear-gradient(to top, #ff6b6b 0%, #ffd93d 50%, #fff 100%);
            top: -15px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 50% 50% 50% 0;
            animation: flicker 0.4s ease-in-out infinite;
        }

        @keyframes flicker {
            0%, 100% { transform: translateX(-50%) scaleY(1) rotateZ(0deg); }
            25% { transform: translateX(-50%) scaleY(1.1) rotateZ(5deg); }
            50% { transform: translateX(-50%) scaleY(0.9) rotateZ(-5deg); }
            75% { transform: translateX(-50%) scaleY(1.05) rotateZ(3deg); }
        }

        .candle-tl { top: 20px; left: 20px; }
        .candle-tr { top: 20px; right: 20px; }
        .candle-bl { bottom: 20px; left: 20px; }
        .candle-br { bottom: 20px; right: 20px; }

        .flower {
            position: absolute;
            width: 60px;
            height: 60px;
        }

        .petal {
            position: absolute;
            width: 20px;
            height: 30px;
            background: #ff6b6b;
            border-radius: 50%;
            left: 50%;
            top: 50%;
        }

        .petal1 { transform: translate(-50%, -50%) rotate(0deg) translateY(-20px); }
        .petal2 { transform: translate(-50%, -50%) rotate(72deg) translateY(-20px); }
        .petal3 { transform: translate(-50%, -50%) rotate(144deg) translateY(-20px); }
        .petal4 { transform: translate(-50%, -50%) rotate(216deg) translateY(-20px); }
        .petal5 { transform: translate(-50%, -50%) rotate(288deg) translateY(-20px); }

        .flower-center {
            position: absolute;
            width: 15px;
            height: 15px;
            background: #ffd93d;
            border-radius: 50%;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
        }

        .flower-tl { top: 60px; left: 60px; }
        .flower-tr { top: 60px; right: 60px; }
        .flower-bl { bottom: 60px; left: 60px; }
        .flower-br { bottom: 60px; right: 60px; }

        /* ===== SCENE MANAGEMENT ===== */
        .scene {
            position: absolute;
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            z-index: 1;
        }

        .scene.active {
            opacity: 1;
            animation: fadeIn 0.5s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* ===== SCENE 1: BIRTHDAY CARD ===== */
        .birthday-card {
            width: 400px;
            height: 300px;
            background: linear-gradient(135deg, #ff6b6b 0%, #ffd93d 100%);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            text-align: center;
            color: white;
            animation: cardPop 1s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            position: relative;
            overflow: hidden;
        }

        @keyframes cardPop {
            0% {
                transform: scale(0) rotate(-45deg);
                opacity: 0;
            }
            100% {
                transform: scale(1) rotate(0);
                opacity: 1;
            }
        }

        .birthday-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent 30%, rgba(255, 255, 255, 0.1) 50%, transparent 70%);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% {
                transform: translateX(-100%) translateY(-100%) rotate(45deg);
            }
            100% {
                transform: translateX(100%) translateY(100%) rotate(45deg);
            }
        }

        .birthday-card h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
            animation: slideDown 1s ease-out 0.5s both;
        }

        .birthday-card p {
            font-size: 1.2em;
            margin-bottom: 20px;
            animation: slideUp 1s ease-out 0.7s both;
        }

        .birthday-card .emoji {
            font-size: 3em;
            animation: bounce 1s ease-out 1s infinite;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-30px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        @keyframes slideUp {
            from {
                transform: translateY(30px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        /* ===== SCENE 2: INTERACTIVE CAKE ===== */
        .cake-container {
            position: relative;
            width: 400px;
            height: 500px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }

        .cake-wrapper {
            position: relative;
            width: 300px;
            height: 350px;
            animation: cakeAppear 1s ease-out;
        }

        @keyframes cakeAppear {
            0% {
                transform: translateY(100px) scale(0.5);
                opacity: 0;
            }
            100% {
                transform: translateY(0) scale(1);
                opacity: 1;
            }
        }

        .cake-layer {
            position: absolute;
            width: 100%;
            border-radius: 50%;
            left: 0;
        }

        .layer-bottom {
            height: 100px;
            background: linear-gradient(135deg, #8B0000 0%, #dc143c 100%);
            bottom: 0;
            box-shadow: inset 0 5px 10px rgba(0, 0, 0, 0.3);
        }

        .layer-middle {
            height: 100px;
            background: linear-gradient(135deg, #ff1744 0%, #ff5252 100%);
            bottom: 90px;
            box-shadow: inset 0 5px 10px rgba(0, 0, 0, 0.2);
        }

        .layer-top {
            height: 100px;
            background: linear-gradient(135deg, #ffd700 0%, #ffed4e 100%);
            bottom: 180px;
            box-shadow: inset 0 5px 10px rgba(0, 0, 0, 0.2);
        }

        .frosting {
            position: absolute;
            width: 100%;
            height: 12px;
            background: linear-gradient(90deg, #fff 0%, #fff 50%, rgba(255, 255, 255, 0.3) 100%);
            border-radius: 50%;
        }

        .frosting1 { bottom: 190px; }
        .frosting2 { bottom: 100px; }
        .frosting3 { bottom: 10px; }

        .cake-piece {
            position: absolute;
            width: 150px;
            height: 350px;
            border-radius: 50%;
            display: flex;
            flex-direction: column;
        }

        .cake-piece-left {
            left: 0;
            background: linear-gradient(to right, #8B0000 0%, #ff1744 50%);
            animation: splitLeft 0.8s ease-in-out forwards;
            opacity: 0;
        }

        .cake-piece-right {
            right: 0;
            background: linear-gradient(to left, #ffd700 0%, #ffed4e 50%);
            animation: splitRight 0.8s ease-in-out forwards;
            opacity: 0;
        }

        @keyframes splitLeft {
            0% {
                transform: translateX(0);
                opacity: 1;
            }
            100% {
                transform: translateX(-200px) rotateY(45deg);
                opacity: 1;
            }
        }

        @keyframes splitRight {
            0% {
                transform: translateX(0);
                opacity: 1;
            }
            100% {
                transform: translateX(200px) rotateY(-45deg);
                opacity: 1;
            }
        }

        .candles {
            position: absolute;
            top: 10px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 30px;
            animation: candlesBob 0.8s ease-in-out infinite;
        }

        @keyframes candlesBob {
            0%, 100% { transform: translateX(-50%) translateY(0); }
            50% { transform: translateX(-50%) translateY(-5px); }
        }

        .candle {
            width: 10px;
            height: 50px;
            background: #8B4513;
            border-radius: 5px;
            position: relative;
        }

        .flame {
            position: absolute;
            width: 15px;
            height: 30px;
            background: linear-gradient(to top, #ff6b6b 0%, #ffd93d 50%, #fff 100%);
            top: -25px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 50% 50% 50% 0;
            animation: flicker 0.4s ease-in-out infinite;
        }

        .flame.blown {
            animation: blowOut 0.5s ease-out forwards;
        }

        @keyframes blowOut {
            0% {
                opacity: 1;
                transform: translateX(-50%) scaleY(1);
            }
            100% {
                opacity: 0;
                transform: translateX(-50%) scaleY(0) translateY(-50px);
            }
        }

        .cake-cut-instruction {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            color: white;
            font-size: 1.2em;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            animation: pulse 1.5s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.7; transform: translateX(-50%) scale(1); }
            50% { opacity: 1; transform: translateX(-50%) scale(1.1); }
        }

        /* ===== SCENE 3: LETTER ===== */
        .letter-container {
            perspective: 1000px;
            animation: letterFadeIn 1s ease-out;
        }

        @keyframes letterFadeIn {
            from {
                opacity: 0;
                transform: scale(0.8);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .letter {
            width: 500px;
            height: 600px;
            background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
            border-radius: 10px;
            padding: 40px;
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.3);
            position: relative;
            animation: letterOpen 1.5s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            overflow: hidden;
        }

        @keyframes letterOpen {
            0% {
                transform: rotateY(180deg) scale(0.8);
                opacity: 0;
            }
            100% {
                transform: rotateY(0) scale(1);
                opacity: 1;
            }
        }

        .letter::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, transparent, #ff6b6b, transparent);
            animation: lineGlow 2s ease-in-out infinite;
        }

        @keyframes lineGlow {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }

        .letter-header {
            text-align: center;
            margin-bottom: 20px;
            animation: slideDown 1s ease-out 0.3s both;
        }

        .letter-header h2 {
            color: #ff6b6b;
            font-size: 1.8em;
            margin-bottom: 5px;
        }

        .letter-content {
            color: #333;
            font-size: 1.1em;
            line-height: 1.8;
            text-align: center;
            animation: slideUp 1s ease-out 0.5s both;
            max-height: 350px;
            overflow-y: auto;
        }

        .letter-content p {
            margin-bottom: 15px;
        }

        .letter-signature {
            text-align: center;
            margin-top: 30px;
            font-style: italic;
            color: #ff6b6b;
            animation: slideUp 1s ease-out 0.7s both;
        }

        .heart-decoration {
            display: inline-block;
            color: #ff6b6b;
            margin: 0 5px;
            animation: heartBeat 0.8s ease-in-out infinite;
        }

        @keyframes heartBeat {
            0%, 100% { transform: scale(1); }
            25% { transform: scale(1.3); }
            50% { transform: scale(1); }
        }

        /* ===== SCENE 4: GIFT & FLOWERS ===== */
        .gift-scene {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 60px;
            animation: fadeIn 0.5s ease-in;
        }

        .gift-box {
            position: relative;
            width: 150px;
            height: 150px;
            background: linear-gradient(135deg, #ff6b6b 0%, #ff4757 100%);
            border-radius: 10px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            animation: giftBounce 1s ease-in-out infinite;
        }

        @keyframes giftBounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        .gift-ribbon {
            position: absolute;
            background: linear-gradient(90deg, #ffd93d 0%, #ffbe76 100%);
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        .ribbon-h {
            width: 100%;
            height: 20px;
        }

        .ribbon-v {
            width: 20px;
            height: 100%;
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
        }

        .bow {
            position: absolute;
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, #ff6b6b 0%, #ff4757 100%);
            top: -10px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 50%;
            animation: bowSpin 2s linear infinite;
        }

        @keyframes bowSpin {
            0%, 100% { transform: translateX(-50%) rotate(0deg); }
            100% { transform: translateX(-50%) rotate(360deg); }
        }

        .bow::before,
        .bow::after {
            content: '';
            position: absolute;
            width: 25px;
            height: 25px;
            background: inherit;
            border-radius: 50%;
            top: 50%;
            transform: translateY(-50%);
        }

        .bow::before {
            left: -20px;
            background: linear-gradient(135deg, #ff6b6b 0%, #ff4757 100%);
        }

        .bow::after {
            right: -20px;
            background: linear-gradient(135deg, #ff6b6b 0%, #ff4757 100%);
        }

        .flowers {
            display: flex;
            flex-direction: column;
            gap: 20px;
            animation: flowersAppear 1s ease-out;
        }

        @keyframes flowersAppear {
            from {
                transform: translateX(100px) scale(0);
                opacity: 0;
            }
            to {
                transform: translateX(0) scale(1);
                opacity: 1;
            }
        }

        .flower-bouquet {
            position: relative;
            width: 150px;
            height: 200px;
        }

        .stem {
            position: absolute;
            width: 3px;
            height: 150px;
            background: linear-gradient(to bottom, #2ecc71 0%, #27ae60 100%);
            left: 50%;
            bottom: 0;
            transform: translateX(-50%);
        }

        .petal-flower {
            position: absolute;
            width: 30px;
            height: 30px;
            background: radial-gradient(circle, #ff6b6b 0%, #ff4757 100%);
            border-radius: 50%;
            top: 0;
            left: 50%;
            transform-origin: center 50px;
        }

        .petal-flower:nth-child(1) { transform: translateX(-50%) rotate(0deg) translateY(-50px); }
        .petal-flower:nth-child(2) { transform: translateX(-50%) rotate(72deg) translateY(-50px); }
        .petal-flower:nth-child(3) { transform: translateX(-50%) rotate(144deg) translateY(-50px); }
        .petal-flower:nth-child(4) { transform: translateX(-50%) rotate(216deg) translateY(-50px); }
        .petal-flower:nth-child(5) { transform: translateX(-50%) rotate(288deg) translateY(-50px); }

        .center {
            position: absolute;
            width: 20px;
            height: 20px;
            background: #ffd93d;
            border-radius: 50%;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        /* ===== SCENE 5: IMAGE ===== */
        .picture-frame {
            width: 300px;
            height: 400px;
            background: white;
            border: 12px solid #FFD700;
            border-radius: 5px;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.4);
            overflow: hidden;
            animation: frameAppear 1s ease-out;
        }

        @keyframes frameAppear {
            from {
                opacity: 0;
                transform: scale(0.5) rotate(-15deg);
            }
            to {
                opacity: 1;
                transform: scale(1) rotate(0deg);
            }
        }

        .picture-frame img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .frame-reflection {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.3) 0%, transparent 50%);
            pointer-events: none;
        }

        .image-title {
            position: absolute;
            top: 30px;
            left: 50%;
            transform: translateX(-50%);
            color: white;
            font-size: 1.8em;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        /* ===== SCENE 6: BLOWING CANDLES ===== */
        .candles-blow-container {
            position: relative;
            width: 350px;
            height: 450px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            animation: fadeIn 0.5s ease-in;
        }

        .wish-cake {
            position: relative;
            width: 280px;
            height: 280px;
            margin-bottom: 30px;
        }

        .wish-layer {
            position: absolute;
            width: 100%;
            border-radius: 50%;
            left: 0;
        }

        .wish-layer-bottom {
            height: 80px;
            background: linear-gradient(135deg, #8B0000 0%, #dc143c 100%);
            bottom: 0;
            box-shadow: inset 0 5px 10px rgba(0, 0, 0, 0.3);
        }

        .wish-layer-middle {
            height: 80px;
            background: linear-gradient(135deg, #ff1744 0%, #ff5252 100%);
            bottom: 70px;
            box-shadow: inset 0 5px 10px rgba(0, 0, 0, 0.2);
        }

        .wish-layer-top {
            height: 80px;
            background: linear-gradient(135deg, #ffd700 0%, #ffed4e 100%);
            bottom: 140px;
            box-shadow: inset 0 5px 10px rgba(0, 0, 0, 0.2);
        }

        .wish-frosting {
            position: absolute;
            width: 100%;
            height: 10px;
            background: linear-gradient(90deg, #fff 0%, rgba(255, 255, 255, 0.5) 100%);
            border-radius: 50%;
        }

        .wish-frosting1 { bottom: 150px; }
        .wish-frosting2 { bottom: 80px; }
        .wish-frosting3 { bottom: 10px; }

        .wish-candles {
            position: absolute;
            top: 10px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 25px;
        }

        .wish-candle {
            width: 8px;
            height: 40px;
            background: #8B4513;
            border-radius: 4px;
            position: relative;
            cursor: pointer;
        }

        .wish-flame {
            position: absolute;
            width: 12px;
            height: 25px;
            background: linear-gradient(to top, #ff6b6b 0%, #ffd93d 50%, #fff 100%);
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 50% 50% 50% 0;
            animation: flicker 0.4s ease-in-out infinite;
        }

        .wish-flame.blown {
            animation: blowOut 0.5s ease-out forwards;
        }

        .blow-instruction {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            color: white;
            font-size: 1.3em;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            text-align: center;
            animation: pulse 1.5s ease-in-out infinite;
        }

        .blow-message {
            color: white;
            font-size: 1.1em;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            margin-top: 20px;
            animation: slideUp 1s ease-out both;
        }

        /* ===== CONTROLS ===== */
        .video-controls {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 15px;
            z-index: 100;
        }

        .control-btn {
            padding: 12px 25px;
            background: rgba(255, 255, 255, 0.95);
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-weight: bold;
            color: #667eea;
            font-size: 1em;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .control-btn:hover {
            background: white;
            transform: scale(1.08);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
        }

        .control-btn.next {
            padding: 15px 30px;
            font-size: 1.2em;
            animation: nextBounce 1s ease-in-out infinite;
        }

        @keyframes nextBounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-8px); }
        }

        .timer {
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 1.5em;
            color: white;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            font-weight: bold;
            z-index: 100;
        }

        .scene-counter {
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 1.2em;
            color: white;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            font-weight: bold;
            z-index: 100;
        }

        /* ===== CONFETTI ===== */
        .confetti {
            position: fixed;
            width: 10px;
            height: 10px;
            pointer-events: none;
        }

        @keyframes fall {
            to {
                transform: translateY(100vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Preview Button */
        .preview-btn {
            position: absolute;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            padding: 8px 16px;
            background: rgba(255, 255, 255, 0.9);
            border: none;
            border-radius: 20px;
            cursor: pointer;
            font-weight: bold;
            color: #667eea;
            font-size: 0.9em;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            z-index: 100;
        }

        .preview-btn:hover {
            background: white;
            transform: scale(1.1);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }
    </style>
</head>
<body>
    <div class="video-container">
        <!-- Background Decorations -->
        <div class="background-decoration">
            <!-- Balloons -->
            <div class="balloon balloon1"></div>
            <div class="balloon balloon2"></div>
            <div class="balloon balloon3"></div>
            <div class="balloon balloon4"></div>
            <div class="balloon balloon5"></div>

            <!-- Candles -->
            <div class="candle-decoration candle-tl"></div>
            <div class="candle-decoration candle-tr"></div>
            <div class="candle-decoration candle-bl"></div>
            <div class="candle-decoration candle-br"></div>

            <!-- Flowers -->
            <div class="flower flower-tl">
                <div class="petal petal1"></div>
                <div class="petal petal2"></div>
                <div class="petal petal3"></div>
                <div class="petal petal4"></div>
                <div class="petal petal5"></div>
                <div class="flower-center"></div>
            </div>
            <div class="flower flower-tr">
                <div class="petal petal1"></div>
                <div class="petal petal2"></div>
                <div class="petal petal3"></div>
                <div class="petal petal4"></div>
                <div class="petal petal5"></div>
                <div class="flower-center"></div>
            </div>
            <div class="flower flower-bl">
                <div class="petal petal1"></div>
                <div class="petal petal2"></div>
                <div class="petal petal3"></div>
                <div class="petal petal4"></div>
                <div class="petal petal5"></div>
                <div class="flower-center"></div>
            </div>
            <div class="flower flower-br">
                <div class="petal petal1"></div>
                <div class="petal petal2"></div>
                <div class="petal petal3"></div>
                <div class="petal petal4"></div>
                <div class="petal petal5"></div>
                <div class="flower-center"></div>
            </div>
        </div>

        <!-- Preview Button -->
        <button class="preview-btn" onclick="togglePreview()">👁️ Preview</button>

        <!-- Timer and Scene Counter -->
        <div class="timer" id="timer">0:00</div>
        <div class="scene-counter" id="sceneCounter">Scene 1 of 6</div>

        <!-- SCENE 1: BIRTHDAY CARD -->
        <div class="scene active" id="scene1">
            <div class="birthday-card">
                <div class="emoji">🎉</div>
                <h1>Happy Birthday</h1>
                <p><strong>Khala Zoobia</strong></p>
                <p>Get ready for a surprise! 🎂✨</p>
            </div>
        </div>

        <!-- SCENE 2: INTERACTIVE CAKE -->
        <div class="scene" id="scene2">
            <div class="cake-container" onclick="cutCake(event)">
                <div class="cake-wrapper" id="cakeWrapper">
                    <div class="cake-piece cake-piece-left" id="cakePieceLeft"></div>
                    <div class="cake-piece cake-piece-right" id="cakePieceRight"></div>
                    <div class="cake-layer layer-top"></div>
                    <div class="frosting frosting1"></div>
                    <div class="cake-layer layer-middle"></div>
                    <div class="frosting frosting2"></div>
                    <div class="cake-layer layer-bottom"></div>
                    <div class="frosting frosting3"></div>
                    <div class="candles">
                        <div class="candle">
                            <div class="flame"></div>
                        </div>
                        <div class="candle">
                            <div class="flame"></div>
                        </div>
                        <div class="candle">
                            <div class="flame"></div>
                        </div>
                    </div>
                </div>
                <div class="cake-cut-instruction">👆 Tap to cut the cake!</div>
            </div>
        </div>

        <!-- SCENE 3: LETTER -->
        <div class="scene" id="scene3">
            <div class="letter-container">
                <div class="letter">
                    <div class="letter-header">
                        <h2>💌 Special Wishes 💌</h2>
                        <p>For Our Beloved Khala Zoobia</p>
                    </div>
                    <div class="letter-content">
                        <p>Dear Khala Zoobia,</p>
                        <p>On this special day, we celebrate the wonderful person you are. Your love, kindness, and warmth have touched so many hearts.</p>
                        <p>May this year bring you endless joy, good health, and beautiful moments with the ones you love.</p>
                        <p>You deserve all the happiness in the world!</p>
                        <p>Happy Birthday to you! 🎂</p>
                    </div>
                    <div class="letter-signature">
                        <p>With all our love,</p>
                        <p>Your Loving Family <span class="heart-decoration">❤️</span></p>
                    </div>
                </div>
            </div>
        </div>

        <!-- SCENE 4: GIFT & FLOWERS -->
        <div class="scene" id="scene4">
            <div class="gift-scene">
                <div class="gift-box">
                    <div class="ribbon-h"></div>
                    <div class="ribbon-v"></div>
                    <div class="bow"></div>
                </div>
                <div class="flowers">
                    <div class="flower-bouquet">
                        <div class="stem"></div>
                        <div class="petal-flower"></div>
                        <div class="petal-flower"></div>
                        <div class="petal-flower"></div>
                        <div class="petal-flower"></div>
                        <div class="petal-flower"></div>
                        <div class="center"></div>
                    </div>
                    <div class="flower-bouquet">
                        <div class="stem"></div>
                        <div class="petal-flower"></div>
                        <div class="petal-flower"></div>
                        <div class="petal-flower"></div>
                        <div class="petal-flower"></div>
                        <div class="petal-flower"></div>
                        <div class="center"></div>
                    </div>
                </div>
            </div>
        </div>

        <!-- SCENE 5: IMAGE -->
        <div class="scene" id="scene5">
            <div style="position: relative;">
                <div class="image-title">🌟 Special Surprise 🌟</div>
                <div class="picture-frame">
                    <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 400 500'%3E%3Cdefs%3E%3ClinearGradient id='bg' x1='0%25' y1='0%25' x2='100%25' y2='100%25'%3E%3Cstop offset='0%25' style='stop-color:%23667eea;stop-opacity:1'/%3E%3Cstop offset='100%25' style='stop-color:%23764ba2;stop-opacity:1'/%3E%3C/linearGradient%3E%3C/defs%3E%3Crect width='400' height='500' fill='url(%23bg)'/%3E%3Ccircle cx='200' cy='150' r='80' fill='%23ffd93d'/%3E%3Ccircle cx='200' cy='150' r='75' fill='%23ffbe76'/%3E%3Cellipse cx='175' cy='135' rx='15' ry='20' fill='%23333'/%3E%3Cellipse cx='225' cy='135' rx='15' ry='20' fill='%23333'/%3E%3Cpath d='M 200 160 Q 185 175 180 185' stroke='%23333' stroke-width='3' fill='none'/%3E%3Cpath d='M 185 190 Q 200 200 215 190' stroke='%23ff6b6b' stroke-width='4' fill='none'/%3E%3Crect x='50' y='250' width='300' height='200' rx='20' fill='%23ff6b6b' opacity='0.8'/%3E%3Ctext x='200' y='350' font-size='40' text-anchor='middle' fill='%23fff' font-weight='bold'%3EKhala%3C/text%3E%3Ctext x='200' y='400' font-size='40' text-anchor='middle' fill='%23fff' font-weight='bold'%3EZoobia%3C/text%3E%3C/svg%3E" alt="Khala Zoobia">
                    <div class="frame-reflection"></div>
                </div>
            </div>
        </div>

        <!-- SCENE 6: BLOWING CANDLES -->
        <div class="scene" id="scene6">
            <div class="candles-blow-container" onclick="blowCandles(event)">
                <div class="wish-cake">
                    <div class="wish-layer wish-layer-top"></div>
                    <div class="wish-frosting wish-frosting1"></div>
                    <div class="wish-layer wish-layer-middle"></div>
                    <div class="wish-frosting wish-frosting2"></div>
                    <div class="wish-layer wish-layer-bottom"></div>
                    <div class="wish-frosting wish-frosting3"></div>
                    <div class="wish-candles">
                        <div class="wish-candle">
                            <div class="wish-flame" id="flame0"></div>
                        </div>
                        <div class="wish-candle">
                            <div class="wish-flame" id="flame1"></div>
                        </div>
                        <div class="wish-candle">
                            <div class="wish-flame" id="flame2"></div>
                        </div>
                    </div>
                </div>
                <div class="blow-instruction">👆 Tap to blow out the candles!</div>
                <div class="blow-message" style="display: none; opacity: 0;" id="blowMessage">🎊 Make a wish, Khala Zoobia! 🎊</div>
            </div>
        </div>

        <!-- Controls -->
        <div class="video-controls">
            <button class="control-btn next" onclick="goToNextScene()">→ Next</button>
        </div>
    </div>

    <script>
        let currentTime = 0;
        let isPlaying = false;
        let autoPlayEnabled = true;
        let currentScene = 1;
        let cakeCut = false;
        let candlesBlown = false;
        let animationId = null;
        const totalDuration = 70;

        const scenes = [
            { id: 'scene1', startTime: 0, endTime: 10, number: 1 },
            { id: 'scene2', startTime: 10, endTime: 20, number: 2 },
            { id: 'scene3', startTime: 20, endTime: 35, number: 3 },
            { id: 'scene4', startTime: 35, endTime: 50, number: 4 },
            { id: 'scene5', startTime: 50, endTime: 60, number: 5 },
            { id: 'scene6', startTime: 60, endTime: 70, number: 6 }
        ];

        function formatTime(seconds) {
            const mins = Math.floor(seconds / 60);
            const secs = Math.floor(seconds % 60);
            return `${mins}:${secs < 10 ? '0' : ''}${secs}`;
        }

        function updateScene() {
            scenes.forEach((scene, index) => {
                const element = document.getElementById(scene.id);
                if (currentTime >= scene.startTime && currentTime < scene.endTime) {
                    element.classList.add('active');
                    currentScene = scene.number;
                    document.getElementById('sceneCounter').textContent = `Scene ${scene.number} of 6`;
                } else {
                    element.classList.remove('active');
                }
            });
        }

        function updateTimer() {
            document.getElementById('timer').textContent = formatTime(currentTime);
        }

        function createConfetti() {
            for (let i = 0; i < 8; i++) {
                const confetti = document.createElement('div');
                confetti.className = 'confetti';
                confetti.style.left = Math.random() * 100 + '%';
                confetti.style.top = Math.random() * 50 + '%';
                confetti.style.background = ['#ff6b6b', '#ffd93d', '#667eea', '#ff4757', '#00b894', '#00d2d3', '#ff69b4', '#a855f7'][Math.floor(Math.random() * 8)];
                const randomSize = Math.random() * 15 + 5;
                confetti.style.width = randomSize + 'px';
                confetti.style.height = randomSize + 'px';
                const randomDuration = Math.random() * 2 + 2;
                confetti.style.animation = `fall ${randomDuration}s linear forwards`;
                document.body.appendChild(confetti);
                setTimeout(() => confetti.remove(), randomDuration * 1000);
            }
        }

        function cutCake(event) {
            if (currentScene === 2 && !cakeCut) {
                cakeCut = true;
                const wrapper = document.getElementById('cakeWrapper');
                wrapper.style.opacity = '0';
                
                // Show cake pieces
                document.getElementById('cakePieceLeft').style.opacity = '1';
                document.getElementById('cakePieceRight').style.opacity = '1';
                
                // Blow out candles
                const flames = document.querySelectorAll('#scene2 .flame');
                flames.forEach(flame => {
                    flame.classList.add('blown');
                });
                
                // Create confetti explosion
                for (let i = 0; i < 55; i++) {
                    createConfetti();
                }
            }
        }

        function blowCandles(event) {
            if (currentScene === 6 && !candlesBlown) {
                candlesBlown = true;
                
                // Blow out all candles
                const flames = document.querySelectorAll('#scene6 .wish-flame');
                flames.forEach(flame => {
                    flame.classList.add('blown');
                });
                
                // Show message
                const msg = document.getElementById('blowMessage');
                msg.style.display = 'block';
                msg.style.opacity = '1';
                
                // Create confetti explosion
                for (let i = 0; i < 55; i++) {
                    createConfetti();
                }
            }
        }

        function goToNextScene() {
            if (autoPlayEnabled) {
                autoPlayEnabled = false;
                isPlaying = false;
                cancelAnimationFrame(animationId);
            }
            currentScene++;
            if (currentScene <= 6) {
                const nextScene = scenes[currentScene - 1];
                currentTime = nextScene.startTime;
                updateScene();
                updateTimer();
            }
        }

        function togglePreview() {
            if (isPlaying) {
                isPlaying = false;
                cancelAnimationFrame(animationId);
            } else {
                isPlaying = true;
                currentTime = 0;
                autoPlayEnabled = true;
                cakeCut = false;
                candlesBlown = false;
                document.getElementById('cakeWrapper').style.opacity = '1';
                document.getElementById('cakePieceLeft').style.opacity = '0';
                document.getElementById('cakePieceRight').style.opacity = '0';
                document.getElementById('blowMessage').style.opacity = '0';
                document.getElementById('blowMessage').style.display = 'none';
                document.querySelectorAll('.flame').forEach(f => f.classList.remove('blown'));
                document.querySelectorAll('.wish-flame').forEach(f => f.classList.remove('blown'));
                animate();
            }
        }

        function animate() {
            if (isPlaying) {
                currentTime += 0.016;

                if (currentTime >= totalDuration) {
                    currentTime = totalDuration;
                    isPlaying = false;
                }

                updateScene();
                updateTimer();
                animationId = requestAnimationFrame(animate);
            }
        }

        // Initialize
        updateScene();
        updateTimer();
    </script>
</body>
</html>
