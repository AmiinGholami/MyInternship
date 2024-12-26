# 📊 Report on Learning Streamlit and Gradio Libraries

## Task Overview
As part of my internship, I was assigned the task to **learn about Streamlit and Gradio Libraries**, both of which are powerful tools for building interactive web applications tailored for data science and machine learning workflows. The goal was to understand their installation process, core functionalities, and how to build basic applications with each library. Here's a detailed explanation of the steps I followed and the results.


## Making My Own GDP Dashboard with Streamlit:

🌎 GDP dashboard: https://gdp-dashboard-of-amin.streamlit.app/

Repository : https://github.com/AmiinGholami/GDPdashboard

---

## 1. Learning Streamlit

### What is Streamlit?
Streamlit is a fast and easy way to create custom web apps in Python, specifically for machine learning and data science. It allows developers to quickly turn data scripts into shareable web apps with very little effort.

### Step-by-Step Process

#### a) **Installation and Setup**
To get started with Streamlit, I first needed to install it. The installation is quite straightforward:
```bash
pip install streamlit
```

Once installed, you can start any Streamlit application with:
```bash
streamlit run app.py
```
Streamlit automatically launches the app in the browser, making development quick and interactive.


### b) **Building a Basic App**

I started with a simple example to understand the basic functionalities:
```bash
import streamlit as st

st.title("Hello, Streamlit!")
st.write("This is my first Streamlit application.")

# Create a simple slider to adjust values
slider_value = st.slider('Select a value', 0, 100, 50)
st.write(f'Selected value: {slider_value}')
```
With this small code, I was able to launch a web app that allowed users to interact with a slider, providing instant visual feedback.


### c) **Displaying Data**
Streamlit is especially useful for visualizing data in data science projects. Here’s how I learned to display a Pandas DataFrame:

```bash
import pandas as pd

data = {'Name': ['John', 'Jane', 'Sam'],
        'Age': [28, 34, 22]}
df = pd.DataFrame(data)

st.write("Displaying DataFrame:")
st.write(df)
```
This helped me understand how easy it is to display and manipulate data within a Streamlit app. The integration with other Python libraries like Pandas is seamless.

### d) **Visualizing Data**
One of the key features of Streamlit is the ability to quickly visualize data with minimal code. Here’s an example where I generated a simple line chart using Matplotlib:


```bash
import matplotlib.pyplot as plt

fig, ax = plt.subplots()
ax.plot([1, 2, 3, 4], [10, 20, 25, 30])
st.pyplot(fig)
```

Streamlit makes it incredibly easy to incorporate any data visualization tools into a web app, which is essential for data science projects.


### Key Takeaways from Streamlit:

	•	Fast development: It allows for the rapid creation of apps.
	•	Easy to use: You can turn simple Python scripts into powerful web apps.
	•	Perfect for data science: It integrates seamlessly with popular data science libraries like Pandas, Matplotlib, and Seaborn.


 ## 2. Learning Gradio

### What is Gradio?
Gradio is a Python library that makes it super simple to create UIs for machine learning models and share them via a web interface. It’s especially designed for users who want to quickly build and test ML models in a user-friendly environment.


I am using Gradio Playground for making more familiar with Gradio

Gradio Playground:	https://www.gradio.app/playground

 
### Step-by-Step Process

### a) **Installation and Setup**
Just like Streamlit, Gradio has an easy setup process. To install:
```bash
pip install gradio
```

Once installed, running a Gradio app can be done in a Python script, or directly in Jupyter notebooks.


### b) **Building a Simple Gradio Interface**

The first step in learning Gradio was to create a basic interface:
```bash
import gradio as gr

def greet(name):
    return f"Hello {name}!"

iface = gr.Interface(fn=greet, inputs="text", outputs="text")
iface.launch()
```
This simple app allows a user to input their name, and the app will greet them by displaying “Hello [Name]!”. I learned how easy it was to create interactive interfaces without needing extensive knowledge of web development.

### c) **Integrating Machine Learning Models**

Gradio is particularly useful for building interfaces to interact with machine learning models. I tried building an app that uses a pre-trained machine learning model for image classification:

```bash
import gradio as gr
import tensorflow as tf

model = tf.keras.applications.MobileNetV2()

def classify_image(img):
    img = tf.image.resize(img, (224, 224))
    img = tf.expand_dims(img, 0)
    prediction = model.predict(img)
    return prediction

iface = gr.Interface(fn=classify_image, inputs="image", outputs="label")
iface.launch()
```

With this example, I learned how to create an interactive interface that allows users to upload an image, and the app will classify the image using a pre-trained model. Gradio provides a convenient way to showcase machine learning models with minimal code.

### d) **Customization and Sharing**

One of Gradio’s strong points is that it lets you share your interface with anyone instantly, just by using a shareable link. This was a valuable feature for quick collaboration and testing:

```bash
iface.launch(share=True)
```
This creates a public link that anyone can access to interact with the app.


### Key Takeaways from Gradio:

	•	Simple and intuitive: It allows developers to build interfaces for ML models with very little code.
	•	Real-time sharing: You can easily share your app with others through a public link.
	•	Optimized for ML: Perfect for testing and showcasing machine learning models quickly.


## 3. Comparison Between Streamlit and Gradio

| Feature                 | Streamlit                            | Gradio                              |
|-------------------------|--------------------------------------|-------------------------------------|
| **Primary Use Case**     | Data dashboards, visualization       | Machine learning model interfaces   |
| **Ease of Use**          | Very easy for building data apps     | Extremely simple for ML interfaces  |
| **Installation**         | `pip install streamlit`              | `pip install gradio`                |
| **Customizability**      | Highly customizable                  | Limited but effective               |
| **Best for**             | Data science apps                    | ML model testing and deployment     |
| **App Sharing**          | Needs deployment setup or Streamlit Cloud | One-click public link sharing       |

 ## Conclusion

After completing this task, I have a solid understanding of both Streamlit and Gradio, their use cases, and their strengths. Streamlit is best suited for building data dashboards and applications that display large datasets, while Gradio is more focused on creating quick, user-friendly interfaces for machine learning models. Both libraries offer fast prototyping and development, making them excellent choices for data scientists and machine learning engineers.

## Next Steps:

	•	I plan to explore more advanced functionalities of Streamlit, such as integrating APIs.
	•	For Gradio, I aim to build more complex interfaces for machine learning models that accept multiple types of input (e.g., images and text).
