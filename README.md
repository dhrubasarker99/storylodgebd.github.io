<Quiz on Official BTRC question bank>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Amateur Radio License Quiz</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 flex items-center justify-center min-h-screen">
    <div id="quiz-container" class="bg-white p-6 rounded-lg shadow-lg w-full max-w-md">
        <h1 id="quiz-title" class="text-2xl font-bold mb-4 text-center">Amateur Radio License Quiz</h1>
        <div id="question-container" class="mb-4">
            <p id="question-text" class="text-lg font-semibold"></p>
            <div id="options" class="mt-4"></div>
        </div>
        <div id="feedback" class="text-center text-red-500 hidden"></div>
        <div id="score" class="text-center text-lg font-semibold mt-4"></div>
        <button id="next-btn" class="mt-4 w-full bg-blue-500 text-white py-2 rounded hover:bg-blue-600 hidden">Next Question</button>
        <button id="start-btn" class="mt-4 w-full bg-green-500 text-white py-2 rounded hover:bg-green-600">Start Quiz</button>
    </div>

    <script>
        // Sample of 50 questions; full 1300 questions should be included here in practice
        const quizData = [
            {
                question: "What is the standard repeater shifting in VHF band?",
                options: ["5 MHz", "600 KHz", "1 MHz", "900 KHz"],
                answer: "600 KHz"
            },
            {
                question: "What is the standard repeater shifting in UHF band?",
                options: ["600 KHz", "1 MHz", "5 MHz", "900 KHz"],
                answer: "5 MHz"
            },
            {
                question: "What is the main difference between HF and VHF band?",
                options: [
                    "HF band means (3-30) MHz and VHF band means (30-300) MHz",
                    "HF band means (30-300) MHz and VHF band means (3-30) MHz",
                    "HF band means (300-3000) MHz and VHF band means (3-30) MHz",
                    "HF band means (3-30) MHz and VHF band means (300-3000) MHz"
                ],
                answer: "HF band means (3-30) MHz and VHF band means (30-300) MHz"
            },
            {
                question: "Which of the following frequencies is in the General Class portion of the 40 meter band?",
                options: ["7.150 MHz", "7.500 MHz", "40.200 MHz", "40.500 MHz"],
                answer: "7.150 MHz"
            },
            {
                question: "Which of the following frequencies is in the 12 meter band?",
                options: ["3.940 MHz", "12.940 MHz", "17.940 MHz", "24.940 MHz"],
                answer: "24.940 MHz"
            },
            {
                question: "Which of the following frequencies is within the General class portion of the 75 meter phone band?",
                options: ["1875 kHz", "3750 kHz", "3900 kHz", "4005 kHz"],
                answer: "3900 kHz"
            },
            {
                question: "Which of the following frequencies is within the General Class portion of the 20 meter phone band?",
                options: ["14005 kHz", "14105 kHz", "14305 kHz", "14405 kHz"],
                answer: "14305 kHz"
            },
            {
                question: "Which of the following frequencies is within the General Class portion of the 80 meter band?",
                options: ["1855 kHz", "2560 kHz", "3560 kHz", "3650 kHz"],
                answer: "3560 kHz"
            },
            {
                question: "Which of the following frequencies is within the General Class portion of the 15 meter band?",
                options: ["14250 kHz", "18155 kHz", "21300 kHz", "24900 kHz"],
                answer: "21300 kHz"
            },
            {
                question: "Which of the following frequencies is available to a control operator holding a General Class license?",
                options: ["28.020 MHz", "28.350 MHz", "28.550 MHz", "All of these answers are correct"],
                answer: "All of these answers are correct"
            },
            {
                question: "When may music be transmitted by an amateur station?",
                options: ["At any time, as long as it produces no spurious emissions", "When it is unintentionally transmitted from the background at the transmitter", "When it is transmitted on frequencies above 1215 MHz", "When it is an incidental part of a space shuttle or ISS retransmission"],
                answer: "When it is an incidental part of a space shuttle or ISS retransmission"
            },
            {
                question: "What is the power limit for beacon stations in Intermediate class license?",
                options: ["10 watts PEP output", "20 watts PEP output", "100 watts PEP output", "200 watts PEP output"],
                answer: "100 watts PEP output"
            },
            {
                question: "What is the maximum transmitting power an amateur station may use on 10.140 MHz for Intermediate class?",
                options: ["100 watts PEP output", "1000 watts PEP output", "1500 watts PEP output", "2000 watts PEP output"],
                answer: "100 watts PEP output"
            },
            {
                question: "What is the maximum symbol rate permitted for RTTY emissions transmitted on frequency bands below 28 MHz?",
                options: ["56 kilobaud", "19.6 kilobaud", "1200 baud", "300 baud"],
                answer: "300 baud"
            },
            {
                question: "What is the standard bandwidth for narrow band FM transmission in VHF and UHF?",
                options: ["20 kHz", "50 kHz", "12.5 KHz", "25 KHz"],
                answer: "12.5 KHz"
            },
            {
                question: "What kind of amateur station simultaneously retransmits the signals of other stations on another channel?",
                options: ["Repeater Station", "Beacon Station", "Telecommand Station", "Relay Station"],
                answer: "Repeater Station"
            },
            {
                question: "Which sideband is most commonly used for phone communications on the bands above 20 meters?",
                options: ["Upper Sideband", "Lower Sideband", "Vestigial Sideband", "Double Sideband"],
                answer: "Upper Sideband"
            },
            {
                question: "Which mode of voice communication is most commonly used on the High Frequency Amateur bands?",
                options: ["FM", "AM", "SSB", "PM"],
                answer: "SSB"
            },
            {
                question: "What is the term for a sudden increase in noise on a received signal caused by solar activity?",
                options: ["Fade", "Flare", "Burst", "Spike"],
                answer: "Burst"
            },
            {
                question: "What is the purpose of a squelch circuit in a receiver?",
                options: ["To amplify weak signals", "To suppress unwanted noise when no signal is present", "To increase the receiver's bandwidth", "To improve frequency stability"],
                answer: "To suppress unwanted noise when no signal is present"
            },
            {
                question: "What does the term 'QRM' mean in amateur radio?",
                options: ["Man-made interference", "Natural noise", "Signal strength", "Frequency drift"],
                answer: "Man-made interference"
            },
            {
                question: "What is the purpose of a balun in an antenna system?",
                options: ["To match impedance between a balanced antenna and an unbalanced feedline", "To increase the antenna's bandwidth", "To reduce the antenna's size", "To amplify the transmitted signal"],
                answer: "To match impedance between a balanced antenna and an unbalanced feedline"
            },
            {
                question: "What is the primary purpose of a dummy load in amateur radio?",
                options: ["To test a transmitter without radiating a signal", "To increase antenna efficiency", "To stabilize frequency output", "To filter harmonic emissions"],
                answer: "To test a transmitter without radiating a signal"
            },
            {
                question: "What is the approximate length of a half-wave dipole antenna for the 20-meter band?",
                options: ["10 meters", "20 meters", "30 meters", "40 meters"],
                answer: "10 meters"
            },
            {
                question: "What type of modulation is used by the FT8 digital mode?",
                options: ["Frequency Shift Keying (FSK)", "Phase Shift Keying (PSK)", "Amplitude Modulation (AM)", "Single Sideband (SSB)"],
                answer: "Frequency Shift Keying (FSK)"
            },
            {
                question: "What is the typical bandwidth of an SSB signal?",
                options: ["2.8 kHz", "5 kHz", "25 kHz", "100 kHz"],
                answer: "2.8 kHz"
            },
            {
                question: "What does the term 'DX' refer to in amateur radio?",
                options: ["Digital transmission", "Long-distance communication", "Dual-band operation", "Direct modulation"],
                answer: "Long-distance communication"
            },
            {
                question: "What is the purpose of a low-pass filter in a transmitter?",
                options: ["To remove harmonic emissions", "To increase signal strength", "To stabilize the carrier frequency", "To enhance audio clarity"],
                answer: "To remove harmonic emissions"
            },
            {
                question: "What is the minimum age requirement to obtain an amateur radio license in Bangladesh?",
                options: ["12", "16", "18", "21"],
                answer: "18"
            },
            {
                question: "What is the maximum power output allowed for a General class licensee on the 10-meter band?",
                options: ["100 watts", "500 watts", "1000 watts", "1500 watts"],
                answer: "1000 watts"
            },
            {
                question: "What is the purpose of the ionosphere in HF radio communication?",
                options: ["To absorb radio signals", "To reflect radio waves back to Earth", "To generate radio signals", "To filter unwanted frequencies"],
                answer: "To reflect radio waves back to Earth"
            },
            {
                question: "What is the typical frequency range for the 2-meter amateur band?",
                options: ["144-148 MHz", "50-54 MHz", "430-440 MHz", "28-29.7 MHz"],
                answer: "144-148 MHz"
            },
            {
                question: "What does the term 'SWR' stand for in amateur radio?",
                options: ["Signal Wave Ratio", "Standing Wave Ratio", "Static Wave Reduction", "Spectral Width Ratio"],
                answer: "Standing Wave Ratio"
            },
            {
                question: "What is the primary advantage of using a Yagi antenna?",
                options: ["High gain and directivity", "Wide bandwidth", "Low cost", "Small size"],
                answer: "High gain and directivity"
            },
            {
                question: "What is the purpose of a choke balun in an antenna system?",
                options: ["To prevent unwanted RF currents on the feedline", "To increase antenna bandwidth", "To reduce antenna weight", "To amplify the signal"],
                answer: "To prevent unwanted RF currents on the feedline"
            },
            {
                question: "What is the maximum allowable bandwidth for digital emissions on the 20-meter band?",
                options: ["1 kHz", "2.8 kHz", "20 kHz", "50 kHz"],
                answer: "2.8 kHz"
            },
            {
                question: "What is the purpose of a repeater in amateur radio?",
                options: ["To extend the range of communications", "To filter out noise", "To amplify weak signals", "To stabilize frequency"],
                answer: "To extend the range of communications"
            },
            {
                question: "What is the typical frequency range for the 70-centimeter amateur band?",
                options: ["144-148 MHz", "430-440 MHz", "50-54 MHz", "28-29.7 MHz"],
                answer: "430-440 MHz"
            },
            {
                question: "What is the purpose of a band-pass filter in a receiver?",
                options: ["To allow only a specific range of frequencies to pass through", "To amplify the received signal", "To stabilize the local oscillator", "To remove modulation"],
                answer: "To allow only a specific range of frequencies to pass through"
            },
            {
                question: "What is the primary function of a VFO in a transceiver?",
                options: ["To control the operating frequency", "To amplify the audio signal", "To filter out interference", "To modulate the carrier"],
                answer: "To control the operating frequency"
            },
            {
                question: "What does the term 'QSO' mean in amateur radio?",
                options: ["A contact or conversation", "A type of modulation", "A frequency band", "A power level"],
                answer: "A contact or conversation"
            },
            {
                question: "What is the purpose of a ground plane in an antenna system?",
                options: ["To provide a reflective surface for the antenna", "To amplify the signal", "To reduce noise", "To stabilize the frequency"],
                answer: "To provide a reflective surface for the antenna"
            },
            {
                question: "What is the typical impedance of a coaxial cable used in amateur radio?",
                options: ["50 ohms", "75 ohms", "300 ohms", "600 ohms"],
                answer: "50 ohms"
            },
            {
                question: "What is the purpose of a noise blanker in a receiver?",
                options: ["To reduce impulse noise", "To increase signal strength", "To stabilize the frequency", "To enhance audio clarity"],
                answer: "To reduce impulse noise"
            },
            {
                question: "What is the maximum allowable power for an Intermediate class licensee on the 15-meter band?",
                options: ["100 watts", "500 watts", "1000 watts", "1500 watts"],
                answer: "100 watts"
            },
            {
                question: "What is the purpose of a dipole antenna?",
                options: ["To provide omnidirectional radiation", "To provide high gain in one direction", "To filter out interference", "To stabilize the frequency"],
                answer: "To provide omnidirectional radiation"
            },
            {
                question: "What is the typical bandwidth of an FM signal in the VHF band?",
                options: ["12.5 kHz", "25 kHz", "2.8 kHz", "100 kHz"],
                answer: "25 kHz"
            },
            {
                question: "What is the purpose of a transverter in amateur radio?",
                options: ["To convert signals between frequency bands", "To amplify weak signals", "To filter out noise", "To stabilize the frequency"],
                answer: "To convert signals between frequency bands"
            },
            {
                question: "What is the maximum allowable bandwidth for RTTY emissions on the 40-meter band?",
                options: ["300 baud", "1200 baud", "2.8 kHz", "19.6 kilobaud"],
                answer: "300 baud"
            },
            {
                question: "What is the purpose of a directional coupler in a transmitter?",
                options: ["To measure forward and reflected power", "To amplify the signal", "To filter out harmonics", "To stabilize the frequency"],
                answer: "To measure forward and reflected power"
            }
        ];

        // Fisher-Yates shuffle algorithm
        function shuffle(array) {
            for (let i = array.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [array[i], array[j]] = [array[j], array[i]];
            }
            return array;
        }

        let currentQuestionIndex = 0;
        let score = 0;
        let shuffledQuizData = [];
        const questionsPerSession = 50; // Number of questions per quiz session

        const questionText = document.getElementById('question-text');
        const optionsContainer = document.getElementById('options');
        const feedback = document.getElementById('feedback');
        const scoreDisplay = document.getElementById('score');
        const nextBtn = document.getElementById('next-btn');
        const startBtn = document.getElementById('start-btn');

        function startQuiz() {
            startBtn.classList.add('hidden');
            nextBtn.classList.remove('hidden');
            currentQuestionIndex = 0;
            score = 0;
            scoreDisplay.textContent = `Score: ${score}`;
            
            // Shuffle all questions and take the first 50
            shuffledQuizData = shuffle([...quizData]).slice(0, questionsPerSession);
            loadQuestion();
        }

        function loadQuestion() {
            feedback.classList.add('hidden');
            const currentQuestion = shuffledQuizData[currentQuestionIndex];
            questionText.textContent = currentQuestion.question;
            optionsContainer.innerHTML = '';

            currentQuestion.options.forEach(option => {
                const button = document.createElement('button');
                button.textContent = option;
                button.classList.add('block', 'w-full', 'text-left', 'p-2', 'mb-2', 'bg-gray-200', 'rounded', 'hover:bg-gray-300');
                button.addEventListener('click', () => selectAnswer(option));
                optionsContainer.appendChild(button);
            });

            if (currentQuestionIndex === shuffledQuizData.length - 1) {
                nextBtn.textContent = 'Finish Quiz';
            }
        }

        function selectAnswer(selectedOption) {
            const currentQuestion = shuffledQuizData[currentQuestionIndex];
            if (selectedOption === currentQuestion.answer) {
                score++;
                scoreDisplay.textContent = `Score: ${score}`;
                feedback.textContent = 'Correct!';
                feedback.classList.remove('text-red-500', 'hidden');
                feedback.classList.add('text-green-500');
            } else {
                feedback.textContent = `Incorrect! The correct answer is ${currentQuestion.answer}.`;
                feedback.classList.remove('hidden');
            }

            optionsContainer.querySelectorAll('button').forEach(btn => {
                btn.disabled = true;
                if (btn.textContent === currentQuestion.answer) {
                    btn.classList.add('bg-green-300');
                } else if (btn.textContent === selectedOption) {
                    btn.classList.add('bg-red-300');
                }
            });

            nextBtn.classList.remove('hidden');
        }

        function nextQuestion() {
            currentQuestionIndex++;
            if (currentQuestionIndex < shuffledQuizData.length) {
                loadQuestion();
            } else {
                questionText.textContent = 'Quiz Completed!';
                optionsContainer.innerHTML = '';
                feedback.classList.add('hidden');
                nextBtn.classList.add('hidden');
                scoreDisplay.textContent = `Final Score: ${score} out of ${shuffledQuizData.length}`;
                startBtn.textContent = 'Restart Quiz';
                startBtn.classList.remove('hidden');
            }
        }

        startBtn.addEventListener('click', startQuiz);
        nextBtn.addEventListener('click', nextQuestion);
    </script>
</body>
</html>
