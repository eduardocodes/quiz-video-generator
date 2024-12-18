# 🎥 Quiz Video Generator

#### Vídeo:

## URLs

Gerar música - https://api.musicfy.lol/v1/generate-music<br>
Baixar música - https://api.apyhub.com/convert/audio/wav-url/mp3-url<br>

## 👨‍💻 Códigos

## Before

```bash
<style>
.background {
    background-color: rgba(0, 0, 0, 0);
    border-radius: 12px;
}

.option {
    background-color: rgba(128, 128, 128, 0.5);
    padding: 3rem;
    text-align: center;
    font-size: 3rem;
    border-radius: 0.75rem;
    margin-bottom: 1rem;
    width: 100%;
    font-weight: 600;
    color: white;
}

.option:last-child {
    margin-bottom: 0;
}

.question {
    background-color: rgba(0, 0, 0, 0.5);
    padding: 3rem;
    text-align: center;
    font-size: 5rem;
    border-radius: 0.75rem;
    width: 100%;
    font-weight: 600;
    color: white;
    margin-bottom: 1rem;
}
</style>

<div class="flex items-center justify-center h-screen bg-transparent" style="width: 1080px; height: 1920px;">
    <div class="background w-full p-6 rounded-lg" style="max-width: 1080px;">
        <h1 class="question text-center">
            {{3.question}}
        </h1>

        <div class="space-y-6">
            <div class="option">
                {{3.options[1]}}
            </div>
            <div class="option">
                {{3.options[2]}}
            </div>
            <div class="option">
                {{3.options[3]}}
            </div>
        </div>
    </div>
</div>
```

### After

```bash
<style>
.stroked-text {
    color: white;
    font-weight: bold;
}

.background {
    background-color: rgba(0, 0, 0, 0);
    border-radius: 12px;
}

.correct-answer {
    background-color: #38a169;
    color: white;
}

.incorrect-option {
    background-color: rgba(128, 128, 128, 0.5);
    color: white;
}

.option {
    padding: 3rem;
    text-align: center;
    font-size: 3rem;
    border-radius: 0.75rem;
    width: 100%;
    font-weight: 600;
    margin-bottom: 1rem;
}

.option:last-child {
    margin-bottom: 0;
}

.question {
    background-color: rgba(0, 0, 0, 0.5);
    padding: 3rem;
    text-align: center;
    font-size: 5rem;
    border-radius: 0.75rem;
    width: 100%;
    font-weight: 600;
    color: white;
    margin-bottom: 1rem;
}
</style>

<div class="flex items-center justify-center h-screen bg-transparent" style="width: 1080px; height: 1920px;">
    <div class="background w-full p-6 rounded-lg" style="max-width: 1080px;">
        <h1 class="question text-center mb-8">
            {{3.question}}
        </h1>

        <div class="space-y-6">
            <div class="option {{if(3.options[1] = 3.answer; " correct-answer"; "incorrect-option")}}">
                {{3.options[1]}}
            </div>
            <div class="option {{if(3.options[2] = 3.answer; " correct-answer"; "incorrect-option")}}">
                {{3.options[2]}}
            </div>
            <div class="option {{if(3.options[3] = 3.answer; " correct-answer"; "incorrect-option")}}">
                {{3.options[3]}}
            </div>
        </div>
    </div>
</div>
```

### Create Movie from JSON

```bash
{
  "id": "q0auykfj",
  "comment": "Empty movie",
  "resolution": "instagram-story",
  "quality": "high",
  "scenes": [
    {
      "id": "qmrdxtjk",
      "comment": "Scene 1",
      "elements": [
        {
          "id": "q44jxi2d",
          "type": "image",
          "comment": "BackGround Image",
          "src": "{{6.generated_images[].url}}",
          "width": 1080,
          "height": 1920,
          "x": 0,
          "y": 0,
          "duration": 8
        },
        {
          "id": "qhjpm2cw",
          "type": "image",
          "comment": "AnswerImage",
          "src": "{{7.generated_images[].url}}",
          "width": 1080,
          "height": 1920,
          "duration": 1.5,
          "start": 8,
          "x": 0,
          "y": 0
        },
        {
          "id": "qpnk6koc",
          "type": "voice",
          "comment": "Qv",
          "text": "{{3.question}}",
          "voice": "pt-BR-AntonioNeural",
          "duration": 3
        },
        {
          "id": "q82olzuq",
          "type": "voice",
          "comment": "Av",
          "text": "A resposta é {{3.answer}}",
          "voice": "pt-BR-AntonioNeural",
          "start": 7.5,
          "duration": 2
        }
      ]
    }
  ],
  "elements": [
    {
      "id": "q4pitum2",
      "type": "html",
      "comment": "Before",
      "tailwindcss": true,
      "position": "custom",
      "x": 0,
      "y": -350,
      "duration": 8,
      "html": "{{replace(replace(8.Before; """"; "\"""); newline; "\n")}}"
    },
    {
      "id": "q5ojpmaa",
      "type": "html",
      "comment": "After",
      "tailwindcss": true,
      "position": "custom",
      "x": 0,
      "y": -350,
      "start": 8,
      "duration": 1.5,
      "html": "{{replace(replace(8.After; """"; "\"""); newline; "\n")}}"
    },
    {
      "id": "qbtmfjvx",
      "type": "audio",
      "src": "https://assets.json2video.com/clients/cuzocz7xi6/uploads/Count Down_timer (online-audio-converter.com).mp3",
      "duration": 5,
      "start": 3
    },
    {
      "id": "q13x7ihb",
      "type": "image",
      "src": "https://assets.json2video.com/clients/cuzocz7xi6/uploads/8 to 0.gif",
      "x": 0,
      "position": "custom",
      "y": 1100,
      "duration": 5,
      "start": 3
    }
  ],
  "width": 1080,
  "height": 1920
}
```
