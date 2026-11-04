# Purpose-built AWS AI services

Purpose-built services expose a pre-trained capability through an API. On the exam, choose one when the desired input and output match a standard task and the team wants little model-development work.

## Selection map

| Need | Input → output | Service | Decisive cue |
|---|---|---|---|
| Analyze language | Text → sentiment, entities, key phrases, topics, PII, or categories | Amazon Comprehend | Insights from existing text |
| Build a conversational interface | Voice or text → recognized intent and slots | Amazon Lex | Bot, intent, utterance, slot, conversation |
| Personalize recommendations | User/item/event data → ranked recommendations | Amazon Personalize | Recommendations tailored to each user |
| Synthesize speech | Text → audio | Amazon Polly | The application needs to speak |
| Analyze visual media | Image or video → labels, faces, moderation findings, or text | Amazon Rekognition | Objects, scenes, faces, or unsafe visual content |
| Read documents | Document image/PDF → text, forms, tables, queries, or document fields | Amazon Textract | Structure in forms, receipts, invoices, or tables |
| Recognize speech | Audio → text | Amazon Transcribe | Calls, meetings, captions, or searchable recordings |
| Translate language | Text in one language → text in another | Amazon Translate | Language conversion |

## Amazon Comprehend

Use Comprehend for natural language processing on existing text. Common cues include sentiment analysis, entity recognition, key phrases, language detection, topic modeling, PII detection, and custom classification.

Do not choose Comprehend to generate an original response, build a conversational bot, or translate text. A foundation model generates; Lex manages intent-based conversations; Translate changes the language.

**Scenario:** A retailer wants to classify thousands of reviews by sentiment and extract product names. Choose Comprehend.

[Official Amazon Comprehend documentation](https://docs.aws.amazon.com/comprehend/latest/dg/what-is.html)

## Amazon Lex

Use Lex to build voice and text conversational interfaces. Lex models intents, sample utterances, and slots, then can invoke fulfillment logic.

Lex is a strong answer when the question describes a transactional bot with defined intents, such as booking an appointment or checking an order. A general-purpose generative assistant may use Bedrock instead. Some architectures combine them.

**Scenario:** A caller says, "Move my appointment to Friday," and the bot must identify the reschedule intent and date slot. Choose Lex.

[Official Amazon Lex V2 documentation](https://docs.aws.amazon.com/lexv2/latest/dg/what-is.html)

## Amazon Personalize

Use Personalize to create individualized recommendations and rankings from user behavior, item data, and interaction events. The service handles recommendation-model workflows without requiring the team to build them from scratch.

Do not choose Personalize for generic text generation or broad business analytics.

**Scenario:** A streaming app must rank shows for each viewer based on viewing history. Choose Personalize.

[Official Amazon Personalize documentation](https://docs.aws.amazon.com/personalize/latest/dg/what-is-personalize.html)

## Amazon Polly

Use Polly to turn text into speech. Cues include lifelike voices, narration, accessibility audio, announcements, and speech synthesis.

Polly and Transcribe point in opposite directions.

**Scenario:** An accessibility feature must read an article aloud. Choose Polly.

[Official Amazon Polly documentation](https://docs.aws.amazon.com/polly/latest/dg/what-is.html)

## Amazon Rekognition

Use Rekognition to analyze images and videos. It can detect labels, scenes, faces, unsafe content, and text in visual media. The exam expects service recognition rather than implementation detail.

Choose Textract when document structure matters. Rekognition can detect text in an image, but Textract targets documents and extracts forms, tables, and fields.

**Scenario:** A media site must flag unsafe uploaded images. Choose Rekognition.

[Official Amazon Rekognition documentation](https://docs.aws.amazon.com/rekognition/latest/dg/what-is.html)

## Amazon Textract

Use Textract for optical character recognition plus document structure. Cues include scanned forms, invoices, receipts, tables, handwriting, key-value pairs, and document processing.

**Scenario:** An insurer needs claim numbers and values from scanned forms. Choose Textract rather than Rekognition.

[Official Amazon Textract documentation](https://docs.aws.amazon.com/textract/latest/dg/what-is.html)

## Amazon Transcribe

Use Transcribe to convert recorded or streaming speech into text. Cues include call transcripts, subtitles, meeting notes, speaker labeling, and searchable audio.

Transcribe produces text. Polly produces audio. Comprehend can analyze the transcript after Transcribe creates it.

**Scenario:** A contact center needs transcripts before running sentiment analysis. Use Transcribe, then Comprehend.

[Official Amazon Transcribe documentation](https://docs.aws.amazon.com/transcribe/latest/dg/what-is.html)

## Amazon Translate

Use Translate for neural machine translation between languages. It supports real-time and batch text translation and can work in a pipeline with other language services.

**Scenario:** A support application must translate incoming Spanish messages to English. Choose Translate. Add Comprehend only if the application must analyze the translated text.

[Official Amazon Translate documentation](https://docs.aws.amazon.com/translate/latest/dg/what-is.html)

## Combined-service scenarios

- **Multilingual call analysis:** Transcribe speech, Translate the text, then Comprehend sentiment.
- **Read a translated document aloud:** Textract the document, Translate the text, then Polly creates speech.
- **Voice bot:** Lex manages intents and conversation; Lambda can perform fulfillment; Polly and Transcribe capabilities support the voice experience.
- **Personalized content:** Personalize ranks items; another service stores or delivers them.

A pipeline can combine multiple services, with each service performing a distinct transformation.

The [official AIF-C01 in-scope list](https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/aif-01-in-scope-services.html) is subject to change.

[Domain guide](../README.md#domain-guide) · [Service selection](service-selection.md) · [Reference index](README.md)
