# LibreTranslate

[Try it online!](https://libretranslate.com) | [API Docs](https://libretranslate.com/docs) | [Community Forum](https://community.libretranslate.com/)

[![Python versions](https://img.shields.io/pypi/pyversions/libretranslate)](https://pypi.org/project/libretranslate) [![Run tests](https://github.com/LibreTranslate/LibreTranslate/workflows/Run%20tests/badge.svg)](https://github.com/LibreTranslate/LibreTranslate/actions?query=workflow%3A%22Run+tests%22) [![Publish to DockerHub](https://github.com/LibreTranslate/LibreTranslate/workflows/Publish%20to%20DockerHub/badge.svg)](https://hub.docker.com/r/libretranslate/libretranslate) [![Publish to GitHub Container Registry](https://github.com/LibreTranslate/LibreTranslate/workflows/Publish%20to%20GitHub%20Container%20Registry/badge.svg)](https://github.com/LibreTranslate/LibreTranslate/actions?query=workflow%3A%22Publish+to+GitHub+Container+Registry%22) [![Awesome Humane Tech](https://raw.githubusercontent.com/humanetech-community/awesome-humane-tech/main/humane-tech-badge.svg?sanitize=true)](https://github.com/humanetech-community/awesome-humane-tech)

Free and Open Source Machine Translation API, entirely self-hosted. Unlike other APIs, it doesn't rely on proprietary providers such as Google or Azure to perform translations. Instead, its translation engine is powered by the open source [Argos Translate][argo] library.

![image](https://user-images.githubusercontent.com/64697405/139015751-279f31ac-36f1-4950-9ea7-87e76bf65f51.png)


[Try it online!](https://libretranslate.com) | [API Docs](https://libretranslate.com/docs)

## API Examples


### Plain Text

Request:

```javascript
const res = await fetch("https://libretranslate-fzoby.run-eu-central1.goorm.io/", {
	method: "POST",
	body: JSON.stringify({
		q: "Hello!",
		source: "en",
		target: "es"
	}),
	headers: { "Content-Type": "application/json" }
});

console.log(await res.json());
```

Response:

```javascript
{
    "translatedText": "¡Hola!"
}
```

### HTML (beta)

Request:

```javascript
const res = await fetch("https://libretranslate-fzoby.run-eu-central1.goorm.io/", {
	method: "POST",
	body: JSON.stringify({
		q: '<p class="green">Hello!</p>',
		source: "en",
		target: "es",
		format: "html"
	}),
	headers: { "Content-Type": "application/json" }
});

console.log(await res.json());
```

Response:

```javascript
{
    "translatedText": "<p class=\"green\">¡Hola!</p>"
}
```
