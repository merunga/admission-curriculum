# Admission Curriculum

This repository holds the topics required for the admission process in spanish and portuguese.

## Install

`npm install`

---
## Set Typeform IDs

_Note:_ Before going ahead, have a look at [the admission documentation about typeform](https://github.com/Laboratoria/admission.laboratoria.la#typeform)

1. Copy `.typeformrc.example` file to `.typeformrc`
2. Add all typeform ids inside `.typeformrc` file according the language and environment.

The Typeform ids _required_ are:

```json
  "TYPEFORM_ID_BASE_LINE_QUESTIONNAIRE": "your-typeformid",
  "TYPEFORM_ID_TESTS_READING": "your-typeformid",
  "TYPEFORM_ID_TESTS_LOGIC": "your-typeformid",
  "TYPEFORM_ID_TESTS_PERSONALITY": "your-typeformid",
```

> **Heads-up:** There are three environments available (development, staging and production) for different purposes and two languages (es-ES, pt-BR), make sure you are setting up the right ones.

---
## Build 🏗

> **Important:** Make sure you are building the right content for your environment and language

You can pass 2 environment variables: `env`, `locale`

**`env`** : `development`, `staging`, `production`
**`locale`**: `es-ES`, `pt-BR`

By default `locale` takes the value `es-ES`

**For instance:**

`npm run build -- --env=production --locale=pt-BR`

The final content will be saved in `build/admission-pt.json` file

---
## Testing 🧪

- To validate the course content `npm run validate`
- To run markdown linter `npm run mdlint`
- To run tests and pretest `npm run test`

---
## Upload 🚀

You can used any tool to upload the built topic (course), e.g: [Postman](https://www.postman.com/), [Insomnia](https://insomnia.rest/) or if you love cli tools 🤟, I recommend using this [httpie](https://httpie.io/)

_Note:_ You will need a json-token to authenticate before uploading. Get it by using `POST */auth` endpoint

__To production__

`POST https://api.laboratoria.la/topics`

__To staging__

`POST https://laboratoria-la-staging.firebaseapp.com/topics`
