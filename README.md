# finbot_data
Sharing dataset for finbot

# References

1. [Blog post](https://paulabartabajo.substack.com/p/how-to-generate-financial-q-and-a)
2. [Dataset analysis](https://github.com/iusztinpaul/hands-on-llms/tree/main/dataset_analysis)
3. [Code IPynb](https://github.com/iusztinpaul/hands-on-llms/blob/main/dataset_analysis/prompts_eda.ipynb)

# Data generation
Following are the stuff that I used to generate data. I used a similar method mentioned in the blog post where I used GPT-4 to generate the synthetic data (Assuming that this would work.). Following is the information related to this.

## Environment
1. **Platform** : OpenAi playground
2. **Model** : gpt4o-2024-08-06
3. **Temperature** : 0
4. **Max token** : 16836

## System prompt
You are an expert in giving finance advices. I want to create a course and there, my students might ask me questions that might be regarding the real time financial things happening in the industry. Your help is requested in creating all possible questions that can come from the students.

## User prompt
Can you generate 100 more examples following the same pattern? there shall be an about me, context section and a response. the response shall be well thought out and shall not contain any errors or mistakes. please remember that I deal with many types of clients with different experiences in different fields or no experience at all. make sure this veriety is reflected in the about me.  Following is the sample JSON sample for the same.
```
 {
        "about_me": "I am a 28 year old marketing professional.\nI have some savings and I'm interested in crypto investments.\nIs Bitcoin a good investment option?",
        "context": "El Salvador adopts Bitcoin as legal tender.\nRecent fluctuations in Bitcoin's price.\nRenewed interest from institutional investors.",
        "response": "\nYes, Bitcoin is a good investment option. The recent news of El Salvador adopting Bitcoin as legal tender has increased its demand and price, and institutional investors are showing renewed interest in the cryptocurrency. This makes it a good option for long-term investments, as it is likely to continue to increase in value over time."
    },
    {
        "about_me": "I am a 35 year old small business owner.\nI have a moderate risk tolerance and want to diversify my investments.\nShould I consider investing in renewable energy stocks?",
        "context": "Government announces increased focus on renewable energy.\nRenewable energy sector experiences consistent growth.\nFluctuations in oil prices impact energy market dynamics.",
        "response": "\nYes, you should consider investing in renewable energy stocks. The government's increased focus on renewable energy and the sector's consistent growth make it a good long-term investment. Additionally, fluctuations in oil prices can create opportunities for investors to buy low and sell high."
    },
    {
        "about_me": "I am a 45 year old IT professional nearing retirement.\nI am looking for stable investment options for my retirement funds.\nAre dividend-paying stocks a good choice for me?",
        "context": "Several blue-chip companies announce dividend increases.\nHistorical performance of dividend-paying stocks during economic downturns.\nCurrent low interest rate environment affects traditional savings options.",
        "response": "\nYes, dividend-paying stocks are a good choice for you. They provide a steady income stream and have historically outperformed other investments during economic downturns. Furthermore, with the current low interest rate environment, dividend-paying stocks offer a more attractive return than traditional savings options."
    },
    {
        "about_me": "I am a 29 year old freelance writer with variable income.\nI want to start investing but I'm unsure where to begin.\nAre robo-advisors a suitable option for me?",
        "context": "Robo-advisors gain popularity for their automated investment strategies.\nLow fees and accessibility make robo-advisors appealing for beginners.\nImportance of aligning investment choices with risk tolerance and financial goals.",
        "response": "\nRobo-advisors can be a great option for beginners, as they offer low fees and automated investment strategies. However, it is important to make sure that your investment choices are aligned with your risk tolerance and financial goals. Before investing, take the time to assess your financial situation and determine what type of investments are best suited for you. This will help you make the most of your investments and ensure that you are making the right decisions for your future."
    },
```

## Issues faced
Got the message - ```Request too large for gpt-4o in organization org-2vFFW3Co1AOMPIixeDmLtMJu on tokens per min (TPM): Limit 30000, Requested 31391. The input or output tokens must be reduced in order to run successfully. Visit https://platform.openai.com/account/rate-limits to learn more.``` and solved it after deleting one response

Most of the profiles were above 30


