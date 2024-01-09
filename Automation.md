Task And Solutions 
-------
Week 1 
-----
When i began my reasearch on Artificial Intelligence and it's application in the antimicrobial i had cardinal questions which became a task, i also delve deep to provide a solution check it out below.

Task
-------
- [x] how to identify potential antimicronbial compounds using AI, not using the traditional way which is time consuming 
--------

Solution 
----------

-  by using datasets of molecular-like structures statistical task using sum of squared errors

step 1 -  Loading Datasets :

import pandas as pd

Load the dataset
url = 'https://archive.ics.uci.edu/ml/machine-learning-databases/0024/data_features.csv'
dataset = pd.read_csv(url, header=0)

step 2 - Feature Selection

For our solution , we'll only use the features x1, x2, x3, and x4.

#Select the features

#features = ['x1', 'x2', 'x3', 'x4']



------
week 2
--------

# generate_blog_post.py

import nbformat
from nbconvert import MarkdownExporter
from jinja2 import Environment, FileSystemLoader
import datetime

# Load Jupyter Notebook
notebook_path = "Transformative_AI_Antimicrobial_Research.ipynb"
with open(notebook_path, "r", encoding="utf-8") as f:
    notebook_content = nbformat.read(f, as_version=4)

# Convert Notebook to Markdown
md_exporter = MarkdownExporter()
md_content, _ = md_exporter.from_notebook_node(notebook_content)

# Load Markdown Template
template_loader = FileSystemLoader(searchpath="./")
template_env = Environment(loader=template_loader)
template = template_env.get_template("blog_template.md")

# Create Output Markdown File
output_path = f"output_blog_{datetime.datetime.now().strftime('%Y%m%d%H%M%S')}.md"
with open(output_path, "w", encoding="utf-8") as output_file:
    output_file.write(template.render(notebook_content=md_content))

print(f"Blog post generated successfully: {output_path}")


#dataset = dataset[features]

step 3 - Data Preprocessing
#Convert categorical data to numerical data
from sklearn.preprocessing import LabelEncoder


#for feature in features:
    labelencoder = LabelEncoder()
    dataset[feature] = labelencoder.fit_transform(dataset[feature])


#Scale our features
from sklearn.preprocessing import StandardScaler


#scaler = StandardScaler()
dataset = pd.DataFrame(scaler.fit_transform(dataset), columns=features)

step 4 -  Statistical Task

#Load the target variable
url = 'https://archive.ics.uci.edu/ml/machine-learning-databases/0024/data_target.csv'
target = pd.read_csv(url, header=0)


#Compute the SSE
sse = sum((dataset['x1'] - target['y']) ** 2)
print('SSE:', sse)

[Automation.md]




