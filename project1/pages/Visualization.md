---
title: Visualizations
layout: about
permalink: /visualizations.html
---

<style>
  .visualization-container {
    display: flex;
    align-items: flex-start;
    gap: 20px;
    margin-bottom: 40px;
  }
  .text-content {
    flex: 1;
  }
  .iframe-container {
    flex: 1;
    text-align: center;
  }
  iframe {
    width: 100%;
    height: 500px;
    border: none;
  }
</style>

# Visualizations

## Interactive Word Cloud

The Interactive Word Cloud presents a frequency analysis of key terms extracted from archival records on colonial and native land claims. This visualization emphasizes the most commonly occurring words, offering insights into dominant themes such as governance, land disputes, community engagement, and indigenous rights.

<div class="iframe-container" style="margin-top: 20px; position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
    <iframe src="objects/007_CLAIRE_Interactive_Word_Cloud.html" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none;"></iframe>
</div>

---

## Colonial Land Policies and Community Responses in Enugu: An Interactive Chronology

<div class="visualization-container">
  <div class="text-content">
    The interactive timeline explores historical interactions between colonial governance and indigenous communities in Southeastern Nigeria, focusing on land management, policies, and resistance.
    <br>
    [View Interactive Visualization](objects/006_CLAIRE_Colonial_Land_Timeline_Red_White.html)
  </div>
  <div class="iframe-container">
    <iframe src="objects/006_CLAIRE_Colonial_Land_Timeline_Red_White.html"></iframe>
  </div>
</div>

---
## Interactive Topic Model

<div class="visualization-container">
  <div class="text-content">
    This model visualizes latent themes in archival documents using topic modeling (LDA), offering a structured view of major themes such as governance, land management, and socio-economic dynamics.
    <br>
    <a href="objects/001_CLAIRE_interactive_topic_model.html" target="_blank">View Interactive Visualization</a>
  </div>
  <div class="iframe-container" style="margin-top: 20px;">
    <iframe src="objects/001_CLAIRE_interactive_topic_model.html" width="100%" height="800" style="border:none;"></iframe>
  </div>
</div>

---

## Interactive Topic Table

<div class="visualization-container">
  <div class="text-content">
    The Interactive Topic Table organizes and displays keywords and topics extracted from archival petitions, offering insights into recurring themes in land claims and disputes.
    <br>
    <a href="objects/003_CLAIRE_Interactive_Topic_Table.html" target="_blank">View Interactive Visualization</a>
  </div>
  <div class="iframe-container" style="margin-top: 20px;">
    <iframe src="objects/003_CLAIRE_Interactive_Topic_Table.html" width="100%" height="800" style="border:none;"></iframe>
  </div>
</div>

---

## Network Visualization of Topics

<div class="visualization-container">
  <div class="text-content">
    This network visualization represents relationships between topics, helping users understand the thematic structures and interconnections in archival data.
    <br>
    <a href="objects/004_CLAIRE_highlight_relationship_network.html" target="_blank">View Interactive Visualization</a>
  </div>
  <div class="iframe-container" style="margin-top: 20px;">
    <iframe src="objects/004_CLAIRE_highlight_relationship_network.html" width="100%" height="800" style="border:none;"></iframe>
  </div>
</div>

---

## Claims Frequency Visualization

<div class="visualization-container">
  <div class="text-content">
    The bar chart compares the frequency of colonial versus native land claims by topic, illustrating patterns of land disputes and governance.
    <br>
    <a href="objects/005_CLAIRE_claims_frequency_visualization.html" target="_blank">View Interactive Visualization</a>
  </div>
  <div class="iframe-container" style="margin-top: 20px;">
    <iframe src="objects/005_CLAIRE_claims_frequency_visualization.html" width="100%" height="800" style="border:none;"></iframe>
  </div>
</div>

## Topic Frequency Heat Map

<div class="visualization-container">
  <div class="text-content">
    The heat map visualizes the frequency distribution of topics across archival documents, offering a detailed view of thematic density.
    <br>
    [View Interactive Visualization](/objects/008_CLAIRE_Interactive_Topic_Frequency_Heat_Map.html)
  </div>
  <div class="iframe-container">
    <iframe src="objects/008_CLAIRE_Interactive_Topic_Frequency_Heat_Map.html"></iframe>
  </div>
</div>

---

## Interactive Word Cloud

The interactive word cloud was generated from 26 transribed text files, it combines frequency analysis with visual and interactive features. Its ability to highlight dominant themes, facilitate deeper exploration, and present data in an engaging manner makes it invaluable for textual analysis. By emphasizing terms like "land," "community," and "petition," the word cloud provides a window into recurring issues of governance, rights, and community advocacy within the dataset. As a methodological tool, it bridges the gap between computational analysis and qualitative inquiry, enabling researchers to uncover meaningful patterns and narratives within large textual corpora.

Data Preparation: The dataset consisted of 26 text files, which were first combined into a single corpus in R. Text preprocessing techniques were applied to ensure consistency and clarity in the analysis. These techniques included converting all text to lowercase, removing punctuation, eliminating stop words (e.g., "and," "of," "the"), and optionally stemming or lemmatizing words to unify variants (e.g., "petition" and "petitions" reduced to "petition"). This preprocessing ensured that only meaningful words remained in the analysis.

Frequency Analysis: Tokenization, the process of splitting text into individual words, was performed on the preprocessed corpus. A frequency count of all unique words was then calculated, highlighting the most commonly occurring terms across the dataset. Words with higher frequencies were marked for prominence in the word cloud.

Visualization in R: The processed data was fed into R libraries such as tm (Text Mining) or wordcloud2 to generate the word cloud. These tools map word frequencies to their size and placement within the visualization—higher frequencies result in larger words. The layout and colors of the word cloud were customized for aesthetic appeal and ease of interpretation.

Interactive Features: To enhance usability, interactive functionality was added using tools like wordcloud2 or the shiny R package. In an interactive word cloud, users can hover over or click on words to view additional information, such as exact word frequencies or their contexts within the dataset. This functionality allows for dynamic exploration of the data.

Functionality of the Interactive Word Cloud
Interactive word clouds provide an engaging and user-friendly platform for text analysis. Users can explore the dataset beyond visual prominence by interacting with individual terms. For instance, hovering over the term "land" might reveal how many times it appears across the 26 text files, while clicking on it might link to sections of the text where the term is heavily concentrated. This interactivity makes the word cloud not only a summary tool but also a gateway for deeper, document-specific exploration.

## Colonial Land Policies and Community Responses in Enugu: An Interactive Chronology

The interactive timeline titled "Colonial Land Policies and Community Responses in Enugu" offers a detailed exploration of the historical interactions between colonial governance and indigenous communities in Southeastern Nigeria. Utilizing the TimelineJS tool, this chronology sheds light on key events, themes, and developments in land management, colonial policies, and community resistance during the late 19th and early 20th centuries. Through its visual and interactive structure, the timeline provides a nuanced understanding of how colonial policies shaped land governance in Enugu and how local communities responded to these shifts.

- Thematic Overview of the Timeline
The timeline is organized around six major themes that provide a comprehensive framework for understanding the events and dynamics of the colonial period:

1. Land Management: Focuses on policies and practices governing the allocation and use of land under colonial administration.
2. Crown Land Issues: Highlights disputes and governance decisions surrounding Crown Land, land declared by the colonial state to be under its control.
3. Community Demands: Captures the petitions, protests, and appeals by indigenous communities seeking fairness and justice in the face of dispossession.
4. Colonial Policies: Examines broader legislative and administrative measures enacted by the colonial government to assert control over land and resources.
5. Resistance: Documents grassroots efforts by indigenous communities to contest colonial authority, often through organized protests or formal petitions.
6. Policy Changes: Chronicles adjustments in colonial governance strategies, often influenced by indigenous resistance or shifts in global colonial practices.
These themes provide users with a structured lens through which to engage with the historical narrative, emphasizing the interconnectedness of policy-making, land appropriation, and community activism.

# Features of the Interactive Timeline

Chronological Exploration:

Events are plotted along a horizontal axis, allowing users to move through time and gain a step-by-step understanding of historical developments. The timeline begins in the 1906, a period marking the early phase of colonial penetration into Southeastern Nigeria, and progresses reflecting the height of colonial influence in Enugu.

- Event Highlighting:

Each event is displayed prominently with its title, date, and description. For example:
The Crown Land Ordinance highlights how colonial authorities used legislative tools to expropriate land, undermining indigenous ownership systems.

The Petition from Enugu Chiefs showcases the organized resistance of local leaders against unjust land practices.
Thematic Organization:

-Visual Accessibility:

The bright red background and bold text emphasize the importance of the events, ensuring clarity and drawing the viewer's attention to critical moments in the timeline.

-Historical Significance and Key Themes
The timeline captures the interplay between colonial governance and indigenous agency, focusing on land as a site of power, negotiation, and resistance. 

Additionally, the timeline highlights the long-term impacts of colonial land practices, which continue to influence land governance and resource conflicts in post-colonial Nigeria.

## Interactive Topic Model


# Tech Info: Interactive Topic Modeling with Google Colab
The interactive topic model was developed using Google Colab, an accessible platform for conducting computational analyses. The dataset consisted of 26 transcripts, primarily petitions and correspondence, which documented indigenous grievances, negotiations, and responses to colonial land acquisition policies. To extract meaningful patterns from these texts, a Latent Dirichlet Allocation (LDA) model was applied, which is a popular method for topic modeling. The LDA model identifies latent themes within a corpus by clustering words that frequently appear together.

To ensure the model’s relevance, the texts underwent preprocessing steps, including the removal of stopwords, stemming, and lemmatization, which standardized the language and enhanced the interpretability of the results. Keywords were selected based on their frequency and thematic importance, offering a robust foundation for analyzing recurring issues. The interactive visualization of the topic model allows for dynamic exploration of topics, their relationships, and associated terms, providing a structured view of the major themes that emerge from the petitions.

# Major Themes from the Petitions and Correspondence
The topic modeling analysis reveals several overarching themes that reflect the struggles and negotiations of indigenous communities during the colonial period. These themes include the commodification of land, bureaucratic instruments of colonial power, and the strategies of resistance employed by indigenous populations.

1. The Commodification of Land
One of the central themes highlighted in the analysis is the transformation of land from a communal resource to a commodified asset under colonial policies. Keywords such as “land,” “acres,” “rent,” and “compensation” appear frequently in the petitions, emphasizing the colonial administration’s efforts to impose new systems of land ownership. This shift was primarily driven by the economic imperatives of the British Empire, particularly the need to extract natural resources such as coal in Enugu.

The frequent reference to “compensation” in the transcripts underscores the colonial government’s attempts to legitimize land acquisition by offering monetary reparations to displaced communities. However, the inadequacy and inequity of these compensations are evident in the petitions, which detail the disruptions to livelihoods and cultural practices caused by land alienation. The commodification of land also displaced communities from their ancestral lands, severing them from resources essential to their agricultural and spiritual practices.

2. Bureaucratic Instruments of Colonial Power
The analysis further underscores the role of colonial bureaucracy in facilitating land acquisition. Keywords like “court,” “documents,” “sign,” and “government” reveal the mechanisms used by the colonial administration to formalize land alienation. Courts and formal agreements were pivotal in legitimizing the seizure of indigenous lands, often at the expense of local populations who lacked access to legal representation or literacy.

Petitions frequently lament the coercive tactics used by colonial officials to secure agreements, often forcing indigenous people to sign documents they did not understand. The use of formal documentation as a tool of colonization highlights the systemic power imbalance between the colonial administration and indigenous communities. This bureaucratic approach also marginalized traditional systems of land governance, replacing them with structures that prioritized colonial economic interests.

3. Indigenous Resistance and Petitions
Despite the systemic challenges posed by colonial land policies, indigenous communities demonstrated resilience and agency in resisting land alienation. Terms such as “petition,” “grievances,” “chief,” “council,” and “demands” reflect the strategies employed by local leaders and communities to challenge colonial authorities. Petitions emerged as a critical tool for articulating grievances, negotiating terms, and seeking redress.

Chiefs and councils played central roles in mobilizing communities and presenting their demands to the colonial administration. These petitions often highlighted the inadequacy of compensation, the cultural significance of the alienated lands, and the broader socio-economic consequences of colonial policies. In addition to petitions, indigenous resistance included public demonstrations and other informal methods of protest, underscoring the contested nature of colonial land policies.

Insights from the Topic Model
The interactive topic model offers valuable insights into the historical dynamics of colonial land acquisition and indigenous resistance in Enugu. The prominence of certain keywords and topics underscores the interconnectedness of land commodification, bureaucratic exploitation, and indigenous resilience. By dynamically exploring these topics, the model reveals not only the grievances of indigenous communities but also their strategies for contesting colonial power.

Moreover, the spatial and temporal dimensions of these issues are reflected in the frequent references to specific locations such as “Enugu” and “Ngwo.” These areas, central to coal mining and other colonial economic activities, became focal points of land alienation and resistance. The analysis also highlights the ecological impacts of colonial land policies, including the restriction of indigenous access to forests and other natural resources.

## Interactive Topic Table


The interactive topic model was created using Latent Dirichlet Allocation (LDA) in Google Colab to analyze 26 transcripts of petitions and correspondence related to colonial land acquisition and indigenous resistance in Enugu. Keywords were extracted and categorized based on their frequency and relevance, allowing for thematic grouping into topics such as governance, land management, and socio-economic dynamics, represented visually through an interactive analysis interface.


# Understanding and Methodology Behind the Network Visualization of Topics
The provided network visualization is a graphical representation of topics extracted from a textual dataset using topic modeling techniques such as Latent Dirichlet Allocation (LDA). Each node in the network represents a topic, and the connections or arrows between them signify relationships or interdependencies between these topics. This type of visualization is useful in understanding the thematic structures and relationships within a large corpus of text.

1. Understand the thematic distribution of topics in the data.
Observe how topics interact or overlap, revealing the connections between themes.
Explore the relationships between significant thematic categories, enabling a deeper understanding of the corpus.
The network visualization complements the numerical results of topic modeling by presenting a human-readable, visual format that enhances interpretation and accessibility.

2. Methodology
The process behind such a visualization can be broken down into several distinct stages:

a. Data Preparation
The textual data undergoes preprocessing to ensure it is ready for analysis. This includes:

Tokenization: Splitting the text into individual words or tokens.
Stopword Removal: Eliminating frequently occurring but non-informative words (e.g., "and," "the").
Stemming or Lemmatization: Reducing words to their root forms to avoid redundancy (e.g., "running" becomes "run").
Vectorization: Converting the cleaned text into a numerical format, typically a Document-Term Matrix (DTM), where rows represent documents, columns represent words, and cell values indicate word frequencies.
b. Topic Modeling with LDA
Latent Dirichlet Allocation (LDA) is a probabilistic algorithm used to uncover the hidden thematic structure of a text corpus. LDA assumes:

Each document is a mixture of multiple topics.
Each topic is a mixture of words, with varying probabilities of association.

Nodes (Topics): Each topic is represented as a node in the network, labeled with either its number or its most representative terms (e.g., "Urban Expansion and Environmental Issues").

Edges (Connections): Connections between nodes indicate relationships or shared terms between topics. These relationships are quantified through measures such as co-occurrence or cosine similarity.

Arrows/Edges: Show relationships or transitions between topics.

3. Interpretation of the Visualization
The visualization highlights:

Thematic Clusters: Nodes with similar colors likely belong to the same thematic cluster. For example, topics related to environmental issues may form a distinct group.

Topic Importance: Larger nodes may indicate topics that dominate the corpus.

Inter-Topic Relationships: The arrows or edges show how topics are semantically linked, revealing overlaps or shared ideas across themes.
In the provided example, topics such as "Waterworks Grievances and Rent Disputes" and "Socio-Economic Dynamics of Land Rights" may share terms or documents, leading to an observed connection.

4. Technological Framework
The creation of such a visualization involves multiple technological components:

Topic Modeling: LDA implementation using libraries like Gensim or scikit-learn in Python.
Network Visualization:
NetworkX: For generating and manipulating network graphs.
Plotly: For creating interactive network visualizations with zoom and hover functionalities.
pyLDAvis: A specialized library for visualizing LDA topic models interactively.
Dimensionality Reduction: Tools like t-SNE or PCA for reducing the complexity of high-dimensional data.

5. Limitations
While powerful, this approach has limitations:

Interpretability: Topic labels are not inherently meaningful and require human interpretation.
Dimensionality Reduction: Techniques like t-SNE may distort global relationships in favor of local clustering.
Overlapping Topics: Topics may overlap significantly, making clear distinctions difficult.

## Claims Frequency Visualization


# Methodology and Technology: Analyzing Archival Records to Explore Colonial and Native Land Claims

The analysis began with the selection and transcription of 70 archival records, which included petitions, treaties, legal agreements, and administrative correspondence. These records were rich in content, documenting the interactions between colonial authorities and indigenous communities over land and resource disputes. The methodological process involved the following key steps:

--Archival Transcription:

-Thematic Coding:

Each document was carefully reviewed to identify recurring themes such as land acquisitions, legal disputes, environmental ownership, resistance to public land projects, and labor rights. These themes were informed by the content of the records and the broader historical context of colonial governance and indigenous resistance.

-Frequency Analysis:

The frequency of claims in each category was calculated to reveal patterns in the documentation of land claims. This step enabled the study to quantify the prevalence of specific themes, such as colonial land acquisitions versus indigenous petitions for communal land rights.
Inter-Generational Analysis:

Beyond the immediate documentation of claims, the records were analyzed for evidence of inter-generational discourse within indigenous communities. For example, debates among chiefs regarding the legitimacy of 1915/1917 agreements and their renegotiation in the 1930s were categorized as inter-generational negotiations.

# Technology: Using Google Colab for Data Analysis and Visualization

The technological backbone of the analysis was Google Colab, a cloud-based platform that enabled seamless integration of data processing, analysis, and visualization. Google Colab was particularly suited to this project due to its accessibility, collaborative features, and compatibility with Python libraries.

- Data Structuring:

The transcribed archival records were converted into a structured dataset using Python’s Pandas library. Each record was assigned metadata, including the type of claim (colonial or indigenous), thematic category, and frequency.

- Data Analysis:

Python libraries such as Pandas and NumPy were used to process and analyze the data. These tools allowed for efficient manipulation of the dataset, enabling calculations of claim frequencies across the thematic categories.
Data Visualization:

The final visualization, a bar chart comparing the frequency of colonial versus native land claims by topic, was created using the Plotly library. Plotly’s interactive features ensured clarity and accessibility, making it easier to compare the prevalence of claims across different themes.
- Linking Archival Records to Frequency Visualization
The 70 archival records served as the foundation for the entire analysis. Each document was a piece of a larger puzzle, contributing to the visualization of how land claims were distributed across themes. For instance:

Colonial Claims: The records revealed a high frequency of colonial claims related to formal land acquisitions, legal boundary interpretations, and land governance. These claims often reflected the colonial administration’s efforts to consolidate power and legitimize land appropriations for public projects.

Native Land Claims: Indigenous petitions and appeals frequently documented disputes over environmental ownership, communal land rights, and resistance to colonial encroachments. These claims highlighted the resilience of native communities in using formal mechanisms to negotiate their rights.

The visualization also reflected inter-generational debates within indigenous communities. For example, petitions from the 1930s revisited agreements made in 1915/1917, with indigenous leaders challenging the fairness of these earlier agreements and accusing colonial authorities of deceit. This thematic and inter-generational analysis underscored the evolving strategies of resistance and advocacy employed by native populations.

# Data Visualization Code Guide

# Fle: CODES_DATAVIZ.md

# Table of Contents

1.Topic Frequency Heat Map
2.Claims Frequency Visualization
3.Interactive Topic Modeling
4.Interactive Word Cloud
5.Interactive Timeline
6.Network Visualization

## 1. Topic Frequency Heat Map

Script: scripts/heatmap_generator.py

Input: Archival text files located in the data/ directory.

Output: outputs/topic_frequency_heatmap.html

Description: Generates an interactive heat map displaying the frequency of key topics (e.g., governance, resistance, petitions) across archival documents.

bash

python scripts/heatmap_generator.py

Dependencies

pandas

plotly

## 2. Claims Frequency Visualization

Script: scripts/claims_comparison.py

Input: Text files in data/, separated as "native_claims.txt" and "colonial_claims.txt".

Output: outputs/claims_frequency.html

Description: Produces an interactive bar chart comparing the frequency of topics in colonial claims versus indigenous claims.

bash

python scripts/claims_comparison.py

Dependencies

pandas

plotly

## 3. Interactive Topic Modeling

Script: scripts/topic_modeling.py

Input: Archival text files in data/.

Output: outputs/topic_model.html

Description: Uses Latent Dirichlet Allocation (LDA) to identify latent themes within the text and visualizes them interactively.

bash

python scripts/topic_modeling.py

Dependencies

scikit-learn

pandas

## 4. Interactive Word Cloud

Script: scripts/frequency_analysis.py

Input: Archival text files in data/.

Output: outputs/word_cloud.html

Description: Creates an interactive word cloud representing the most frequently occurring words in the archival data.

bash

python scripts/frequency_analysis.py

Dependencies

pandas

plotly

## 5. Interactive Timeline

Script: scripts/timeline_generator.py

Input: events_timeline.txt located in data/.

Output: outputs/event_timeline.html

Description: Generates an interactive timeline of key historical events related to land acquisition and indigenous resistance.

bash

python scripts/timeline_generator.py

Dependencies

Timeline.js (CDN included in script)

## 6. Network Visualization

Script: scripts/network_visualization.py

Input: Archival text files in data/.

Output: outputs/topic_network.html

Description: Produces an interactive network graph linking documents to their most frequent keywords, highlighting relationships between key themes.

bash

python scripts/network_visualization.py

Dependencies

networkx

pyvis

### Setup Instructions

Ensure you have Python installed (version 3.7+).

Install the required dependencies:

bash

Copy code

pip install -r requirements.txt

Place the raw text data into the data/ directory.

Run the desired script(s) as outlined above.

Outputs

All visualizations will be saved as interactive HTML files in the outputs/ directory. You can open these files in any web browser.
