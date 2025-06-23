WORD_CLOUD

"C:\Users\Dummy Account\Desktop\MyFolder\Data"
import os

def create_html_from_text_files(directory, output_file):
    """
    Reads all text files from a given directory and generates an interactive HTML file.
    
    Args:
        directory (str): Path to the directory containing text files.
        output_file (str): Name of the output HTML file.
    """
    # Collect text file names and contents
    text_files = [f for f in os.listdir(directory) if f.endswith('.txt')]
    file_contents = {}
    
    for text_file in text_files:
        with open(os.path.join(directory, text_file), 'r', encoding='utf-8') as f:
            file_contents[text_file] = f.read()

    # Start generating the HTML content
    html_content = '''<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Text Files</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        h1 {
            color: #333;
        }
        select, pre {
            margin-top: 10px;
            width: 100%;
        }
        pre {
            background: #f4f4f4;
            border: 1px solid #ddd;
            padding: 10px;
            overflow: auto;
            height: 300px;
        }
    </style>
    <script>
        function displayFileContent() {
            const selectedFile = document.getElementById("file-selector").value;
            const fileContents = JSON.parse(document.getElementById("file-data").textContent);
            document.getElementById("file-content").textContent = fileContents[selectedFile];
        }
    </script>
</head>
<body>
    <h1>Interactive Text File Viewer</h1>
    <label for="file-selector">Choose a text file:</label>
    <select id="file-selector" onchange="displayFileContent()">
        <option value="">--Select a file--</option>
'''
    # Add options for each text file
    for text_file in text_files:
        html_content += f'        <option value="{text_file}">{text_file}</option>\n'

    # Add JSON data for file contents
    html_content += '''    </select>
    <pre id="file-content">Select a file to view its content here...</pre>
    <script type="application/json" id="file-data">
'''
    html_content += f'{str(file_contents).replace("'", '"')}'  # Convert to JSON format

    html_content += '''
    </script>
</body>
</html>'''

    # Save the HTML content to the specified file
    with open(output_file, 'w', encoding='utf-8') as f:
        f.write(html_content)

    print(f"Interactive HTML saved as {output_file}")

# Directory containing text files and the output HTML file
text_files_directory = "./text_files"  # Change to your directory path
output_html = "interactive_text_viewer.html"

# Run the function to create the HTML
create_html_from_text_files(text_files_directory, output_html)


##TIMELINE

Time Line-
import os
import json

def create_timeline_html(text_files_directory, output_html):
    """
    Reads multiple text files, extracts content as events, and generates an interactive HTML timeline.

    Args:
        text_files_directory (str): Path to directory containing text files.
        output_html (str): Name of the output HTML file.
    """
    events = []
    text_files = [f for f in os.listdir(text_files_directory) if f.endswith('.txt')]

    # Process each text file to create an event
    for text_file in text_files:
        with open(os.path.join(text_files_directory, text_file), 'r', encoding='utf-8') as f:
            lines = f.readlines()
            if len(lines) >= 2:
                title = lines[0].strip()  # First line as title
                description = ''.join(lines[1:]).strip()  # Rest as description
                events.append({
                    "year": title.split()[0],  # Extract year from title
                    "headline": title,
                    "text": description
                })

    # Convert events to JSON
    timeline_data = {
        "timeline": {
            "headline": "Interactive Timeline",
            "type": "default",
            "text": "Generated Timeline of Events",
            "date": events
        }
    }

    # HTML Content with Timeline.js
    html_content = f'''<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Timeline</title>
    <link rel="stylesheet" type="text/css" href="https://cdn.knightlab.com/libs/timeline3/latest/css/timeline.css">
    <script src="https://cdn.knightlab.com/libs/timeline3/latest/js/timeline.js"></script>
    <style>
        body {{ margin: 0; font-family: Arial, sans-serif; }}
        #timeline-embed {{ width: 100%; height: 600px; }}
    </style>
</head>
<body>
    <h1 style="text-align: center;">Interactive Event Timeline</h1>
    <div id="timeline-embed"></div>
    <script>
        var timeline_json = {json.dumps(timeline_data)};
        window.timeline = new TL.Timeline('timeline-embed', timeline_json);
    </script>
</body>
</html>'''

    # Write the HTML file
    with open(output_html, 'w', encoding='utf-8') as f:
        f.write(html_content)
    print(f"Timeline saved to {output_html}")

# Directory of text files and output HTML
text_files_directory = "./text_files"  # Change to your directory path
output_html = "interactive_timeline.html"

# Run the function to create timeline
create_timeline_html(text_files_directory, output_html)

import os
import json

def create_timeline_html(text_files_directory, output_html):
    """
    Reads multiple text files, extracts content as events, and generates an interactive HTML timeline.

    Args:
        text_files_directory (str): Path to directory containing text files.
        output_html (str): Name of the output HTML file.
    """
    events = []
    text_files = [f for f in os.listdir(text_files_directory) if f.endswith('.txt')]

    # Process each text file to create an event
    for text_file in text_files:
        with open(os.path.join(text_files_directory, text_file), 'r', encoding='utf-8') as f:
            lines = f.readlines()
            if len(lines) >= 2:
                title = lines[0].strip()  # First line as title
                description = ''.join(lines[1:]).strip()  # Rest as description
                events.append({
                    "year": title.split()[0],  # Extract year from title
                    "headline": title,
                    "text": description
                })

    # Convert events to JSON
    timeline_data = {
        "timeline": {
            "headline": "Interactive Timeline",
            "type": "default",
            "text": "Generated Timeline of Events",
            "date": events
        }
    }

    # HTML Content with Timeline.js
    html_content = f'''<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Timeline</title>
    <link rel="stylesheet" type="text/css" href="https://cdn.knightlab.com/libs/timeline3/latest/css/timeline.css">
    <script src="https://cdn.knightlab.com/libs/timeline3/latest/js/timeline.js"></script>
    <style>
        body {{ margin: 0; font-family: Arial, sans-serif; }}
        #timeline-embed {{ width: 100%; height: 600px; }}
    </style>
</head>
<body>
    <h1 style="text-align: center;">Interactive Event Timeline</h1>
    <div id="timeline-embed"></div>
    <script>
        var timeline_json = {json.dumps(timeline_data)};
        window.timeline = new TL.Timeline('timeline-embed', timeline_json);
    </script>
</body>
</html>'''

    # Write the HTML file
    with open(output_html, 'w', encoding='utf-8') as f:
        f.write(html_content)
    print(f"Timeline saved to {output_html}")

# Directory of text files and output HTML
text_files_directory = "./text_files"  # Change to your directory path
output_html = "interactive_timeline.html"

# Run the function to create timeline
create_timeline_html(text_files_directory, output_html)

TOPIC_MODEL

import os
import json
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.decomposition import LatentDirichletAllocation
import pandas as pd

def read_text_files(directory):
    """Read all text files in a directory and return their contents."""
    texts = []
    filenames = []
    for file in os.listdir(directory):
        if file.endswith(".txt"):
            with open(os.path.join(directory, file), 'r', encoding='utf-8') as f:
                texts.append(f.read())
                filenames.append(file)
    return texts, filenames

def generate_topic_model_html(texts, filenames, n_topics=5, output_html="topic_model.html"):
    """
    Perform topic modeling using LDA and generate an interactive HTML visualization.
    
    Args:
        texts (list): List of text contents.
        filenames (list): List of filenames corresponding to the texts.
        n_topics (int): Number of topics to extract.
        output_html (str): Output HTML file name.
    """
    # Vectorize the text using CountVectorizer
    vectorizer = CountVectorizer(stop_words='english')
    dtm = vectorizer.fit_transform(texts)
    
    # Apply Latent Dirichlet Allocation
    lda = LatentDirichletAllocation(n_components=n_topics, random_state=42)
    lda.fit(dtm)
    
    # Extract topics and words
    words = vectorizer.get_feature_names_out()
    topics = {f"Topic {i+1}": [words[index] for index in topic.argsort()[-10:][::-1]]
              for i, topic in enumerate(lda.components_)}
    
    # Prepare document-topic distribution
    doc_topic_dist = lda.transform(dtm)
    doc_topics = []
    for i, dist in enumerate(doc_topic_dist):
        dominant_topic = f"Topic {dist.argmax() + 1}"
        doc_topics.append({"file": filenames[i], "dominant_topic": dominant_topic, "distribution": dist.tolist()})

    # Generate HTML
    html_content = f'''<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Topic Model</title>
    <style>
        body {{ font-family: Arial, sans-serif; margin: 20px; }}
        h1, h2 {{ color: #333; }}
        .topic {{ margin-bottom: 20px; }}
        table {{ width: 100%; border-collapse: collapse; margin-top: 10px; }}
        th, td {{ border: 1px solid #ddd; padding: 8px; text-align: center; }}
        th {{ background-color: #f4f4f4; }}
    </style>
</head>
<body>
    <h1>Interactive Topic Model</h1>
    <h2>Top Words in Topics</h2>
    '''
    
    # Display topics and top words
    for topic, words in topics.items():
        html_content += f'<div class="topic"><strong>{topic}:</strong> {", ".join(words)}</div>'
    
    html_content += '''<h2>Document Topics</h2>
    <table>
        <tr>
            <th>Document</th>
            <th>Dominant Topic</th>
            <th>Topic Distribution</th>
        </tr>
    '''
    
    # Display document-topic associations
    for doc in doc_topics:
        distribution = ', '.join([f'{prob:.2f}' for prob in doc['distribution']])
        html_content += f'''
        <tr>
            <td>{doc['file']}</td>
            <td>{doc['dominant_topic']}</td>
            <td>{distribution}</td>
        </tr>
        '''
    
    html_content += '''</table>
</body>
</html>'''

    # Save the HTML content to file
    with open(output_html, 'w', encoding='utf-8') as f:
        f.write(html_content)
    print(f"Topic model visualization saved to {output_html}")

# Directory containing text files
text_files_directory = "./text_files"  # Change this to the path of your text files
texts, filenames = read_text_files(text_files_directory)

# Generate the topic model HTML
generate_topic_model_html(texts, filenames, n_topics=5, output_html="topic_model.html")

INTERACTIVE_TOPIC_FREQUENCY_TABLE

import os
import pandas as pd
from collections import Counter
import re

def read_text_files(directory):
    """Reads all text files in a directory and returns their contents."""
    texts = []
    filenames = []
    for file in os.listdir(directory):
        if file.endswith(".txt"):
            with open(os.path.join(directory, file), 'r', encoding='utf-8') as f:
                texts.append(f.read())
                filenames.append(file)
    return texts, filenames

def calculate_word_frequencies(texts, stop_words=None):
    """Calculates word frequencies for a list of texts."""
    stop_words = stop_words or set()
    word_freq = Counter()
    for text in texts:
        words = re.findall(r'\b\w+\b', text.lower())
        filtered_words = [word for word in words if word not in stop_words]
        word_freq.update(filtered_words)
    return word_freq

def generate_topic_frequency_html(word_freq, output_html):
    """
    Generates an interactive HTML table showing word/topic frequencies.

    Args:
        word_freq (Counter): Word frequency data.
        output_html (str): Output HTML file name.
    """
    # Convert to DataFrame
    df = pd.DataFrame(word_freq.items(), columns=["Word", "Frequency"])
    df = df.sort_values(by="Frequency", ascending=False)

    # Generate HTML
    html_content = f'''<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Topic Frequency</title>
    <style>
        body {{ font-family: Arial, sans-serif; margin: 20px; }}
        h1 {{ text-align: center; color: #333; }}
        table {{ width: 100%; border-collapse: collapse; margin-top: 20px; }}
        th, td {{ border: 1px solid #ddd; padding: 8px; text-align: center; }}
        th {{ background-color: #f2f2f2; }}
        tr:nth-child(even) {{ background-color: #f9f9f9; }}
    </style>
</head>
<body>
    <h1>Interactive Topic Frequency Table</h1>
    <table>
        <tr>
            <th>Word</th>
            <th>Frequency</th>
        </tr>
'''
    # Add table rows
    for _, row in df.iterrows():
        html_content += f'''
        <tr>
            <td>{row['Word']}</td>
            <td>{row['Frequency']}</td>
        </tr>
        '''

    html_content += '''
    </table>
</body>
</html>'''

    # Write to HTML file
    with open(output_html, 'w', encoding='utf-8') as f:
        f.write(html_content)
    print(f"Topic frequency table saved to {output_html}")

# Directory containing text files
text_files_directory = "./text_files"  # Change to your directory path
output_html = "topic_frequency.html"
stop_words = {"the", "and", "is", "in", "to", "of", "a", "on", "for", "with", "by", "at"}  # Example stop words

# Read text files
texts, filenames = read_text_files(text_files_directory)

# Calculate word frequencies
word_frequencies = calculate_word_frequencies(texts, stop_words=stop_words)

# Generate the HTML table
generate_topic_frequency_html(word_frequencies, output_html)

INTERACTIVE NETWORK VISUALIZATION

import os
import re
from collections import defaultdict, Counter
import pandas as pd
import networkx as nx
from pyvis.network import Network

def read_text_files(directory):
    """Reads all text files in a directory and returns their contents."""
    texts = []
    filenames = []
    for file in os.listdir(directory):
        if file.endswith(".txt"):
            with open(os.path.join(directory, file), 'r', encoding='utf-8') as f:
                texts.append(f.read())
                filenames.append(file)
    return texts, filenames

def extract_keywords(texts, stop_words=None, top_n=5):
    """Extracts keywords from a list of texts using frequency analysis."""
    stop_words = stop_words or set()
    keyword_freq = Counter()
    
    for text in texts:
        words = re.findall(r'\b\w+\b', text.lower())
        filtered_words = [word for word in words if word not in stop_words]
        keyword_freq.update(filtered_words)
    
    return [word for word, _ in keyword_freq.most_common(top_n)]

def build_topic_network(texts, filenames, stop_words=None, top_n=5):
    """Builds a topic network from text files and returns a NetworkX graph."""
    stop_words = stop_words or set()
    G = nx.Graph()
    
    # Extract keywords and add nodes
    for i, text in enumerate(texts):
        keywords = extract_keywords([text], stop_words, top_n)
        G.add_node(filenames[i], size=20, title=f"Document: {filenames[i]}")
        
        for keyword in keywords:
            if not G.has_node(keyword):
                G.add_node(keyword, size=10, color='red', title=f"Keyword: {keyword}")
            G.add_edge(filenames[i], keyword, weight=1)
    return G

def generate_network_html(graph, output_html):
    """Generates an interactive network visualization and saves it as HTML."""
    net = Network(height="700px", width="100%", bgcolor="#ffffff", font_color="black", notebook=False)
    net.from_nx(graph)
    net.show(output_html)
    print(f"Interactive network visualization saved to {output_html}")

# Directory containing text files
text_files_directory = "./text_files"  # Change to your directory path
output_html = "topic_network.html"
stop_words = {"the", "and", "is", "in", "to", "of", "a", "on", "for", "with", "by", "at"}  # Example stop words

# Read text files
texts, filenames = read_text_files(text_files_directory)

# Build topic network
graph = build_topic_network(texts, filenames, stop_words, top_n=5)

# Generate the interactive network visualization
generate_network_html(graph, output_html)


CLAIM FREQUENCY BAR CHART

import os
import re
from collections import Counter
import pandas as pd
import plotly.express as px

def read_text_files(directory):
    """Reads all text files in a directory and separates them into Native and Colonial claims."""
    native_texts = []
    colonial_texts = []
    for file in os.listdir(directory):
        if file.endswith(".txt"):
            with open(os.path.join(directory, file), 'r', encoding='utf-8') as f:
                content = f.read()
                if 'native' in file.lower():
                    native_texts.append(content)
                elif 'colonial' in file.lower():
                    colonial_texts.append(content)
    return native_texts, colonial_texts

def calculate_topic_frequencies(texts, stop_words=None):
    """Calculates word frequencies from a list of texts."""
    stop_words = stop_words or set()
    word_freq = Counter()
    for text in texts:
        words = re.findall(r'\b\w+\b', text.lower())
        filtered_words = [word for word in words if word not in stop_words]
        word_freq.update(filtered_words)
    return word_freq

def generate_comparison_chart_html(native_freq, colonial_freq, output_html):
    """Generates an interactive bar chart comparing Native and Colonial topic frequencies."""
    # Merge frequencies into a DataFrame
    topics = set(native_freq.keys()).union(set(colonial_freq.keys()))
    data = []
    for topic in topics:
        data.append({
            'Topic': topic,
            'Native Claim': native_freq.get(topic, 0),
            'Colonial Claim': colonial_freq.get(topic, 0)
        })
    df = pd.DataFrame(data)
    df = df.sort_values(by=['Native Claim', 'Colonial Claim'], ascending=False).head(20)  # Top 20 topics

    # Melt DataFrame for Plotly compatibility
    df_melted = pd.melt(df, id_vars='Topic', value_vars=['Native Claim', 'Colonial Claim'],
                        var_name='Claim Type', value_name='Frequency')

    # Create the interactive bar chart
    fig = px.bar(
        df_melted, x='Topic', y='Frequency', color='Claim Type',
        title='Comparison of Native Claim vs Colonial Claim Topic Frequencies',
        labels={'Frequency': 'Word Frequency', 'Topic': 'Topics'},
        barmode='group'
    )

    # Save the chart to an HTML file
    fig.write_html(output_html)
    print(f"Interactive bar chart saved as {output_html}")

# Directory containing text files
text_files_directory = "./text_files"  # Change to your directory path
output_html = "native_vs_colonial_claims.html"
stop_words = {"the", "and", "is", "in", "to", "of", "a", "on", "for", "with", "by", "at", "this", "that", "it", "as"}  # Example stop words

# Read text files and split into Native and Colonial claims
native_texts, colonial_texts = read_text_files(text_files_directory)

# Calculate topic frequencies
native_freq = calculate_topic_frequencies(native_texts, stop_words)
colonial_freq = calculate_topic_frequencies(colonial_texts, stop_words)

# Generate comparison bar chart HTML
generate_comparison_chart_html(native_freq, colonial_freq, output_html)

TOPIC FREQUENCY HEAT MAP

import os
import re
from collections import Counter
import pandas as pd
import plotly.express as px

def read_text_files(directory):
    """Reads all text files in a directory and returns their contents along with filenames."""
    texts = []
    filenames = []
    for file in os.listdir(directory):
        if file.endswith(".txt"):
            with open(os.path.join(directory, file), 'r', encoding='utf-8') as f:
                texts.append(f.read())
                filenames.append(file)
    return texts, filenames

def calculate_topic_frequencies(texts, filenames, stop_words=None):
    """Calculates word frequencies for each document and returns a DataFrame."""
    stop_words = stop_words or set()
    data = []
    for i, text in enumerate(texts):
        word_freq = Counter()
        words = re.findall(r'\b\w+\b', text.lower())
        filtered_words = [word for word in words if word not in stop_words]
        word_freq.update(filtered_words)
        for word, freq in word_freq.items():
            data.append({"Document": filenames[i], "Topic": word, "Frequency": freq})
    return pd.DataFrame(data)

def generate_heatmap_html(df, output_html):
    """Generates an interactive heat map for topic frequencies and saves it as HTML."""
    # Pivot the DataFrame for heatmap structure
    heatmap_data = df.pivot_table(index='Document', columns='Topic', values='Frequency', fill_value=0)
    
    # Create the heat map using Plotly
    fig = px.imshow(
        heatmap_data,
        labels=dict(x="Topics", y="Documents", color="Frequency"),
        title="Interactive Topic Frequency Heat Map",
        color_continuous_scale="Blues"
    )

    # Save the heatmap to an HTML file
    fig.write_html(output_html)
    print(f"Interactive heat map saved as {output_html}")

# Directory containing text files
text_files_directory = "./text_files"  # Change to your directory path
output_html = "topic_frequency_heatmap.html"
stop_words = {"the", "and", "is", "in", "to", "of", "a", "on", "for", "with", "by", "at", "this", "that", "it", "as"}  # Example stop words

# Read text files
texts, filenames = read_text_files(text_files_directory)

# Calculate topic frequencies
topic_df = calculate_topic_frequencies(texts, filenames, stop_words)

# Generate the heatmap HTML
generate_heatmap_html(topic_df, output_html)

