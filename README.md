## Prerequisites

1. Sign up for an [IBM Cloud account](https://cloud.ibm.com/registration/).
1. Download the [IBM Cloud CLI](https://cloud.ibm.com/docs/cli/index.html#overview).
1. Create an instance of the Personality Insights service and get your credentials:
    - Go to the [Personality Insights](https://cloud.ibm.com/catalog/services/personality-insights) page in the IBM Cloud Catalog.
    - Log in to your IBM Cloud account.
    - Click **Create**.
    - Click **Show** to view the service credentials.
    - Copy the `apikey` value.
    - Copy the `url` value.

## Configuring the application

1. In the application folder, copy the *.env.example* file and create a file called *.env*

    ```
    cp .env.example .env
    ```

2. Open the *.env* file and add the service credentials that you obtained in the previous step.

    Example *.env* file that configures the `apikey` and `url` for a Personality Insights service instance hosted in the US East region:

    ```
    PERSONALITY_INSIGHTS_IAM_APIKEY=X4rbi8vwZmKpXfowaS3GAsA7vdy17Qh7km5D6EzKLHL2
    PERSONALITY_INSIGHTS_URL=https://gateway-wdc.watsonplatform.net/personality-insights/api
    ```
### Setting Up the Twitter Application

1. [Create a Twitter application](https://apps.twitter.com/app/new).

2. Add your application's callback URL:
  - For Bluemix environment: `<application-name>.mybluemix.net/auth/twitter/callback`
  - For Local environment: `http://localhost:3000/auth/twitter/callback`

3. Update the `.env` file and add your twitter application credentials:

  ```none
  TWITTER_CONSUMER_KEY=<consumer-key>
  TWITTER_CONSUMER_SECRET=<consumer-secret>
  ```

## Running locally

1. Install the dependencies

    ```
    npm install
    ```

1. Run the application

    ```
    npm start
    ```

1. View the application in a browser at `localhost:3000`

## Directory structure

```none
.
├── app.js                       // express entry point
├── config                       // express configuration
│   ├── error-handler.js
│   ├── express.js
│   ├── i18n.js
│   ├── passport.js
│   └── security.js
├── helpers                      // utility modules
│   ├── personality-insights.js
│   └── twitter-helper.js
├── i18n                         // internationalization
│   ├── en.json
│   ├── es.json
│   └── ja.json
├── manifest.yml
├── package.json
├── public
│   ├── css
│   ├── data                     // sample text and tweets
│   ├── fonts
│   ├── images
│   └── js
├── router.js                   // express routes
├── server.js                   // application entry point
├── test
└── views                       // ejs views
```

## License

This sample code is licensed under Apache 2.0.  
Full license text is available in [LICENSE](LICENSE).