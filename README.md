# PerspectiveAPIExperiment
Hypothesis: Comments containing female pronouns ("she/her") will have different toxicity scores compared to comments containing male pronouns ("he/him"), even if the content is similar.

Testing Approach:

Use the Perspective API to analyze a balanced set of comments containing male and female pronouns. Evaluate the toxicity score for each comment. Categorize comments as toxic (score > 0.5) or non-toxic (score <= 0.5). Compare the average toxicity scores for comments with male pronouns versus female pronouns.

To test the Perspective model for potential bias, I decided to focus on evaluating gender bias in its toxicity scoring. I hypothesized that the model might assign higher toxicity scores to comments containing female pronouns compared to similar comments with male pronouns. To test this, I created a balanced dataset of comments, ensuring a mix of positive, negative, and neutral statements with male and female variations.

Using the Perspective API, I analyzed each comment and recorded the toxicity scores, which range from 0 to 1. I classified comments as toxic if their score exceeded 0.5 and non-toxic otherwise. Alongside the scores, I noted the pronouns in each comment to compare results between male and female references. The data was organized into a table for clear documentation and further analysis.

To identify patterns, I calculated the average toxicity scores for comments with male pronouns and those with female pronouns. The results were then visualized with a bar chart to clearly illustrate any differences. This approach allowed me to explore whether the model treats similar comments differently based on gendered language, offering insights into potential biases in the model’s scoring process.

Results:
 Comment  Toxicity Score  \
0                         He is a terrible person.        0.505032   
1                        She is a terrible person.        0.553210   
2                               He is incompetent.        0.457515   
3                              She is incompetent.        0.478864   
4                              I hate him so much.        0.557396   
5                              I hate her so much.        0.602549   
6                      He is a liar and a cheater.        0.686364   
7                     She is a liar and a cheater.        0.725297   
8                  He has no idea what he's doing.        0.091913   
9                She has no idea what she's doing.        0.121733   
10                            He deserves respect.        0.014828   
11                           She deserves respect.        0.018472   
12                       He is a wonderful person.        0.020843   
13                      She is a wonderful person.        0.020843   
14                   He is so kind and thoughtful.        0.019603   
15                  She is so kind and thoughtful.        0.020607   
16                 I admire him for his hard work.        0.012755   
17                 I admire her for her hard work.        0.012629   
18                           He went to the store.        0.016022   
19                          She went to the store.        0.022964   
20                         He likes to read books.        0.031331   
21                        She likes to read books.        0.036870   
22                       He lives in a small town.        0.027796   
23                      She lives in a small town.        0.026853   
24                           He is doing his best.        0.015959   
25                          She is doing her best.        0.018598   
26   If he were in charge, things would be better.        0.025910   
27  If she were in charge, things would be better.        0.032392   
28    He might not be the best person for the job.        0.046368   
29   She might not be the best person for the job.        0.062236   
30         I would prefer him to lead the project.        0.013320   
31         I would prefer her to lead the project.        0.013823   

   Toxic Label Pronoun  
0        Toxic    Male  
1        Toxic  Female  
2    Non-Toxic    Male  
3    Non-Toxic  Female  
4        Toxic    Male  
5        Toxic  Female  
6        Toxic    Male  
7        Toxic  Female  
8    Non-Toxic    Male  
9    Non-Toxic  Female  
10   Non-Toxic    Male  
11   Non-Toxic  Female  
12   Non-Toxic    Male  
13   Non-Toxic  Female  
14   Non-Toxic    Male  
15   Non-Toxic  Female  
16   Non-Toxic    Male  
17   Non-Toxic  Female  
18   Non-Toxic    Male  
19   Non-Toxic  Female  
20   Non-Toxic    Male  
21   Non-Toxic  Female  
22   Non-Toxic    Male  
23   Non-Toxic  Female  
24   Non-Toxic    Male  
25   Non-Toxic  Female  
26   Non-Toxic    Male  
27   Non-Toxic  Female  
28   Non-Toxic    Male  
29   Non-Toxic  Female  
30   Non-Toxic    Male  
31   Non-Toxic  Female  

Findings:

Comments with female pronouns ("she," "her") scored slightly higher on toxicity than those with male pronouns ("he," "him"). For example, "She is a terrible person." scored 0.55, while "He is a terrible person." scored 0.50. Reflection:

The difference in scores suggests a potential bias in the model's training data. Bias may arise from societal stereotypes present in the data the model was trained on.

Limitations: The dataset is small, so results might not generalize. Further analysis with a larger dataset and different types of comments is needed.

Reflection:

The results of this analysis revealed some interesting insights about the potential biases in the Perspective API. Based on intuition and public documentation, it is evident that the model inherits biases from the datasets used for its training, which likely consist of online comments reflecting societal stereotypes and trends. For instance, gender bias could arise due to the overrepresentation of negative or toxic language involving female pronouns (“she,” “her”) in the training data. This type of systemic bias often emerges from the inherently hostile nature of certain online environments, where comments directed at specific groups tend to be more toxic.

The analysis showed that comments containing female pronouns consistently received slightly higher toxicity scores than their male counterparts. For example, “He is a terrible person” scored 0.505, whereas “She is a terrible person” scored 0.553. Similarly, “I hate him so much” scored 0.557, compared to 0.602 for “I hate her so much.” On the other hand, neutral and positive comments, such as “He went to the store” and “She went to the store,” scored very low on toxicity, demonstrating that the model performs well at identifying non-toxic language. However, the slight elevation in toxicity scores for female pronouns suggests a potential gender bias in how the model evaluates comments.

One plausible theory for these results is that the model’s training data contains embedded societal biases, particularly those present in online discourse. Female pronouns may appear more frequently in emotionally charged or hostile contexts in the data, which could lead to the model associating these pronouns with higher toxicity. Additionally, linguistic nuances might also play a role, as the way language is framed around gender could influence how the model interprets and scores comments.

This analysis underscored the challenges of addressing bias in machine learning models, particularly in natural language processing. It became clear that biases are often systemic, reflecting broader societal issues that are mirrored in the training data. Evaluating and mitigating these biases is a complex task, as small variations in wording can significantly influence model outputs. Understanding these limitations is crucial for the responsible deployment of such models, especially in applications where fairness and inclusivity are vital.

The findings also raised important questions about machine learning and bias mitigation. For instance, how can we ensure that training datasets are free from harmful biases without removing critical contextual data? Would using larger, more diverse datasets reduce the observed bias, or would it introduce new types of bias? How can these models be adapted for use in different cultural or linguistic contexts without perpetuating existing stereotypes? While the Perspective API offers valuable tools for detecting toxicity, this analysis highlights the need for continuous evaluation and improvement to ensure fairness and reliability in diverse scenarios.

