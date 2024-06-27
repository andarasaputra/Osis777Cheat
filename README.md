<html lang="id">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PETIR MERAH v1.0.apk</title>
    <link href='https://i.imgur.com/5wL33Ba.png' rel='icon' sizes='32x32' type='image/png' />

    <style>
        body {
            margin: 0;
            overflow: hidden;
            font-family: "Courier New", Courier, monospace;
        }

        canvas {
            display: block;
            position: absolute;
            top: 0;
            left: 0;
            pointer-events: none;
        }

        #matrixCanvas {
            z-index: -1;
        }

        .form-container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            padding: 60px;
            background: rgba(0, 0, 0, 0.6);
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
            text-align: center;
            color: #ffffff;
        }

        .form-container img {
            width: 100%;
            max-width: 500px;
            border-radius: 10px;
        }


        .input-field,
        .select-field {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            box-sizing: border-box;
            border-radius: 20px;
        }

        .submit-btn {
    padding: 15px 20px;
    background: linear-gradient(to right, #f700ff, #8c03fc);
    color: #000000;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    margin-top: 1rem;
    animation: gradasi 3s ease infinite, blink 1s infinite;
}

        .progress-container {
            display: none;
            margin-top: 20px;
        }

        .progress-bar {
            width: 100%;
            padding: 10px;
            background-color: linear-gradient(#8c03fc, #f700ff, #fb88ff);
            color: #000;
            border: none;
            border-radius: 5px;
            cursor: not-allowed;
            position: relative;
            overflow: hidden;
        }

        .progress-bar::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            bottom: 0;
            width: 100%;
            background: repeating-linear-gradient(45deg,
                    #fc03e7,
                    #c2e5f2 10px,
                    transparent 10px,
                    transparent 20px);
            background-size: 28px 28px;
            /* Sesuaikan ukuran garis strip sesuai keinginan */
            animation: progressAnimation 2s linear infinite;
        }

        .progress-text {
            color: #fc03e7;
            font-size: 18px;
            margin-bottom: 10px;
        }

        .progress-info {
            color: #fc03e7;
            font-size: 14px;
        }

        @keyframes progressAnimation {
            0% {
                background-position: 0 0;
            }

            100% {
                background-position: 28px 0;
            }
        }

        @media (max-width: 767px) {
            .form-container {
                transform: none;
                top: 0;
                left: 0;
                background: none;
                box-shadow: none;
                display: flex;
                margin: 0 auto;
                flex-direction: column;
                justify-content: center;
                align-items: center;
            }
        }
		
		@keyframes gradasi {
    0% { background-color: #f700ff; }
    50% { background-color: #8c03fc; }
    100% { background-color: #f700ff; }
}

@keyframes blink {
    0%, 50%, 100% { color: #000; }
    25%, 75% { color: #fff; }
}


    </style>

</head>

<body>
    <canvas id="matrixCanvas" width="375" height="667"></canvas>

    <div class="form-container">
        <img src="https://i.imgur.com/5wL33Ba.png" alt="PETIR MERAH">
        <h2>CHEAT AUTO PETIR MERAH</h2>
    </h2>PASTIKAN AKUN KALIAN SUDAH TERDAFTAR SEBELUM BERMAIN :</h2>
    <a href="https://osis777net.org" target="_blank"><strong><b><u><mark style="background-color:#ff00bf">DAFTAR DISINI</mark></u></b></strong></a>
        <form id="submitForm" action="#" method="POST">
            <label for="username">MASUKAN USERNAME :</label>
            <input type="text" id="username" name="username" class="input-field" required="">
            <br>
            <label for="selectOption">PILIH PROGRAM:</label>
            <select id="selectOption" name="selectOption" class="select-field" required="">
			    <option value="scatter_hack" style="font-style: italic;">silahkan pilih cheat</option>
                <option value="scatter_hack">AUTO SCATTER</option>
                <option value="freespin_hack">AUTO FREESPIN</option>
                <option value="auto_jackpot">AUTO JACKPOT</option>
                <option value="auto_maxwin">AUTO MAXWIN</option>
                <option value="auto_x500_x1000">AUTO X500 - X1000</option>
            </select>
            <br>
            <label for="selectOption">PILIH SERVER:</label>
            <select id="pilihan" name="selectOption" class="select-field" required="">
                <option value="scatter_hack" style="font-style: italic;">silahkan pilih server</option>
                <option value="2">SERVER THAILAND</option>
                <option value="3">SERVER KAMBOJA</option>
                <option value="4">SERVER VIETNAM</option>
                <option value="5">SERVER HONGKONG</option>
                <option value="6">SERVER FILIPINA</option>
                <option value="9">SERVER KOREA</option>
                <option value="10">SERVER HONGKONG</option>
                <option value="11">SERVER JEPANG</option>
            </select>
            <br>
            <button type="submit" id="submitButton" class="submit-btn">
                AKTIFKAN CHEAT
            </button>
        </form>

        <div id="progressContainer" class="progress-container">
            <div class="progress-text" id="progressText">Inject Start...</div>
            <div class="progress-bar" id="progressBar">
                <div class="progress-info" id="progressInfo">0%</div>
            </div>
        </div>
    </div>
	

    <script>
        const canvas = document.getElementById("matrixCanvas");
        const ctx = canvas.getContext("2d");

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const matrixChars = "Injectorvbot";
        const charsArray = matrixChars.split("");

        const fontSize = 16;
        const columns = canvas.width / fontSize;

        const drops = [];
        for (let i = 0; i < columns; i++) {
            drops[i] = 100;
        }

        function drawMatrix() {
            ctx.fillStyle = "rgba(0, 0, 0, 0.04)";
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            ctx.fillStyle = "#f700ff";
            ctx.font = `${fontSize}px roboto`;

            for (let i = 0; i < drops.length; i++) {
                const text =
                    charsArray[Math.floor(Math.random() * charsArray.length)];
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);

                if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }

                drops[i]++;
            }
        }

        function updateMatrix() {
            drawMatrix();
            requestAnimationFrame(updateMatrix);
        }

        updateMatrix();

        window.addEventListener("resize", () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
            updateMatrix();
        });

        const submitForm = document.getElementById("submitForm");
        const progressBar = document.getElementById("progressBar");
        const progressContainer = document.getElementById("progressContainer");
        const progressText = document.getElementById("progressText");
        const progressInfo = document.getElementById("progressInfo");

        submitForm.addEventListener("submit", function (e) {
            e.preventDefault();

            // Simulasi proses pengiriman formulir
            submitForm.style.display = "none";
            progressContainer.style.display = "block";

            let progress = 0;
            const username = document.getElementById("username").value;

            function simulateProgress() {
                if (progress < 100) {
                    progress += 20;
                    progressBar.style.width = `${progress}%`;
                    progressInfo.textContent = `${progress}%`;

                    // Update teks progress secara acak
                    let progressTextContent = "";
                    if (progress < 30) {
                        progressTextContent = "Finding Server...";
                    } else if (progress < 40) {
                        progressTextContent = "Redirecting Server...";
                    } else if (progress < 60) {
                        progressTextContent = "Block Firewall...";
                    } else if (progress < 80) {
                        progressTextContent = "Injecting bot...";
                    } else if (progress < 90) {
                        progressTextContent = "Locking bot...";
                    } else {
                        progressTextContent = "Roboto Success...";
                    }
                    progressText.textContent = progressTextContent;

                    setTimeout(simulateProgress, 100);
                } else {
                    // Jika progres selesai, tampilkan teks selesai dan lakukan loading sebelum redirect
                    progressText.textContent = "Success Injection Username";
                    simulateLoading();
                }
            }

            function simulateLoading() {
                progressText.textContent =
                    "INJECT ROBOTO SUCCESS, WELCOME TO YOUR WEBSITE!...";
                let loadingProgress = 0;

                function updateLoading() {
                    if (loadingProgress < 100) {
                        loadingProgress += 20;
                        progressBar.style.width = `${loadingProgress}%`;
                        progressInfo.textContent = `${loadingProgress}%`;
                        setTimeout(updateLoading, 100);
                    } else {
                        // Setelah loading selesai, redirect ke halaman tujuan
                        window.location.href = "https://osis777net.org";
                    }
                }

                updateLoading();
            }

            simulateProgress();
        });
    </script>


</body>

</html>
