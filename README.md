# Effects of Gender-Aware Language on Chatbot Interactions
This repository contains the study materials for the experiment study presented in my seminar paper, which examines how genered language affects user engagement in chatbot interactions. 

## Table of Contents
- [Study Overview](#study-overview)
- [Materials](#materials)
  - [Dialogflow Chatbot](#dialogflow-chatbot)
    - [Webhook](#webhook)
    - [UptimeRobot](#uptimerobot)
  - [Webpage](#webpage)
  - [SoSci Survey](#sosci-survey)
  - [Data Analysis](#data-analysis)
- [License](#license)

## Study Overview
To explore the effects of gender-aware language, a chatbot named StyleBot was developed using Google’s [Dialogflow](https://cloud.google.com/dialogflow/docs) that makes outfit recommendations based on user preferences. Two chatbot versions were created in order to compare language effects: one that addressed participants using gender-specific language like "sir" or "madam" and another that used gender-neutral language. Participants were randomly assigned to chat with one of the two versions and afterwards were asked to fill out a quick post-survey including an adapted short version of the User Engagement Scale. 

## Materials
### Dialogflow Chatbot
The [gender_chatbot](gender_chatbot.zip) and [neutral_chatbot](neutral_chatbot.zip)  contain the Dialogflow chatbots, which can be directly imported into Dialogflow under Settings -> Export and Import -> Import from zip.

#### Webhook
Once the chatbots are setup, webhook needs to be enabled to allow for dynamic responses.

Steps:
1. Upload the three files in [gender_chatbot_webhook](gender_chatbot_webhook) into a separate public repository.
2. Go to [Render](https://render.com) and log in or sign up.
3. Click on "Add new" and "Web Service".
4. Select the repository you created in step 1.
5. Choose a name for the web service and make sure to select the free option under "Instace Type", unless you want to upgrade to a paid version.
6. Click on "Deploy Web Service"
7. Copy the link provided by Render, and go back to Dialogflow.
8. Go to Fulfillment and enable Webhook. Then, paste the copied link into the URL field. Click save.
9. Repeat these steps for the [neutral_chatbot_webhook](neutral_chatbot_webhook) .

#### UptimeRobot
If you want your chatbot to be monitored for enhanced response times, you can use UptimeRobot.

1. Go to [UptimeRobot](https://uptimerobot.com), register or log in.
2. Click on New monitor, select HTTP / website monitoring and paste the link from Render (step 7 from above) into the URL field.
3. Choose a monitor interval and click on Create monitor.

### Webpage
Upload the [chatbot-webpage](chatbot-webpage) file in two separate public repositories (for each chatbot one, if you want to test both chatbots). Make sure to replace the agent-id in the [index.html](chatbot-webpage/index-html) file with your own agent-id (in Dialogflow: Integrations -> Dialogflow Messenger -> Click "Enable" -> Copy the `<script>...</script>` line and paste into index.html)

To test your chatbot on the webpage, go to your webpage repository, click on Settings -> Pages -> Visit site (Or the click on the link "Your site is live at ...")

### SoSci Survey
You can recreate the survey by uploading the provided [survey.seminar19.xml](survey/survey.seminar19.xml) file in [SoSci Survey](https://www.soscisurvey.de).
The survey and corresponding variables can be seen in [Variable View Survey.pdf](survey/VariableViewSurvey.pdf).

### Data Analysis
Jupyter Notebooks for analysis are in the [python_nb](python_nb) folder. They can be uploaded e.g. in [Google Colab](https://colab.google) and modified for the own use. The required data for running the provided notebooks are provided in [suvey_data](survey_data).

## License
The code (Dialogflow bots, webhook, and .ipynb notebooks) are licensed under the [MIT License](MIT_LICENSE.txt).

The survey materials (.pdf, .xml, .html) are licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
