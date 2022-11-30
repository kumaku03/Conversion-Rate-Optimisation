# Performance-marketing_Deep-Learning-for-Business-Growth-Phase-1

# Performance-marketing_Deep-Learning-for-Business-Growth-Phase-1

PROJECT IN BRIEF: 

I. OBJECTIVE AND SCALABILITY 

Performance Marketing Conversion Rate Optimisation:  The objective of the project was to understand the impact of text content, image objects and graphics on the Click-through rate(CTR) of the creatives used in the Performance Marketing Ads campaign to maximize CTRs. 
This project was further scaled to include other aspects of performance marketing (Geo clusters, Spends, Revenue, Cost of Acquisition etc.)  and App User Interface optimisations which resulted in significant business impact as detailed in the outcomes section. The details included here is a brief narrative. 


II. DETAILS OF ANALYSIS

1. Techniques used: 
Deep learning: Image processing using easyOCR and OpenCV  | Object detection using YOLO and OpenCV | Text processing using NLP packages | Data manipulation using Pandas and Numpy | Machine Learning: Multiple Linear Regression, Decision trees Regressor | Ensemble techniques: Random Forest Regressor, XG Boosting Regressor

2.Data extraction: 

i. Data Source: Nature of data: Images used in Ad Campaigns 
How to get data: Download Google Ads editor and import all the accounts and campaigns offline. Then Export -> Whole account with Images. Also, Use “Get statistics” to get the corresponding image metrics. 
Ref: https://support.google.com/google-ads/editor/answer/38657?hl=en

ii. Text Extraction from Images: Python codes are written with necessary deep learning and other data manipulation packages. EasyOCR and Opencv packages are used to extract text from Images. Object detection models are used to detect people in the images.
Our code goes through the input folder with the list of all images. 
Text extraction and Object detection models are run sequentially and the outputs are stored in a folder. Some key metrics are derived and calculated based on the outputs of the model.

3. Key data manipulation steps:

A. Each Image is governed by the two parameters - Height & Width. 

Total Number of pixels = height * width

For an image with height and width 1200 * 600, total pixels = 72000 

B. Following are the metrics derived:

i.	Text pixels : The number of pixels / space occupied by text content in an Image 
ii.	Text percent : (Text Pixels / Total Pixels) * 100 
iii.	Text content : All the text read from the Image 
iv.	Person count : No of people detected in the image 
v.	Person pixels : The number of pixels / space occupied by person in an Image 
vi.	Person percent : (Person pixels / Total Pixels) * 100 
vii.	Contrast : Sharpness of the objects in the image, standard deviation of all the pixels in a grayscale version

C. Natural Language Processing(NLP) - Text manipulation & processing

The text content is passed through text manipulation functions to get the following parameters:

Word count : Total Number of words in the Image 
Character count : Total number of characters in the image. 
Average word length : Character count / Word count

Sentiment scores: Sentiment scores are also calculated based on two different models and corresponding scores for each image text is obtained.

Named Entity Recognition (NER) models: Classifying the text content under different categories. Edtech being a relatively new domain existing models were not useful. We created our own model to recognize the usage of brand keywords, categories, offers, codes etc. 

All the above metrics were derived at a single campaign and image level. The output file created however was created in an aggregated format. 

D. Mapping the dataset with Google Ads metrics:

Using the Google Ads Online or Adwords editor downloading the image level Ad metrics (for display campaign), Campaign level metrics (for App Install ads). The above two files are merged and all the metrics are available based on the Images available in Image 1 column.
Certain Images were duplicated across different campaigns. Campaign association for specific images were selected basis maximum CTRs.

E. Linear regression:

Dependent Variable: CTR (click through rate : Clicks / Impressions) Independent Variables: 'Text perc', ‘Person perc', 'contrast', 'word count', 'avg_word_length', 'person_count',

Model output: Adjusted R2 value was low indicating the independent variable set combined were not explaining the variability in the dependent variable (CTR). We observed negative correlation between CTR and Text Pixels, CTR and Person count.

F. Ensemble methods: Random Forest regressor and XGBoost 

Random Forest Regression is a supervised learning algorithm that uses ensemble learning method for regression.

XGBoost was the first of The Big Three gradient boosting frameworks, released in 2014. The other two are LightGBM by Microsoft and launched in 2016, and CatBoost by Yandex, launched in 2017. Each of these frameworks are magnificent tools to tackling tabular data problems, using either regression or classification.

Text percentage and word count were found to be the top 2 variables. 

III. OUTPUTS

After using multiple ML methods we observed a strong negative association Text percentage of an image with the Click through Rate (CTR). Basis the ensemble methods detailed we zeroed in on optimum text and object ratios in the creatives. 

We also built a web-based tool for the marketing, design, and product teams to upload the creatives/UI designs and see the real-time analysis and recommendations for maximizing CTR.

IV. OUTCOMES

21% growth in paid marketing revenue, 34% increase in installs, and 143% growth in signups year on year with only 5% increase spends. 
