

# Crazy Tom - Voice Changer Fun

Crazy Tom is a fun, interactive web application where 'Crazy Tom' the cat listens to your voice and repeats it back in a hilariously altered, high-pitched tone. It features real-time audio visualization, automatic silence detection, and interactive animations.

![image](https://github.com/user-attachments/assets/411b56e1-cc38-483e-84ad-d5849647973a)

## Features

*   **Voice Recording:** Click the cat to start and stop recording your voice.
*   **Funny Voice Playback:** Tom repeats what you said with a high-pitched "chipmunk" effect.
*   **Interactive Cat Animation:** The cat image pulses when idle, animates when "talking," and provides visual cues.
*   **Speech Bubble:** Tom shows messages like "Listening...", "Thinking...", or a random funny phrase.
*   **Status Indicator:** A clear status bar below the cat shows the current state (Ready, Recording, Paused, Processing, Playing, Error).
*   **Real-time Audio Visualizer:** A dynamic visualizer at the bottom of the screen reacts to your voice during recording and Tom's voice during playback.
*   **Automatic Silence Detection:** Recording automatically stops after a configurable period of silence (currently 3.5 seconds).
*   **Pause/Resume Recording:** Press the `SPACEBAR` to pause or resume an ongoing recording.
*   **Microphone Permission Guidance:**
    *   A one-time modal explains the need for microphone access.
    *   Clear error messages if microphone access is denied or encounters issues.
*   **Responsive Design:** Adapts to different screen sizes.

## Getting Started

1.  **Open the Application:**
    *   Simply open the `index.html` file in a modern web browser (Chrome, Firefox, Safari, Edge are recommended).
    *   For best results, ensure your browser is up to date.

2.  **Microphone Permission:**
    *   The first time you try to record, the application will (or your browser will directly) ask for permission to use your microphone.
    *   **Please click "Allow"**. Crazy Tom needs to hear you to talk back!

## How to Use

1.  **Click the Cat:** Click on the cat image to start recording your voice.
    *   The status will change to "Recording..." and the cat will visually indicate it's listening.
2.  **Speak:** Say something into your microphone. You'll see the audio visualizer react.
3.  **Stop Recording:**
    *   **Manually:** Click the cat image again.
    *   **Automatically:** Recording will stop automatically if you remain silent for about 3.5 seconds.
4.  **Processing:** The status will briefly show "Mixing sounds..." as Tom prepares to speak.
5.  **Listen to Tom:** Tom will play back your recorded audio with a funny, high-pitched voice. The cat will animate as if it's talking.
6.  **Pause/Resume (During Recording):**
    *   Press the `SPACEBAR` on your keyboard to pause the recording.
    *   Press `SPACEBAR` again to resume recording.
7.  **Status Updates:** Keep an eye on the status indicator below the cat for real-time updates on what the app is doing.

## Technical Stack

*   **HTML5:** For the basic structure of the web page.
*   **CSS3:** For styling, including:
    *   **Tailwind CSS:** A utility-first CSS framework for rapid UI development.
    *   Custom CSS animations and styling.
*   **Font Awesome:** For icons.
*   **JavaScript (ES6+):** For all the application logic, including:
    *   **Web Audio API:**
        *   `AudioContext`: For managing and processing audio.
        *   `AnalyserNode`: For audio visualization and silence detection.
        *   `BiquadFilterNode`, `DynamicsCompressorNode`, `GainNode`: For creating the voice-changing effect.
        *   `decodeAudioData`: To process the recorded audio.
    *   **`navigator.mediaDevices.getUserMedia`:** To access the user's microphone.
    *   **`MediaRecorder` API:** To record audio from the microphone.
    *   **SVG:** The cat image is an embedded SVG, allowing for dynamic interaction.
    *   **`localStorage`:** Used to remember if the initial microphone permission info modal has been shown.

## Key Implementation Details

*   **iOS Audio Unlocking:** The application includes a mechanism to "unlock" or "prime" the Web Audio API on iOS devices. iOS often requires a direct user gesture (like a click) to enable full audio playback capabilities for programmatically generated sound. A tiny, silent sound buffer is played upon the first user interaction to facilitate this.
*   **Silence Detection:** Uses the `AnalyserNode` to monitor the time-domain data of the audio stream. If the amplitude remains below a certain threshold for a set duration, the recording stops.
*   **Visual Feedback:** Rich visual feedback is provided through cat animations, the speech bubble, the status indicator, and the audio visualizer to keep the user informed and engaged.
*   **Error Handling:** Basic error handling is in place for microphone access issues and audio processing problems, with user-friendly messages.

## Troubleshooting

*   **No Sound Output (especially on iOS/Mobile):**
    *   Ensure your device is **not in silent mode** and the volume is up.
    *   The app attempts to unlock audio on iOS, but sometimes browser/OS restrictions can interfere. Try a fresh page load and ensure your *very first interaction* with the page is clicking the cat to record.
*   **Microphone Not Working / "Mic access denied":**
    *   Check your browser's site settings (usually accessible by clicking the padlock icon in the address bar) to ensure microphone access is **allowed** for this page.
    *   Make sure your microphone is properly connected and selected as the default input device in your computer's or phone's system settings.
    *   If you previously denied permission, you'll need to change it in your browser settings.
*   **Recording Doesn't Start / Stuck on "Requesting Mic...":**
    *   This usually indicates an issue with microphone permissions or the browser being unable to access any microphone. Follow the steps above.
*   **Audio Visualizer Not Moving:**
    *   This means no audio is being picked up or processed. Check microphone permissions and connections.

## Future Enhancements (Ideas)

*   Offer a selection of different voice effects.
*   Option to save or share the funny recordings.
*   More complex cat animations and interactions.
*   A gallery of pre-recorded Tom phrases.

---

Built by Anish Thapa. Enjoy the fun!
