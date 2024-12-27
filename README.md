
# Speech-to-Text with Whisper, Noise Reduction, and Grammar Correction

This project uses OpenAI's Whisper model to transcribe audio files into text. It integrates noise reduction and grammar correction features to produce cleaner and more accurate transcriptions. The tool supports processing long audio files by splitting them into smaller segments, applying noise reduction, and transcribing them sequentially. The transcription is then corrected for grammar errors using the LanguageTool API.

## Features
- **Audio Format Conversion:** Automatically converts audio files to WAV format with a sampling rate of 16 kHz.
- **Noise Reduction:** Applies noise reduction to audio files for cleaner transcription.
- **Audio Splitting:** Splits long audio files into smaller, manageable segments for easier processing.
- **Speech-to-Text Transcription:** Uses the Whisper model to convert speech into text.
- **Grammar Correction:** Corrects grammatical errors in the transcriptions using the LanguageTool API.
- **Support for Multiple Audio Formats:** Converts and processes various audio formats (e.g., MP3, WAV, etc.).

## Prerequisites

To run the project, you need to have the following dependencies installed:

- **Python 3.6+**
- **ffmpeg** (for audio conversion)
- **librosa** (for audio processing)
- **whisper** (for speech-to-text transcription)
- **language-tool-python** (for grammar correction)
- **noisereduce** (for noise reduction)
- **portaudio19-dev**, **python3-dev**, **python-dev** (for speech recognition)

Install the required packages by running the following commands:

```bash
pip install openai==0.28.0
pip install git+https://github.com/openai/whisper.git -q
pip install SpeechRecognition
pip install openai-whisper language-tool-python
pip install noisereduce
sudo apt-get update && sudo apt-get install -y portaudio19-dev python3-dev python-dev ffmpeg libav-tools
```

## Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/yourusername/speech-to-text-whisper.git
   cd speech-to-text-whisper
   ```

2. **Install the Dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

3. **Ensure `ffmpeg` is installed:**

   ```bash
   sudo apt-get install ffmpeg
   ```

4. **Run the Program:**

   Once all dependencies are installed, you can run the program by executing the following command:

   ```bash
   python main.py
   ```

## Usage

1. **Prepare your audio file:** Make sure the audio file is accessible and in a format that Whisper can process (e.g., MP3, WAV).
   
2. **Run the program:**
   - When prompted, provide the path to your audio file.
   - The program will:
     - Convert the file to WAV format (if necessary).
     - Perform noise reduction on the audio.
     - Split the audio into smaller segments (if the audio is too long).
     - Transcribe each segment using Whisper.
     - Process and correct the transcription with the LanguageTool API.
   
3. **Output:** After processing, the program will output a grammatically corrected transcription saved in a text file (`final_transcription_output.txt`).

## Workflow

1. **Convert to WAV Format:** The program converts audio to WAV format with a 16 kHz sample rate if it's not already in the correct format.
2. **Noise Reduction:** Noise reduction is applied to the audio to improve transcription accuracy.
3. **Audio Splitting:** The audio is split into smaller segments if it exceeds a specified duration (default 5 minutes per segment).
4. **Transcription:** Each segment is transcribed using Whisper, a powerful speech-to-text model.
5. **Grammar Correction:** The transcribed text is checked and corrected for grammar using the LanguageTool API.
6. **Save Final Transcription:** The final, corrected transcription is saved to a text file.

## Example Output

```text
Final Combined Transcription:
Hello, my name is John. I would like to know more about your services. Can you please provide more information?
...
```

## Contributing

Contributions to the project are welcome! If you have suggestions, improvements, or bug fixes, feel free to open an issue or submit a pull request.

1. Fork the repository
2. Create a new branch (`git checkout -b feature-branch`)
3. Make your changes
4. Commit your changes (`git commit -am 'Add new feature'`)
5. Push to the branch (`git push origin feature-branch`)
6. Open a pull request


## Acknowledgments

- **OpenAI Whisper:** For providing the powerful Whisper model for transcription.
- **LanguageTool:** For offering an API to correct grammar in the transcriptions.
- **Noisereduce:** For its noise reduction capabilities, enhancing transcription quality.
- **FFmpeg:** For handling the conversion of various audio formats to WAV.

