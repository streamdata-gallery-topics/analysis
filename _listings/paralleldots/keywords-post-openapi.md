---
swagger: "2.0"
x-collection-name: ParallelDots
x-complete: 0
info:
  title: ParallelDots Keywords
  description: |-
    # Introduction
    What does your API do?

    Keyword Generator are powerful tools in text analysis that can be used to index data, generate tag clouds and accelerate the searching time. It generates an extensive list of relevant keywords and phrases to make research more context focussed.

    # Overview
    Things that the developers should know about

    The API accepts the input parameters as form-data.

    Response will be in JSON as shown below:

    ```
    {
        "keywords": [
            {
                "keyword": "Cristiano Ronaldo",
                "confidence_score": 0.887065
            },
            {
                "keyword": "Principality Stadium",
                "confidence_score": 0.903289
            },
            {
                "keyword": "Cardiff last",
                "confidence_score": 0.806802
            },
            {
                "keyword": "couple",
                "confidence_score": 0.69036
            },
            {
                "keyword": "hours",
                "confidence_score": 0.984956
            },
            {
                "keyword": "Real Madrid win",
                "confidence_score": 0.812151
            }
        ],
        "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions"
    }
    ```

    # Authentication
    What is the preferred way of using the API?

    An API key is required to be sent as a parameter to authenticate your requests.


    # Rate limit
    Is there a limit to the number of requests an user can send?

    There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
  version: 1.0.0
host: apis.paralleldots.com
basePath: /v3
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /emotion:
    post:
      summary: Emotion
      description: |-
        # Introduction
        What does your API do?

        Sometimes the three classes of sentiment (positive, negative and neutral) are not sufficient to understand the nuances regarding the underlying tone of a sentence. Our Emotion Analysis classifier is trained on our proprietary dataset and tells whether the underlying emotion behind a message is: Happy, Sad, Angry, Fearful, Excited, Funny or Indifferent.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.Languages supported are German (de), French (fr), Dutch (nl), Italian (it), Spanish (es), Chinese (zh), Portuguese (pt), Japanese (ja), Indonesian (id), Thai (th), Danish (da), Finish (fi)

        Response will be in JSON as shown below:

        ```
        {
            "emotion": {
                "probabilities": {
                    "angry": 0.376,
                    "indifferent": 0.189,
                    "sad": 0.381,
                    "excited": 0.014,
                    "happy": 0.04
                },
                "emotion": "sad"
            },
            "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions"
        }

        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: EmotionPost
      x-api-path-slug: emotion-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: lang_code
      - in: formData
        name: text
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Emotion
      - Analysis
  /similarity:
    post:
      summary: Semantic Similarity
      description: |-
        # Introduction
        What does your API do?

        Semantic Analysis API helps users cluster similar articles by understanding the relatedness between different content and streamlines research by eliminating redundant text contents.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.

        Response will be in JSON as shown below:

        ```
        {
          "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions",
          "actual_score": 0.842932,
          "normalized_score": 4.931469
        }

        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: SimilarityPost
      x-api-path-slug: similarity-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: text1
      - in: formData
        name: text2
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Semantic
      - Similarity
      - Analysis
  /keywords:
    post:
      summary: Keywords
      description: |-
        # Introduction
        What does your API do?

        Keyword Generator are powerful tools in text analysis that can be used to index data, generate tag clouds and accelerate the searching time. It generates an extensive list of relevant keywords and phrases to make research more context focussed.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.

        Response will be in JSON as shown below:

        ```
        {
            "keywords": [
                {
                    "keyword": "Cristiano Ronaldo",
                    "confidence_score": 0.887065
                },
                {
                    "keyword": "Principality Stadium",
                    "confidence_score": 0.903289
                },
                {
                    "keyword": "Cardiff last",
                    "confidence_score": 0.806802
                },
                {
                    "keyword": "couple",
                    "confidence_score": 0.69036
                },
                {
                    "keyword": "hours",
                    "confidence_score": 0.984956
                },
                {
                    "keyword": "Real Madrid win",
                    "confidence_score": 0.812151
                }
            ],
            "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions"
        }
        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: KeywordsPost
      x-api-path-slug: keywords-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: text
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Keywords
      - Analysis
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---