# msn-news-skill
# Welcome to the MSN News Skill, where you can access the latest news as you can.
# Here's the code:


;
  const Alexa = require('ask-sdk-core');

const skillBuilder = Alexa.SkillBuilders.custom();

const FlashBriefingHandler = {
    canHandle(handlerInput) {
        const request = handlerInput.requestEnvelope.request;
        return request.type === 'LaunchRequest' || 
               (request.type === 'IntentRequest' && request.intent.name === 'GetFlashBriefingIntent');
    },
    handle(handlerInput) {
        const speechText = 'Good evening. Welcome back to MSN News, which I'm going to see the latest news. Today is 2024-08-25. The Israel Defense Forces says it has launched preemptive strikes on Hezbollah in Lebanon ahead of an expected major missile and drone attack on Israel. Israeli Defence Minister Yoav Gallant declares an "emergency situation" in Israel for the next 48 hours due to the "special situation in the home front". At least five people, including three minors, are killed and 13 others are wounded in an overnight Ukrainian strike on Belgorod, Russia. At least four people are killed and 37 others are injured in overnight Russian attacks in northern and eastern Ukraine. A British safety adviser working for Reuters is killed and two other journalists are injured in a Russian ballistic missile strike on their hotel in Kramatorsk, Donetsk Oblast. President of Ukraine Volodymyr Zelenskyy publicly presents the Ukrainian-produced Palianytsia rocket drone and loitering munition, intended to serve as the Ukrainian counterpart to the Russian ZALA Kub-BLA after a year and a half of development. At least 71 people are killed and 112 people are injured in Israeli attacks in the Gaza Strip. Nearly 200 people are killed and at least 140 people are injured in an attack by the al-Qaeda-linked Jama'at Nasr al-Islam wal-Muslimin jihadist organization in Barsalogho Department, Burkina Faso. German Police detain a 26-year-old Syrian asylum seeker, who has ties to the Islamic State, as the suspect of the stabbing attack in Solingen, NRW, Germany. He is charged with three counts of murder, as well as attempted murder, dangerous bodily harm and membership of a terrorist organisation abroad. Two police officers are killed and three others are injured in an attack in Abuja, Nigeria. A police spokesperson says that the proscribed Islamic Movement of Nigeria was responsible for the attack. Pope Francis condemns the Government of Ukraine's banning of the Moscow-linked Ukrainian Orthodox Church and other Russia-linked religious groups as infringing on Ukrainian civilians' civil right to religious freedom. At least two people are killed in wildfires in São Paulo state, Brazil. Thirteen people are killed and 20 others are injured in a mudslide near the Big Buddha in Phuket, Thailand. Twenty-two people are killed when a bus plunges into a ravine in Pakistan-administered Kashmir. Twelve others are killed in a separated bus crash on the Makran Coastal Highway in the Balochistan Province. At least thirteen people die and 14 others remain missing after a boat carrying Ethiopian and Yemeni migrants from Djibouti sinks off the coast of Taiz Governorate, Yemen. Four people are injured in a mass stabbing in Sydney, Australia, with the suspect being taken into custody. That's all for it. See you in the next hour, for, more MSN News. Goodbye!';
        
        return handlerInput.responseBuilder
            .speak(speechText)
            .getResponse();
    }
};

exports.handler = skillBuilder
    .addRequestHandlers(
        FlashBriefingHandler
    )
    .lambda();
