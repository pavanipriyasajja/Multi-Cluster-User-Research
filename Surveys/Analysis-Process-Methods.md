# Survey analysis methods, Process and Tools:

In our next steps, let’s explore the insights we uncovered from the survey responses. What patterns, challenges, and expectations emerged from engineers working with multi-cluster environments?

### Engineers responded to the survey?

Finally, from our survey, we received responses from <b>170 engineers</b>. Among them, 159 engineers <b>(93% completion rate)</b> completed all the survey questions, including both required and optional questions. The remaining 11 engineers skipped the optional questions and responded only to the required questions.

<b>*Note</b>

We also mentioned during the survey that all responses would be anonymized, and we will not share the raw data directly. 
Instead, the data has been synthesized and presented in clear and understandable form for the results and aggregated results we are going to share with the multi cluster team as well as Kubecon presentations.

### Process and methods and Tools for analysis:

To initiate the analysis process for the survey responses, we began by studying the data multiple times to fully understand and take ownership of it. This helped us better interpret what engineers were trying to convey.
We duplicated the original responses and created a separate file named “Analysis.” 

This ensured that the original data remained intact in case of any accidental changes, and allowed us to reuse and adapt the duplicated data for multiple analysis tasks.
Next, we filtered and extracted responses where participants mentioned “no,” “-,” “don’t want to mention,” or left questions unanswered. We then consolidated this data in one place to make it easier to review and interpret.
Finally, we followed a structured process, as outlined below, to identify patterns in the responses.

### Qualitative Analysis methods and Tools:

<b>Step 1:</b> Reviewed all the collected data thoroughly to understand it and become familiar with the responses.

<b>Step 2:</b> We Used the text-analysis tool and Copy and paste all responses into the tool to automatically group the data into categories. 
Identify the largest or most frequent categories. 

(<b>*Note: </b> We did not rely solely on the analyzer tool. We manually reviewed each response and used our own judgment to group the data accurately.)

<b>Step 3:</b> We Categorized the data using user-research analysis methods such as <b>thematic analysis</b>, <b>narrative analysis</b>, and <b>coding patterns.</b> 
Then we identified the strongest (most frequent) patterns and rank them from highest to lowest. 

<b>Step 4 :</b> We manually interpreted the output from Steps 1, 2, and 3 and summarized them into conclusions. 

<b>Tools we used for the qualitative analysis</b>

Text analyzer : <a href="https://www.online-utility.org/text/analyzer.jsp ">Link</a>

AI analyzer : <a href="https://chatgpt.com/g/g-86OiPigfl-ai-text-analyzer">Link</a>


### Quantitative  Analysis methods and Tools:


<b>Step : 1 Review and calculate basic metrics across Quantitative questions</b>

We analyzed the numerical survey data using a structured and systematic approach to ensure accuracy and consistency across all questions.
First, we organized and cleaned the dataset by removing incomplete or invalid responses and separating required and optional answers. 
We then calculated response distributions for each question, including counts and percentages, to understand how participants responded.
For rating-scale questions, we computed averages and examined the distribution of responses to identify overall sentiment and variability. For multiple-choice and yes/no questions, we focused on identifying dominant responses and comparing trends across options.

<b>Step 2: Identify Patterns and Trends</b>

We then analyzed the data to identify patterns and trends by comparing responses across different groups, such as roles, experience levels, and the number of clusters deployed per month.
We looked for recurring response patterns, dominant selections, and high or low ratings that indicated strong trends. 
Additionally, we examined correlations between related questions to uncover deeper insights—for example, identifying which groups of engineers prioritize specific tools or face similar challenges.

<b>Step 3: Data Visualization Using Python</b>

After identifying key patterns, we used Python to process and visualize the quantitative data. We created visual representations such as pie charts, bar charts, and line charts with clear labels and percentage values to highlight key insights.
These visualizations made it easier to interpret the data and communicate findings effectively.

<b>Step 4: Cross-Referencing with Qualitative Data</b>

Finally, we cross-referenced the quantitative findings with qualitative responses. By matching numerical trends with themes from open-ended answers, we were able to build a strong, evidence-based understanding of the data.
This approach allowed us to support qualitative insights with percentages and numerical evidence, while also uncovering new patterns grounded in both quantitative and qualitative analysis.

Our <b>final step in the analysis was to reorganize the findings into output artifacts</b> (e.g., Survey Key insights and results, personas, slides, etc.) and present them at KubeCon.

### Iterative Theme Refinement:

The thematic analysis in this study was conducted through multiple iterative passes over the dataset. Rather than treating early results as final, we continuously revisited the raw responses to improve the structure and clarity of the findings.

<b>Themes were refined through multiple iterations</b> to better capture recurring patterns across responses.
<b>Initial codes were reorganized into higher-level categories</b>, allowing for clearer abstraction and improved interpretability.
<b>Some themes were merged or split</b> based on consistency, overlap, and strength of supporting data.

This iterative approach strengthens the overall analysis by ensuring that the final themes are not only representative of the data, but also well-structured, consistent, and credible.

