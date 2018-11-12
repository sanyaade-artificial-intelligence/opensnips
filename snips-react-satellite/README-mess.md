

## TODO

### Microphone
- recording duration timeout + other timeout

### AppServer
- say method (and other helpers -> end, continue) export available in app server intent functions
- debounce




### Opensnips
- extend logger to replace opensnips with nodejs replacements for snips-scripts (plus gstreamer-kaldi and rasa server)
* props.disableDefaultListeners 
* kaldi retraining based on user recordings

* methods suitable for nodejs and browser 
  - SnipsAudioServer
  - SnipsTtsServer
  - SnipsHotwordServer
  - SnipsDialogueServer
  - SnipsAsrServer (with kaldi)
  - SnipsNluServer (with rasa)
  - SnipsAppServer
  - SnipsRasaCoreAppServer
  - SnipsTrainingServer (with kaldi/rasa)
        - start with slot values
        - rasa intents
        - rasa core
  - ?? SnipsAirTokensWorker - arbitrary work (training) distributed to clients ??
  - SnipsVoiceIdServer
        - piwho mqtt listener -> userId events
        - ??? pi voiceId/login hooks
  - SnipsDiscoveryServer - mqtt based site discovery

- local messaging wrappers around mqtt send to pass local messages locally to browser
- ? 100% browser ASR - pocketSphinx, NLU - see speechify.js
https://github.com/syl22-00/pocketsphinx.js

- model building UI
    - intents and slots and actions (nodejs/browser)
    - training server

### Snips Image
- sam
- sam login entrypoint in docker image + update docs
- skills server
- toggle services


## OpenSnips aims to be an implementation of the Snips Hermes MQTT protocol in javascript
- run Snips Services in a web browser or in nodejs on a server and orchestrate a mixture of them.
- using PocketSphinx.js for ASR and a custom NLU module, with a local only MQTT proxy, the whole stack can be run in a Web Browser.
- switch between a number of providers of ASR (Snips/Kaldi/Google/Amazon Polly/OpenSphinx/DeepSpeech/???) and NLU (Snips/RASA/Custom/DialogFlow/??) services 

- implement audio on the server using mpg123 and sox as base layers for cross platform support to Windows as well as Linux/Mac/Android.
- support simultaneous input from multiple sources (audioserver -> intent) debounced to trigger a single intent.

- support distributed training via the mqtt protocol.

Because OpenSnips relies on a number of services, we suggest using Docker to orchestrate the suite of microservices as per the included example.




### Config

- inputvolume
- outputvolume
- voicevolume
- ttsvoice
- voicerate
- voicepitch
- remotecontrol
- hotword
- hotwordsensitivity
- silencedetection
- silencesensitivity
- enabletts
- enableaudio
- enablenotifications
