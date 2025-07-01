## Video-To-Text
A simple Python tool that extracts audio from a video, detects the spoken language, transcribes the speech to text using OpenAI’s Whisper model, and translates non-English speech into English. The output is a plain-text transcript suitable for feeding into language models or reading as a transcript.

#Features

Extract audio from any video file (MP4, MOV, AVI, etc.)

Detect the spoken language using Whisper’s language detection

Transcribe English speech to text

Translate non-English speech (e.g., Greek) into English

Save the transcript to a .txt file with optional language code header

#Requirements

Python 3.7 or higher

ffmpeg (must be installed and available in your system’s PATH)

Python packages:

pip install ffmpeg-python openai-whisper torch

#Installation

Clone the repository (or copy the script directly):

git clone https://github.com/yourusername/video-transcriber.git
cd video-transcriber

#Install dependencies:

pip install -r requirements.txt

(Alternatively, install packages individually as shown above.)

#Usage

Run the script with a video file as input:

python video_transcribe.py <input_video> [output_txt]

<input_video>: Path to your video file

[output_txt] (optional): Filename for the transcript (default: transcript.txt)

#Script Output:

Logs the detected language and task (transcribe or translate).

Saves the transcript to the specified .txt file.

#Example

$ python video_transcribe.py interview.mp4
Extracting audio...
Detected language: el (confidence 99.76%)
Running Whisper task='translate'...
Transcript saved to 'transcript.txt'.

The resulting transcript.txt might look like:

[Original language: el]
Hello everyone, and welcome to our interview series. Today...

Script Overview

extract_audio(video_path, audio_path): Uses ffmpeg-python to extract and convert the video’s audio into a 16 kHz mono WAV file.

transcribe_and_translate(audio_path, model_size): Loads a Whisper model (default: small), detects language, and runs either transcription or translation.

main(): Handles command-line arguments, temporary audio extraction, transcription, and writing the output file.

#Customization

Change the Whisper model size by passing a different model_size (tiny, base, small, medium, large) in the script.

Modify audio settings (sample rate, channels) in extract_audio() as needed.

#License

This project is licensed under the MIT License. See the LICENSE file for details.

#Acknowledgments

OpenAI Whisper

ffmpeg-python
