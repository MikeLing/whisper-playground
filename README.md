<div align="center">
  <img width="60px" src="https://user-images.githubusercontent.com/6180201/124313197-cc93f200-db70-11eb-864a-fc65765fc038.png" alt="giant microphone"/>   
 <br/>
  <h2 align="center">Whisper Playground</h2>
  <h6 align="center">Instantly build real-time speech2text apps in 99 languages using faster-whisper, Diart, and Pyannote</h6>
  <h6 align="center">Live demo out soon!</h6>
</div>

![visitors](https://visitor-badge.glitch.me/badge?page_id=saharmor.whisper-playground&left_color=green&right_color=red)



https://github.com/ethanzrd/whisper-playground/assets/79014814/44a9bcf0-e374-4c71-8189-1d99824fbdc5



# Setup
1. Have [`Conda`](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html) and [`Yarn`](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable) on your device 
2. Clone or fork this repository
3. Install the backend and frontend environment `sh install_playground.sh`
4. Review config.py to make sure the transcription device and compute type match your setup
5. Run the backend `cd backend && python server.py`
6. In a different terminal, run the React frontend `cd interface && yarn start`

# Parameters

- Model Size: Choose the model size, from tiny to large-v2.
- Language: Select the language you will be speaking in.
- Transcription Timeout: Set the number of seconds the application will wait before transcribing the current audio data.
- Beam Size: Adjust the amount of transcriptions generated and considered, which affects accuracy and transcription generation time.
- Transcription Method: Choose "real-time" for real-time diarization and transcriptions, or "sequential" for periodic transcriptions with more context.

## Troubleshooting

- If you're unable to connect from the client to the server, use an ngrok tunnel to expose port 8000.
- On MacOS, if building the wheel for safetensors fails, install Rust `brew install rust` and try again.

## Known Bugs

1. On MacOS, there's a clash between av files preventing transcription (works well on Google Colab with Python 3.8).
2. In the sequential mode, there may be uncontrolled speaker swapping, which can be fixed by using pyannote's building blocks and handling speakers manually.
3. In real-time mode, audio data not meeting the transcription timeout won't be transcribed.
4. Speechless batches will cause errors.

This repository hasn't been tested for all languages; please create an issue if you encounter any problems.

## License

This repository and the code and model weights of Whisper are released under the MIT License.
