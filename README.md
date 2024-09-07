# ScribeSlate

ScribeSlate is a transcription and translation application that leverages pre-built advanced machine learning models using web-workers to convert speech to text and translate text between different international and Indian regional languages. This project is built using Vite and React with Tailwind CSS.

## `Table of Contents`

- [Features](#features)
- [Installation](#installation)
- [Technologies Used](#technologies-used)
- [Components](#components)
- [About the Model](#about-the-model)
- [Video Demo](#video-demo)
- [Contributing](#contributing)
- [License](#license)
- [Additional Files and Configurations](#additional-files-and-configurations)

## `Features`

- **Transcription**: Convert speech to text using OpenAI's Whisper model.
- **Translation**: Translate text between different languages using Xenova/transformers library.
- **Simple UI**: Built with React and styled with Tailwind CSS for a clean and responsive interface.

## `Installation`

Follow these steps to run the project on your local computer:

1. **Clone the repository**
    ```bash
    git clone https://github.com/yourusername/scribeslate.git
    cd scribeslate
    ```

2. **Install dependencies**
    ```bash
    npm install
    ```

3. **Run the project**
    ```bash
    npm run dev
    ```

4. **Open the project in your browser**
    ```plaintext
    Vite will provide a local server address, typically http://localhost:3000, which you can open in your web browser to see the application in action.
    ```

## `Technologies Used`

- **Frontend**: React, Vite, Tailwind CSS
- **Backend**: Web Workers, Xenova/transformers library
- **Models**: OpenAI Whisper for transcription, Xenova/transformers for translation

## `Components`

- **FileDisplay.jsx**: Handles display and management of uploaded files.
- **Header.jsx**: Provides navigation and branding.
- **HomePage.jsx**: Serves as the main landing page.
- **Information.jsx**: Handles the displayed information.
- **Transcribing.jsx**: Manages the transcription process using `whisper.worker.js`.
- **Transcription.jsx**: Displays and allows editing of transcribed text.
- **Translation.jsx**: Handles text translation using `translate.worker.js`.

## `Additional Files and Configurations`

### presets.js
- This file contains the configuration for message types, loading statuses, model names, and supported languages.

### whisper.worker.js
- Handles the transcription process using OpenAI's Whisper model. It receives audio data from the main thread, processes it with the Whisper model, and sends the transcribed text back to the main thread. This allows for efficient, asynchronous transcription of audio files without blocking the main application.

### translate.worker.js
- Manages text translation using the Xenova/transformers library. It receives text and language parameters from the main thread, processes the translation using the model, and sends the translated text back to the main thread. This enables seamless and efficient translation of text within the application.

## `About the Model`

- **Whisper Model (Transcription)**
    - `Accuracy`: OpenAI's `pre-trained` Whisper model can achieve accuracy rates between 95% and 98.5% depending on the model size and audio quality
    - `Efficiency`: Compared to traditional speech recognition systems, it can be significantly faster, especially on less powerful hardware.
OpenAI provides different model sizes (small, medium, and large). 

        | Model Size | Accuracy | Efficiency |
        |------------|----------|------------|
        | Small      | 95%      | Fastest    |
        | Medium     | 99.3%    | Faster     |
        | Large      | 98.5%    | Slower     |


- **Xenova/transformers (Translation)**
    - `Accuracy`: High, can reach human-level for specific languages (ideal conditions).
      Depends on chosen `pre-trained model` (e.g., T5, MarianMT, BART).
    - `Efficiency`: Faster than traditional methods due to JavaScript and potential GPU usage.
      - Efficiency depends on:
        - Model size (larger = slower)
        - Hardware (GPU > CPU)
        - Input text complexity (simpler = faster)

## `Video Demo`

Watch the video demonstration of the project here: *https://drive.google.com/file/d/1qs6FrZx5CvNNwSf7NmC3LO6_hNNqBM3w/view?usp=sharing*

## `Contributing`

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a new Pull Request.

## `License`

This project is licensed under the MIT License. See the LICENSE file for details.
