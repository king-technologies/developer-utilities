# Chrome Built-in AI

- [Chrome On Device Internals](chrome://on-device-internals/)
- [Chrome Components](chrome://components/)
- [Prompt API for Gemini Nano](chrome://flags/#prompt-api-for-gemini-nano)
- [Summarization API for Gemini Nano](chrome://flags/#summarization-api-for-gemini-nano)
- [Writer API for Gemini Nano](chrome://flags/#writer-api-for-gemini-nano)
- [Rewriter API for Gemini Nano](chrome://flags/#rewriter-api-for-gemini-nano)
- [Proofreader API for Gemini Nano](chrome://flags/#proofreader-api-for-gemini-nano)
- [Chrome AI Settings](chrome://settings/ai)
- [Firebase Hybrid on Device AI](https://firebase.google.com/docs/ai-logic/hybrid-on-device-inference?api=dev)
- [Chrome Built-in AI](https://developer.chrome.com/docs/ai/built-in)

- Language Model Availability Check

```JS
 let x = await LanguageModel?.availability?.()
// "unavailable": The user's device or requested session options are not supported. The device may have insufficient power or disk space.
// "downloadable": Additional downloads are needed to create a session, which may include an expert model, a language model, or fine-tuning. User activation may be required to call create().
// "downloading": Downloads are ongoing and must complete before you can use a a session.
// "available": You can create a session immediately.

```

## Download the model

- Make sure that the output of availability() is available, downloading, or downloadable.
- If the output is downloadable, start the model download by running:
```JS
await LanguageModel.create();

// You can use the following monitor callback to listen for download progress and make sure that the model is available before making requests:
const session = await LanguageModel.create({
  monitor(m) {
    m.addEventListener("downloadprogress", (e) => {
      console.log(`Downloaded ${e.loaded * 100}%`);
    });
  },
});
```
