#Hello
This is step by step guide to intergrated these TTS Component to your Home Assistant

### STEP1. Download to your Home Assistant Custom_Component Folder

1.1. git clone or copy row file to your Home Assistant Custom_Component Folder

### STEP2. Register and get Free Token/API from STT engines

2.1. Register and create Google API key at: https://support.google.com/googleapi/answer/6158862?hl=en

### STEP3. Configure these TTS Component

3.1. Create folder name tts at local home assistant: www/tts

3.2. Configure the API in your configuration.yaml

3.2.1. Configure Example for Google Cloud TTS
```sh
#TTS of Google Cloud TTS
tts_ggcloud:
 api: 'your Gooogle API' 
 #See in the /custom_components/tts_ggcloud/readme.txt for more detail how to create Google API
 url: 'your hass base URL'

```
3.3. Restart your hass to active these TTS Component

### STEP4. Configure these TTS Component

4.1. Example script use Google Cloud TTS
```sh
script:
  gg_reading_01:  #May be from your script name
    sequence:  
    - service: tts_ggcloud.say
      data_template:
        entity_id: media_player.van_phong
        message: "Your text input here" #May be from your input_text
        speed: '1.0' #May be from your input_number
        pitch: '0' #May be from your input_number
        language: "vi-VN" #May be from your input_select
        voice_name: "Google_Voice_1"' #May be from your input_select
```
5. Enjoy with the TTS voice
