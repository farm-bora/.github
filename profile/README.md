[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Static Badge](https://img.shields.io/badge/Frontend-Code_Engine-blue)](https://farm-bora-frontend.18rsgxmzc56t.eu-gb.codeengine.appdomain.cloud/)
[![Static Badge](https://img.shields.io/badge/Backend-Code_Engine-blue)](https://farm-bora-backend.18rsgxmzc56t.eu-gb.codeengine.appdomain.cloud/api/schema/swagger)
[![Static Badge](<https://img.shields.io/badge/Model_(Gradio)-Code_Engine-blue>)](https://farm-bora-model.18rsgxmzc56t.eu-gb.codeengine.appdomain.cloud/)

# Farm Bora

- [Project summary](#project-summary)
  - [The issue we are hoping to solve](#the-issue-we-are-hoping-to-solve)
  - [How our technology solution can help](#how-our-technology-solution-can-help)
  - [Our idea](#our-idea)
- [Technology implementation](#technology-implementation)
  - [IBM AI service(s) used](#ibm-ai-services-used)
  - [Other IBM technology used](#other-ibm-technology-used)
  - [Solution architecture](#solution-architecture)
- [Presentation materials](#presentation-materials)
  - [Solution demo video](#solution-demo-video)
  - [Project development roadmap](#project-development-roadmap)
- [Additional details](#additional-details)
  - [How to run the project](#how-to-run-the-project)
  - [Live demo](#live-demo)
- [About this Project](#about-this-project)
  - [Authors](#authors)
  - [License](#license)
  - [Acknowledgments](#acknowledgments)

## Project summary

### The issue we are hoping to solve

Plant diseases are a major threat to crop yield and food security. Farmers often struggle when trying identify diseases in their crops, leading to reduced yields and economic losses. Access to specialists who can do this diagnosis is limited especially in developing nations, which further aggravates this problem.

### How our technology solution can help

FarmBora is a tool enables farmers to diagnose plant diseases from images while giving actionable insights.

### Our idea

#### How it works

First, you upload an image of a plant leaf through our frontend. The AI model then gives predictions on what the leaf might have. The returned results are also clickable, leading you to detailed pages with information on how to deal with the predicted disease.

#### Unique Value Proposition

- The model has been trained on a dataset which has 14 plants and up to 26 diseases.
- The train and test accuracies of the model are **95%** and **97%** respectively.
- This performant model is exposed to users in a user friendly frontend which makes the model accessible.
- FarmBora doesn't stop at diagnosis. It also provides actionable insights, suggesting remedies and treatment options for the detected diseases.
- To make it even more accessible, we've developed an API that can be used to connect our AI model to a range of farming equipment and management systems, and this will form the basis for future work.

## Technology implementation

### IBM AI service(s) used

- [Watson Text to Speech](https://cloud.ibm.com/catalog/services/text-to-speech) - To convert the actionable insights from text format to audio format that a farmer can then play and listen to.

### Other IBM technology used

- [Code Engine](https://www.ibm.com/products/code-engine) - This hosts the frontend, the api backend, and the model.

### Solution architecture

![Solution Architecture](https://raw.githubusercontent.com/farm-bora/.github/main/profile/media/architecture.drawio.png)

1. The user uploads an image of a plant leaf.
2. The frontend passes it to the backend which also passes it to the model.
3. The returned predictions from the model are cleaned up and links to details of the diseases are added to the response by the **backend**.
4. The prediction results are show to the user from the **frontend**.

## Presentation materials

### Solution demo video

[Click on the image below to play: ![Watch the video](https://raw.githubusercontent.com/farm-bora/.github/main/profile/media/video-picture.png)](https://www.youtube.com/watch?v=qeEEyPRc_-0)

### Project development roadmap

The project currently does the following things.

- An image classification model has been trained
- An API for accessing this model has been created
- A frontend that exposes the above two has been created.

In the future we plan to...

- Add user authentication/authorization
- Add OpenAI's ChatGPT through LangChain
- Further improve the model's performance
- Integrate the model into farm equipment

See below for our proposed schedule on next steps after Call for Code 2023 submission.

![Roadmap](https://raw.githubusercontent.com/farm-bora/.github/main/profile/media/roadmap.png)

## Additional details

### How to run the project

#### Frontend

Clone the frontend then:

```shell
$ npm ci
$ npm run dev
```

#### Backend

Clone the backend then:

```shell
$ python -m venv env
$ source env/bin/activate
$ pip install -r requirements.txt
$ python manage.py runserver
```

#### AI Model

Clone the model then:

```shell
$ python -m venv env
$ source env/bin/activate
$ pip install -r requirements.txt
$ python app.py
```

### Live demo

You can find a running system to test at...

- https://farm-bora-frontend.18rsgxmzc56t.eu-gb.codeengine.appdomain.cloud/

---

## About this project

### Authors

- **Timothy Karani** - [c3n7](https://github.com/c3n7)

### License

This project is licensed under the MIT License.

### Acknowledgments

- Based on [Billie Thompson's README template](https://gist.github.com/PurpleBooth/109311bb0361f32d87a2).
