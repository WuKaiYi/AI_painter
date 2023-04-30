# Speech Synthesis Markup Language (SSML)

這是Speech Synthesis Markup Language (SSML) 格式的說明，用於ai生成語音

The following table has descriptions of each supported `style` attribute.

#### Voice examples <a href="#voice-examples" id="voice-examples"></a>

The supported values for attributes of the `voice` element were [described previously](https://learn.microsoft.com/en-us/azure/cognitive-services/speech-service/speech-synthesis-markup-voice#voice-element).

**Single voice example**

This example uses the `en-US-JennyNeural` voice.

XMLCopy

```xml
<speak version="1.0" xmlns="http://www.w3.org/2001/10/synthesis" xml:lang="en-US">
    <voice name="en-US-JennyNeural">
        This is the text that is spoken.
    </voice>
</speak>
```

**Multiple voices example**

Within the `speak` element, you can specify multiple voices for text-to-speech output. These voices can be in different languages. For each voice, the text must be wrapped in a `voice` element.

This example alternates between the `en-US-JennyNeural` and `en-US-ChristopherNeural` voices.

XMLCopy

```xml
<speak version="1.0" xmlns="http://www.w3.org/2001/10/synthesis" xml:lang="en-US">
    <voice name="en-US-JennyNeural">
        Good morning!
    </voice>
    <voice name="en-US-ChristopherNeural">
        Good morning to you too Jenny!
    </voice>
</speak>
```

**Custom neural voice example**

To use your [custom neural voice](https://learn.microsoft.com/en-us/azure/cognitive-services/speech-service/how-to-deploy-and-use-endpoint#use-your-custom-voice), specify the model name as the voice name in SSML.

This example uses a custom voice named "my-custom-voice".

XMLCopy

```xml
<speak version="1.0" xmlns="http://www.w3.org/2001/10/synthesis" xml:lang="en-US">
    <voice name="my-custom-voice">
        This is the text that is spoken.
    </voice>
</speak>
```

**Audio effect example**

You use the `effect` attribute to optimize the auditory experience for scenarios such as cars and telecommunications. The following SSML example uses the `effect` attribute with the configuration in car scenarios.

XMLCopy

```xml
<speak version="1.0" xmlns="http://www.w3.org/2001/10/synthesis" xml:lang="en-US">
    <voice name="en-US-JennyNeural" effect="eq_car">
        This is the text that is spoken.
    </voice>
</speak>
```

### Speaking styles and roles <a href="#speaking-styles-and-roles" id="speaking-styles-and-roles"></a>

By default, neural voices have a neutral speaking style. You can adjust the speaking style, style degree, and role at the sentence level.

&#x20;Note

Styles, style degree, and roles are supported for a subset of neural voices as described in the [voice styles and roles](https://learn.microsoft.com/en-us/azure/cognitive-services/speech-service/language-support?tabs=tts#voice-styles-and-roles) documentation. To determine what styles and roles are supported for each voice, you can also use the [list voices](https://learn.microsoft.com/en-us/azure/cognitive-services/speech-service/rest-text-to-speech#get-a-list-of-voices) API and the [Audio Content Creation](https://aka.ms/audiocontentcreation) web application.

Usage of the `mstts:express-as` element's attributes are described in the following table.

| Attribute     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | Required or optional |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| `style`       | The voice-specific speaking style. You can express emotions like cheerfulness, empathy, and calm. You can also optimize the voice for different scenarios like customer service, newscast, and voice assistant. If the style value is missing or invalid, the entire `mstts:express-as` element is ignored and the service uses the default neutral speech. For custom neural voice styles, see the [custom neural voice style example](https://learn.microsoft.com/en-us/azure/cognitive-services/speech-service/speech-synthesis-markup-voice#custom-neural-voice-style-example). | Required             |
| `styledegree` | The intensity of the speaking style. You can specify a stronger or softer style to make the speech more expressive or subdued. The range of accepted values are: 0.01 to 2 inclusive. The default value is 1, which means the predefined style intensity. The minimum unit is 0.01, which results in a slight tendency for the target style. A value of 2 results in a doubling of the default style intensity. If the style degree is missing or isn't supported for your voice, this attribute is ignored.                                                                        | Optional             |
| `role`        | The speaking role-play. The voice can imitate a different age and gender, but the voice name isn't changed. For example, a male voice can raise the pitch and change the intonation to imitate a female voice, but the voice name won't be changed. If the role is missing or isn't supported for your voice, this attribute is ignored.                                                                                                                                                                                                                                            | Optional             |

The following table has descriptions of each supported `style` attribute.

| Style                               | Description                                                                                                                                                                                                     |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `style="advertisement_upbeat"`      | Expresses an excited and high-energy tone for promoting a product or service.                                                                                                                                   |
| `style="affectionate"`              | Expresses a warm and affectionate tone, with higher pitch and vocal energy. The speaker is in a state of attracting the attention of the listener. The personality of the speaker is often endearing in nature. |
| `style="angry"`                     | Expresses an angry and annoyed tone.                                                                                                                                                                            |
| `style="assistant"`                 | Expresses a warm and relaxed tone for digital assistants.                                                                                                                                                       |
| `style="calm"`                      | Expresses a cool, collected, and composed attitude when speaking. Tone, pitch, and prosody are more uniform compared to other types of speech.                                                                  |
| `style="chat"`                      | Expresses a casual and relaxed tone.                                                                                                                                                                            |
| `style="cheerful"`                  | Expresses a positive and happy tone.                                                                                                                                                                            |
| `style="customerservice"`           | Expresses a friendly and helpful tone for customer support.                                                                                                                                                     |
| `style="depressed"`                 | Expresses a melancholic and despondent tone with lower pitch and energy.                                                                                                                                        |
| `style="disgruntled"`               | Expresses a disdainful and complaining tone. Speech of this emotion displays displeasure and contempt.                                                                                                          |
| `style="documentary-narration"`     | Narrates documentaries in a relaxed, interested, and informative style suitable for dubbing documentaries, expert commentary, and similar content.                                                              |
| `style="embarrassed"`               | Expresses an uncertain and hesitant tone when the speaker is feeling uncomfortable.                                                                                                                             |
| `style="empathetic"`                | Expresses a sense of caring and understanding.                                                                                                                                                                  |
| `style="envious"`                   | Expresses a tone of admiration when you desire something that someone else has.                                                                                                                                 |
| `style="excited"`                   | Expresses an upbeat and hopeful tone. It sounds like something great is happening and the speaker is really happy about that.                                                                                   |
| `style="fearful"`                   | Expresses a scared and nervous tone, with higher pitch, higher vocal energy, and faster rate. The speaker is in a state of tension and unease.                                                                  |
| `style="friendly"`                  | Expresses a pleasant, inviting, and warm tone. It sounds sincere and caring.                                                                                                                                    |
| `style="gentle"`                    | Expresses a mild, polite, and pleasant tone, with lower pitch and vocal energy.                                                                                                                                 |
| `style="hopeful"`                   | Expresses a warm and yearning tone. It sounds like something good will happen to the speaker.                                                                                                                   |
| `style="lyrical"`                   | Expresses emotions in a melodic and sentimental way.                                                                                                                                                            |
| `style="narration-professional"`    | Expresses a professional, objective tone for content reading.                                                                                                                                                   |
| `style="narration-relaxed"`         | Express a soothing and melodious tone for content reading.                                                                                                                                                      |
| `style="newscast"`                  | Expresses a formal and professional tone for narrating news.                                                                                                                                                    |
| `style="newscast-casual"`           | Expresses a versatile and casual tone for general news delivery.                                                                                                                                                |
| `style="newscast-formal"`           | Expresses a formal, confident, and authoritative tone for news delivery.                                                                                                                                        |
| `style="poetry-reading"`            | Expresses an emotional and rhythmic tone while reading a poem.                                                                                                                                                  |
| `style="sad"`                       | Expresses a sorrowful tone.                                                                                                                                                                                     |
| `style="serious"`                   | Expresses a strict and commanding tone. Speaker often sounds stiffer and much less relaxed with firm cadence.                                                                                                   |
| `style="shouting"`                  | Speaks like from a far distant or outside and to make self be clearly heard                                                                                                                                     |
| `style="sports_commentary"`         | Expresses a relaxed and interesting tone for broadcasting a sports event.                                                                                                                                       |
| `style="sports_commentary_excited"` | Expresses an intensive and energetic tone for broadcasting exciting moments in a sports event.                                                                                                                  |
| `style="whispering"`                | Speaks very softly and make a quiet and gentle sound                                                                                                                                                            |
| `style="terrified"`                 | Expresses a very scared tone, with faster pace and a shakier voice. It sounds like the speaker is in an unsteady and frantic status.                                                                            |
| `style="unfriendly"`                | Expresses a cold and indifferent tone.                                                                                                                                                                          |

The following table has descriptions of each supported `role` attribute.

| Role                      | Description                               |
| ------------------------- | ----------------------------------------- |
| `role="Girl"`             | The voice imitates a girl.                |
| `role="Boy"`              | The voice imitates a boy.                 |
| `role="YoungAdultFemale"` | The voice imitates a young adult female.  |
| `role="YoungAdultMale"`   | The voice imitates a young adult male.    |
| `role="OlderAdultFemale"` | The voice imitates an older adult female. |
| `role="OlderAdultMale"`   | The voice imitates an older adult male.   |
| `role="SeniorFemale"`     | The voice imitates a senior female.       |
| `role="SeniorMale"`       | The voice imitates a senior male.         |

#### mstts express-as examples <a href="#mstts-express-as-examples" id="mstts-express-as-examples"></a>

The supported values for attributes of the `mstts:express-as` element were [described previously](https://learn.microsoft.com/en-us/azure/cognitive-services/speech-service/speech-synthesis-markup-voice#speaking-styles-and-roles).

**Style and degree example**

You use the `mstts:express-as` element to express emotions like cheerfulness, empathy, and calm. You can also optimize the voice for different scenarios like customer service, newscast, and voice assistant.

The following SSML example uses the `<mstts:express-as>` element with a sad style degree of "2".

XMLCopy

```xml
<speak version="1.0" xmlns="http://www.w3.org/2001/10/synthesis"
       xmlns:mstts="https://www.w3.org/2001/mstts" xml:lang="zh-CN">
    <voice name="zh-CN-XiaomoNeural">
        <mstts:express-as style="sad" styledegree="2">
            快走吧，路上一定要注意安全，早去早回。
        </mstts:express-as>
    </voice>
</speak>
```

**Role example**

Apart from adjusting the speaking styles and style degree, you can also adjust the `role` parameter so that the voice imitates a different age and gender. For example, a male voice can raise the pitch and change the intonation to imitate a female voice, but the voice name won't be changed.

This SSML snippet illustrates how the `role` attribute is used to change the role-play for `zh-CN-XiaomoNeural`.

XMLCopy

```xml
<speak version="1.0" xmlns="http://www.w3.org/2001/10/synthesis"
       xmlns:mstts="https://www.w3.org/2001/mstts" xml:lang="zh-CN">
    <voice name="zh-CN-XiaomoNeural">
        女儿看见父亲走了进来，问道：
        <mstts:express-as role="YoungAdultFemale" style="calm">
            “您来的挺快的，怎么过来的？”
        </mstts:express-as>
        父亲放下手提包，说：
        <mstts:express-as role="OlderAdultMale" style="calm">
            “刚打车过来的，路上还挺顺畅。”
        </mstts:express-as>
    </voice>
</speak>
```

**Custom neural voice style example**

Your custom neural voice can be trained to speak with some preset styles such as cheerful, sad, and whispering. You can also [train a custom neural voice](https://learn.microsoft.com/en-us/azure/cognitive-services/speech-service/how-to-custom-voice-create-voice?tabs=multistyle#train-your-custom-neural-voice-model) to speak in a custom style as determined by your training data. To use your custom neural voice style in SSML, specify the style name that you previously entered in Speech Studio.

This example uses a custom voice named "my-custom-voice". The custom voice speaks with the "cheerful" preset style, and then with a custom style named "my-custom-style".

XMLCopy

```xml
<speak version="1.0" xmlns="http://www.w3.org/2001/10/synthesis"
       xmlns:mstts="https://www.w3.org/2001/mstts" xml:lang="en-US">
    <voice name="my-custom-voice">
        <mstts:express-as style="cheerful">
            That'd be just amazing!
        </mstts:express-as>
        <mstts:express-as style="my-custom-style">
            What's next?
        </mstts:express-as>
    </voice>
</speak>
```
