# annotations

Annotations are stored in git based on container [name](https://github.com/jptmoore/annotations/tree/master/demo) which is broken down into its [main](https://github.com/jptmoore/annotations/tree/master/demo/main) details and a [collection](https://github.com/jptmoore/annotations/tree/master/demo/collection) of individual annotations. 

This repository is served by [Miiify](https://github.com/nationalarchives/miiify) running on a [k8s](https://github.com/nationalarchives/miiify/tree/main/k8s) deployment over at miiify.rocks

```sh
curl -s miiify.rocks/annotations/demo/ | jq
```

```json
{
  "@context": [
    "http://www.w3.org/ns/anno.jsonld",
    "http://www.w3.org/ns/ldp.jsonld"
  ],
  "id": "https://127.0.0.1:5555/annotations/demo/",
  "type": [
    "BasicContainer",
    "AnnotationCollection"
  ],
  "label": "A demo container",
  "created": "2022-01-08T17:24:19Z",
  "modified": "2022-01-08T17:24:43Z",
  "total": 1,
  "first": {
    "id": "https://127.0.0.1:5555/annotations/demo?page=0",
    "type": "AnnotationPage",
    "items": [
      {
        "type": "Annotation",
        "target": {
          "source": "http://localhost:8080/img/desk.60fd7be5.jpg",
          "selector": {
            "value": "xywh=pixel:254,608,117,130",
            "type": "FragmentSelector",
            "conformsTo": "http://www.w3.org/TR/media-frags/"
          }
        },
        "id": "https://127.0.0.1:5555/annotations/demo/9684d9ee-fc86-470d-9223-9a6cf3d0e2a2",
        "created": "2022-01-08T17:24:43Z",
        "body": [
          {
            "type": "TextualBody",
            "value": "Alexa",
            "purpose": "commenting",
            "creator": {
              "name": "miiiy.rocks"
            },
            "created": "2022-01-08T17:24:39.000Z",
            "modified": "2022-01-08T17:24:39.866Z"
          },
          {
            "type": "TextualBody",
            "value": "Echo",
            "purpose": "tagging",
            "creator": {
              "name": "miiiy.rocks"
            },
            "created": "2022-01-08T17:24:40.975Z",
            "modified": "2022-01-08T17:24:42.124Z"
          }
        ],
        "@context": "http://www.w3.org/ns/anno.jsonld"
      }
    ]
  }
}
```