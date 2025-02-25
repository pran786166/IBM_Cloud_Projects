# IBM_Cloud_Projects
# IBM Cloud Text-to-Speech and Speech-to-Text Service

## **Overview**
This repository demonstrates the usage of **IBM Cloud’s Text-to-Speech (TTS)** and **Speech-to-Text (STT)** services. Using IBM Watson's AI-powered APIs, this project automates text-to-speech conversion and speech-to-text transcription through **Git Bash**.

## **Technologies Used**
- **IBM Cloud Watson Services** (TTS & STT APIs)
- **cURL Commands**
- **Git Bash** (Command-Line Execution)
- **JSON Processing**
- **FFmpeg** (Optional for audio format conversions)

## **Setup Instructions**
1. **Create an IBM Cloud Account**: Sign up at [IBM Cloud](https://cloud.ibm.com/).
2. **Provision Watson TTS & STT Services**: Generate API keys and service instances.
3. **Install Dependencies**:
   - Ensure `cURL` and `Git Bash` are installed on your system.
   - Optionally, install `FFmpeg` for audio format conversions.

## **Implementation**

### **1. Text-to-Speech (TTS) - Convert Text to Audio**
```bash
curl -X POST -u "apikey:{apikey}" \
--header "Content-Type: application/json" \
--header "Accept: audio/wav" \
--data "{\"text\":\"hello world\"}" \
--output hello_world.wav \
"{url}/v1/synthesize?voice=en-US_MichaelV3Voice"
```

### **2. Speech-to-Text (STT) - Convert Audio to Text**
```bash
curl -X POST -u "apikey:<YOUR_API_KEY>" \
    --header "Content-Type: audio/wav" \
    --data-binary @output.wav \
    "IBM Speech-to-Text API Endpoint"
```

## **Output**
1. **TTS Result**: Speech audio is saved as `output.wav`.
2. **STT Result**: The API returns a JSON response with transcribed text:
```json
{
  "results": [
    {
      "alternatives": [
        {
          "transcript": "Hello, this is a test of IBM Watson Text-to-Speech service.",
          "confidence": 0.98
        }
      ]
    }
  ]
}
```

## **License**
This project is licensed under the **MIT License**.

## **Contributing**
Feel free to contribute by submitting pull requests or reporting issues.

## **Contact**
For any questions or issues, reach out via [IBM Cloud Support](https://cloud.ibm.com/unifiedsupport).

