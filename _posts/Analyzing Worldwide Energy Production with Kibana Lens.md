---
layout: post
title: "Analyzing Worldwide Energy Production with Kibana Lens"
author: "Elvis"
excerpt: ""
modified:
comments: true
tags: [Data Science,Data Analysis,Technology,Artifical Intelligence,Programming]
image:
  thumb: lm-progress.png
---

![](https://miro.medium.com/max/3200/1*dVeH-KkFJOm1xOUwMVazDg.png)


While there are many tools that can be used to perform a quick analysis of large-scale data, data analysis in itself is not an intuitive process. For instance, what type of chart to use for visualizing fields that contain data of a particular type such as date and numeric ranges? There is no straightforward answer to that. Perhaps for a beginner data analyst and for a lot of users creating visualizations, this is not immediately obvious. In an effort to simplify the process of visualizing and exploring your data in an intuitive manner, Elastic released Kibana Lens. Kibana Lens is a new and interactive way to quickly explore, easily visualize data, and instantly generate rich and powerful visualizations that help to gather insights from data.

In this tutorial, I will demonstrate different ways you can explore and analyze data using Kibana Lens which is a new feature in Kibana. After the end of this tutorial, you will be able to ingest data into Elasticsearch and analyze it using effortless drag and drop actions inside Kibana Lens.


### **The Data**

The data I chose to analyze contains quantities of energy production coming from different countries across the years. The data contains the total energy production between 1990 and 2014 among several countries. Using the Kibana Lens interface and easy-to-compose visualizations we would like to answer simple questions such as:

   -  Which countries have been producing energy using different sources such as nuclear, solar and wind?
   
   - What is the trend of energy production over time for different countries and regions?
   
   - We also want to find out which countries are leading energy production coming from different sources like solar, nuclear or wind?
   
You might be thinking that in order to answer these questions it may require some kind of special querying of your data. Indeed it does, but with Kibana Lens, the process of data analysis and exploration is simplified. In fact, you don't need to know any kind of special query language to visualize the data. All you need to do is drag and drop your fields into a visualization pane and watch your data get converted into beautifully rendered visualizations. Kibana Lens suggests a certain visualization based on the field you want to visualize.

The original data we are going to use for our analysis can be obtained from [here](http://https://www.kaggle.com/unitednations/international-energy-statistics "here"). The data is provided in a csv format. I will convert that data into json objects and index them into Elasticsearch so that I can generate visualizations using Kibana Lens. The data journey is presented in the figure below:

![](https://miro.medium.com/max/1786/1*lduP1fny1Zn1TrbiBjED4w.png)

Even though the data ingesting part is not the focus of this tutorial, I have provided a Jupyter [notebook](http://https://github.com/omarsar/energy_stats/blob/master/energy_usage.ipynb "notebook") that helps to demonstrate how to process the raw data and ingest it into Elasticsearch using this [python client](http://https://elasticsearch-dsl.readthedocs.io/en/latest/ "python client"). This tutorial assumes that you have the latest version of Elasticsearch and Kibana already running on your machine, which is [7.5](http://https://www.elastic.co/blog/elasticsearch-7-5-0-released "7.5") at the time of writing this post.

Before indexing the data into Elasticsearch, I created the following mapping to make sure that the year field has the proper type (i.e., date). The values for this date field are important because they will be used to generate a few useful visualizations using Kibana Lens, which will help us to answer a few questions about the data in the context of time.

Before indexing the data, use the Kibana developer console to create an index with the following mapping:

  

`  PUT energy_stats 
{
      "mappings": {
        "properties": {
          "year": {
            "type": "date",
            "format": "yyyy-MM-dd HH:mm:ss"
          }
        }
      }
    } `

Once you have created the mapping, you can utilize this [notebook](https://github.com/omarsar/energy_stats/blob/master/energy_usage.ipynb "notebook") directly to ingest the data into Elasticsearch using bulk operations.

The next step is to perform the analysis with Kibana Lens but before proceeding I highly recommend that you take a look at this short and excellent overview of Kibana Lens:

[![Watch the video](https://img.youtube.com/vi/6U7uoCyabcg/maxresdefault.jpg)](https://www.youtube.com/embed/6U7uoCyabcg)


### **Analysis with Kibana Lens**

The analysis I want to perform is similar to the excellent work done by Victor Torres in this [ Kaggle notebook](https://www.kaggle.com/vtorreslopez/wind-solar-and-nuclear-energy-production " Kaggle notebook"). If you quickly check out his excellent work, you will see that there is a lot of data transformations that you need to perform on the data to answer very basic questions. Using Kibana Lens, you will notice that the process of exploring and visualizing the data is substantially simplified. You will basically be doing advanced data analytics with very little knowledge of your data or advanced knowledge of a query/programming language.

Kibana Lens is a new feature in the Elastic Stack, embedded inside Kibana, which offers a drag and drop feature that simplifies the process of composing visualizations using the data stored in Elasticsearch. Kibana Lens aims to provide users with an easy-to-use interface for visualizing data while following visualization best practices.

Previously, users had to possess advanced knowledge of the structure of the data and the types of queries that needed to be used to generate different visualizations. With Kibana Lens, the idea is to enable users to generate visualizations without the need to understand the type of queries that need to be sent to Elasticsearch to generate the required data for the visualizations.


### Lets Analyze Energy Production Using Kibana Lens

Assuming the data has been ingested properly and you have Kibana up and running, we are ready to get some quick insights about our data. As it is commonly known, in order to visualize the data, we rely on Elasticsearch [aggregation](https://www.elastic.co/guide/en/elasticsearch/reference/7.5/search-aggregations.html "aggregation") requests. When visualizing data in Kibana you need to know ahead of time the type of aggregation or grouping that you want to use to generate meaningful visualizations. A problem some first-time users of Kibana face is that they typically don’t really understand their data and they have no knowledge of how aggregations work much less how to apply them. This is why Elastic created Kibana Lens.

When you use Kibana Lens, there is no need to know about aggregations and what type of grouping to choose to generate the visualization (this is ideally meant for more advanced users). All you need to do is drag and drop the fields into the visualization pane and Kibana Lens recommends a few visualizations that are suitable to visualize those fields based on their values. You can easily keep adding fields and breaking down your data further. As you do so, Kibana Lens updates the visualization to a suitable type.

Before we get started with Kibana Lens, we need to set up a few things regarding the data. You need to create an index pattern and then select the option to create a Kibana Lens visualization. The video below shows the steps:

[![Watch the video](https://i.ytimg.com/vi_webp/jW6GZ1ZkQuI/maxresdefault.webp)](https://www.youtube.com/embed/jW6GZ1ZkQuI)

…and here is a very quick overview (in text format) about the Kibana Lens interface:

![](https://miro.medium.com/max/6392/1*zGbS8VR1CPj-CcY0bjFzQA.png)

 
 **1. Filter**: Filters are used to manually limit the analysis to a specific subset of the data given a criteria
**2. Index Pattern:** Once created, you need to select the proper index pattern to tell Kibana Lens what dataset you want to use for visualizations

**3. Fields:** Once you have selected your index pattern, Kibana Lens provide you a list of available fields which can be dragged into the visualization pane

**4. Search:** As with any filter, the search bar can also be used to limit the analysis to a subset of the data that meets a search criteria

**5. Time Filter**: It is always recommended to set the appropriate time range for which you want to conduct the analysis

**6. Visualization Pane: **This is where all the visualization magic happens

**7. Visualization Type:** As you drag fields into the visualization pane, Kibana Lens suggests the available visualization types that are possible with those fields

**8. Customization Panel:** In this panel, you can also drag your fields to customize the visualizations. It is also possible to create a special type of grouping of your data based on a specific field in the “Break down by” section.

Finally, let's do some data analysis!

Here is a question worth investigating:

**What is the total wind production over the years, categorized by the European Union and other countries such as the US, Canada, Brazil, Japan, and China?**

In order to help us with the analysis of specific regions or countries, we are going to create a few filters. Below I demonstrate how to create a filter representing the data coming from a few EU countries. *Note that the EU is represented by a few countries just to keep the analysis simple.*


[![Watch the video](https://img.youtube.com/vi/827EacweJWY/maxresdefault.jpg)](https://www.youtube.com/embed/jW6GZ1ZkQuI)


I also created a few filters representing different energy sources (e.g., wind, solar, nuclear, etc.). See the figure below for an example:


![](https://miro.medium.com/max/2124/0*l2DkiwLCOotVOD5h)


Below is the final list of filters I will be using to do the analysis. Notice how I created one filter representing the “Rest of World”. This is because I want to analyze all those countries at once. Individual filters implicitly use an “AND” operation, so if I had a separate filter for each country from the “Rest of World” group I wouldn’t be able to perform the analysis on all of the countries together as there is no data that comes from all the countries at once.

![](https://miro.medium.com/max/2832/0*NsHWlsOLb2jY5K7E)

Now for the fun part! Let’s create a visualization that represents the total wind production for the countries in the “Rest of World” group. Using the power of filters, I can easily enable the “Rest of World” and “wind_electricity” filters and disable the rest of the filters. Once I have the right filters enabled, I can start to drag and drop the fields from the left to the center panel. Take a look at how easily I created the visualization representing the total wind production for countries in the “Rest of World” group across time:



[![Watch the video](https://img.youtube.com/vi/qgTKGR6MMmQ/maxresdefault.jpg)](https://youtu.be/qgTKGR6MMmQ)

Wow! With just a couple of drag and drop actions, I was able to replicate the same chart that Victor Torres generated in his amazing [python notebook]( https://www.kaggle.com/vtorreslopez/wind-solar-and-nuclear-energy-production "python notebook"). It took less effort (in terms of coding) to generate my chart but this is exactly the strength of Kibana Lens. Anyone with a bit of curiosity can begin to explore data without needing to know the details of the underlying queries.

>  Kibana Lens simplifies the analysis process and lowers the barrier to entry for doing powerful data analysis.

Below is a line chart showing the wind production quantities for the European countries, which are separated using the “EU” filter:

![](https://miro.medium.com/max/3600/0*XkthOf8_NxqcnKIv)

I could continue to do different types of analyses here. For instance, if I wanted to analyze solar, wind or nuclear energy production for specific countries or regions, I just need to leverage my filters.

We can also analyze all three types of energy sources by certain countries. For instance, let's look at a few countries like Canada, the UK, and the US:

[![Watch the video](https://img.youtube.com/vi/uClfv9rOvKw/maxresdefault.jpg)](https://youtu.be/uClfv9rOvKw)

Note that the data lives in Elasticsearch which means that I can transform my data using ingest pipelines similar to what you would do using [pandas data frames](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html "pandas data frames"). Once the data is transformed we can perform even more advanced and interesting analyses. For instance, the raw data doesn’t include any additional information that gives you the ability to easily group countries by regions such as Europe and Asia — this is why I had to manually create separate filters. I can easily create my own grouping using a [script processor](https://www.elastic.co/guide/en/elasticsearch/reference/master/script-processor.html "script processor") and then perform an even broader analysis by region. I will leave this as an exercise or potential future post.

In summary, we learned about a new feature called Kibana Lens that you can use to easily and quickly analyze your data via suggested visualizations. We also did a basic analysis of the energy production dataset to obtain insights about the use of different energy sources from different countries over the last three decades or so. I strongly recommend Kibana Lens if you want to keep improving your data analysis skills.

Happy Analyzing!

**References:**

   -  [Introducing Kibana Lens](https://www.elastic.co/blog/introducing-kibana-lens "Introducing Kibana Lens")
   - [Wind, Solar, and Nuclear Energy Production](https://www.kaggle.com/vtorreslopez/wind-solar-and-nuclear-energy-production "Wind, Solar, and Nuclear Energy Production")
   - [Kibana Lens Overview: An easy, intuitive way to visualize Elasticsearch data](https://www.youtube.com/watch?v=6U7uoCyabcg "Kibana Lens Overview: An easy, intuitive way to visualize Elasticsearch data")
   - [International Energy Statistics](https://www.kaggle.com/unitednations/international-energy-statistics "International Energy Statistics")


