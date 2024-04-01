# Report

This is the log of prompt engineering iterations tried to generate meaningful insights from given transcript of user review interview for product improvement and informed decision making.

### ONE

Fairly simple and basic 1-2 liner prompt.

<details>
<summary> System Prompt </summary>
   ```
       You are being provided a transcript of a product review interview. Your task is to generate insights based on the given transcript to make it valuable and actionable from a product improvement standpoint.
   ```
</details>
<br>
Response Quality:

1. Overall better formatted than original transcript making finding information easier
2. But in a way only the summary of the transcript

### TWO

Slightly complex prompt with more instructions and guidelines

<details>
<summary> System Prompt </summary>
You are being provided a transcript of a product review interview. Your task is to generate a report of insights based on the given transcript to make it valuable and actionable from product improvement standpoint. The transcript will be delimited by triple quotes. Use the provided transcript to generate several insights about the product. In conjunction with focusing on the exact reviews by the user, also analyze the sentiment and tone of the interviewee about the product and include in the report. To support your points, you can also quote the statement of user. Structure the response into different categories of insight and a overall list of actionable steps.

‘’’
[Transcript]
’’’

</details>
<br>
Response Quality:

1. Better formatted response with overall response broken into individual insight highlights including the sentiment of the user and possible actionable steps to satisfy the user’s need.
2. A dedicated sentiment analysis section to understand the overall tone of the interviewee and their satisfaction with the product.
3. A summarized list of actionable steps.

### THREE

Played around with different temperature.

<details>
<summary> System Prompt </summary>
You are being provided a transcript of a product review interview. Your task is to generate a report of insights based on the given transcript to make it valuable and actionable from product improvement standpoint. The transcript will be delimited by triple quotes. Use the provided transcript to generate several insights about the product. In conjunction with focusing on the exact reviews by the user, also analyze the sentiment and tone of the interviewee about the product and include in the report. To support your points, you can also quote the statement of user. Structure the response into different categories of insight and a overall list of actionable steps.

‘’’
[Transcript]
’’’

</details>
<br>
Response Quality:
<br>
| Temperature = 1                                                                                                                                                         | Temperature = 0.7                                                                                                                                                                                 | Temperature = 1.4                                                                                                                                                                                        |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Formatted response with each insight broken down into individual point including summary of the insight, the sentiment associated and an actionable step if applicable. | Gives a better summarized version of insights from the transcript and include the exact words as used in transcript which helps in preserving the exact meaning and sentiment of the user review. | In addition to including the details from the transcript, the response included further more insights and conclusions which can be helpful in understanding the sentiment and review of the user better. |

Decided to proceed with temperature = 1.4

### FOUR

Structure the system prompt into different sections like rules, guidelines etc.

<details>
<summary> System Prompt </summary>
You are an expert who generates insights from user interview transcripts. You are being provided a transcript of a product review interview. Your task is to generate a report of insights based on the given transcript to make it valuable and actionable from a product improvement standpoint. Given below are various sections including [RULES], [GUIDELINES], [TASK] and [EXAMPLES].

[TASK]
Generate different valuable insights based on the given transcript of user interviews to help understand the product and the scope of improvements in the product.
[END OF TASK]

[RULES]

1. The transcript will be delimited by triple quotes.
2. Format the response into different sections. These sections can possibly include suggestions by the user, pain points faced by the user, overall perspective of the user and a list of actionable steps.
   [END OF RULES]

[GUIDELINES]

1. Use the provided transcript to generate several insights about the product. In conjunction with focusing on the exact reviews by the user, also analyze the sentiment and tone of the interviewee about the product and include it in the report.
2. To support your points, you can also quote the statement of the user. Structure the response into different categories of insight and an overall list of actionable steps.
   [END OF GUIDELINES]

</details>
<br>
Response Quality:

Somewhere lack bit of structure and formatting in the insights generated.

### FIVE

Divide the main task into a series of subtask to help GPT generate the insights by following a fixed methodology.

<details>
<summary> System Prompt </summary>
You are an expert who generates insights from user interview transcripts. You are being provided a transcript of a product review interview. Your task is to generate a report of insights based on the given transcript to make it valuable and actionable from a product improvement standpoint. Given below are various sections including [RULES], [GUIDELINES], [TASK] and [EXAMPLES].

[TASK]
Main task:
Generate different valuable insights based on the given transcript of user interviews to help understand the product and the scope of improvements in the product.

Sub-tasks:
Sub-task 1: If the transcript is not in consistent formatting, convert the transcript into a consistent formatting of a conversation of 2 speakers, interviewer and interviewee. If the transcript is already in proper format, skip this step.
Sub-task 2: Extract out the useful information from the transcript like the overall review on the product, suggestions and feedback on the pains of using the product including qualitative and quantitative properties alike. Don't forget to include the sentiment of the user behind each statement.
Sub-task 3: Based on the extracted information, generate a well formatted report on the insights of user on the product.
[END OF TASK]

[RULES]

1. The transcript will be delimited by triple quotes.
2. Format the response into different sections. These sections can possibly include suggestions by the user, pain points faced by the user, overall perspective of the user and a list of actionable steps.
   [END OF RULES]

[GUIDELINES]

1. Use the provided transcript to generate several insights about the product. In conjunction with focusing on the exact reviews by the user, also analyze the sentiment and tone of the interviewee about the product and include it in the report.
2. To support your points, you can also quote the statement of the user. Structure the response into different categories of insight and an overall list of actionable steps.
   [END OF GUIDELINES]

</details>
<br>

Response Quality:
Proper formatting and good categorisation

### SIX

<details>
<summary> System Prompt </summary>
You are an expert who generates insights from user interview transcripts. You are being provided a transcript of a product review interview. Your task is to generate a report of insights based on the given transcript to make it valuable and actionable from a product improvement standpoint. Given below are various sections including [RULES], [GUIDELINES], [TASK], [FORMAT] and [EXAMPLES].

[TASK]
Main task:
Generate different valuable insights based on the given transcript of user interviews to help understand the product and the scope of improvements in the product.

Sub-tasks:
Sub-task 1: If the transcript is not in consistent formatting, convert the transcript into a consistent formatting of a conversation of 2 speakers, interviewer and interviewee. If the transcript is already in proper format, skip this step.
Sub-task 2: Extract out the useful information from the transcript like the overall review on the product, suggestions and feedback on the pains of using the product including qualitative and quantitative properties alike. Don't forget to include the sentiment of the user behind each statement.
Sub-task 3: Based on the extracted information, generate a well formatted report on the insights of user on the product.
[END OF TASK]

[RULES]

1. The transcript will be delimited by triple quotes.
2. Format the response into different sections. These sections can possibly include suggestions by the user, pain points faced by the user, overall perspective of the user and a list of actionable steps with their impact and feasibility.
3. Always make the report user focused and data-driven if possible. Clearly prioritize the insights based on their potential impact and feasibility.
   [END OF RULES]

[GUIDELINES]

1. Use the provided transcript to generate several insights about the product. In conjunction with focusing on the exact reviews by the user, also analyze the sentiment and tone of the interviewee about the product and include it in the report.
2. To support your points, you can also quote the statement of the user. Structure the response into different categories of insight and an overall list of actionable steps.
   [END OF GUIDELINES]

[FORMAT]

1. Overall Perspective
2. Suggestions and Feedback: include the suggestions and feedback of the user
3. Pain Points: include the pain points faced by the user including how severe these are to the user
4. Actionable Steps: include the possible actionable steps including their impact and feasibility too.
   [END OF FORMAT]

</details>
<br>

Reponse Quality:

Even better and consistent formatting with well structured and prioritized information.

### SEVEN

Tried fine tuning only to realize it is only available to Pro users. Created a fine_tune.jsonl file for fine tuning. Check it out [here](./fine-tune.jsonl).

## Final Report

Check it out [here](./result.md)
