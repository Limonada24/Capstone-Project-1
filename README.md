# Capstone-Project-1

Name: Dámaris Flores Albores  
Date: November 2022  

### The Steps  
1.- For this project we will start by evaluating the business needs and determine our key questions from which we will start our data exploration an analysis. 

2.- After that we will do a first data exploration of our given datasets and determined (based on our actual resources and timeline) the datasets to work with. 

3.- The next step will be cleaning our dataset: look for null data, renaming columns and changing the type of certain columns for analysis purposes.  

4.- More data exploration. We will look for outliers and some first descriptive statistics to have a better understanding of the data.  

5.- We will perform an hypothesis testing to proove if our findings are statistically significant.  

6.- At the same time we do the analysis, we will create some data visualizations to communicate our findings.  

7.- It's time to do our recommendation. Based on our findings we will get to a conclusion and translate it into actionable insights.  

8.- Explore further steps. Sugestion of next steps for a deeper analysis and more recomendations based on our client needs.  

# Business Understanding  

Computing Vision sees all the big companies creating original video content and they want to get in on the fun. They have decided to create a new movie studio.   
We are charged with exploring what types of films are currently doing the best at the box office using different samples of available data.  
Then will translate those findings into actionable insights that the head of Computing Vision's new movie studio can use to help decide what type of films to create.  

#### As  a new movie studio, what are the business needs?   

As we know, this is a newly formed movie studio, and their principal need, as any other business, is to get profits so it can keep doing movies.  

#### What does a succesfull movie means?  

For this purpose we will understand a succesfull movie as the one that is profitable.   

#### How much should be spend for a higher return of investment?  

Profits can be measured by their return of investment, so we will drive our analysis on this direction to be able to respond this question.   

# Data Understanding

First data exploration of our given data sets.   

* Box Office   
* IMDB  
* Rotten Tomatoes  
* Movie DB  
* The Numbers  

| Table Name   |# Entries|# Columns| Description                                                  |  
|--------------|:-------:|:-------:|------------------------------------------------------------  |  
|movie_gross   |3387     |5        |Movie, studio, year of release and domestic and foreign gross |  
|movie_info    |1560	 |12	   |General info of movies, like synopsis, rating, genre, director|  
|reviews       |54432	 |8	   |Reviews and ratings                                           |  
|movies	       |26517    |10	   |Popularity and votings                                        |  
|budgets       |5782	 |6	   |Production budget and worldwide gross                         |  
|persons       |606648	 |5	   |Name, id, primary profession                                  |  
|known_for     |1638260	 |2	   |Person id, movie id                                           |  
|directors     |291174	 |2	   |Person_id, movie id                                           |  
|writers       |255873	 |2	   |Person id, movie id                                           |  
|movie_basics  |146144	 |6	   |Title, release date, runtime and genre                        |  


![Roi Histogram](/Visualizations/roi_hist.png)   

![Roi by Budget](/Visualizations/roi_by_budget.png)

![Roi KDE](/Visualizations/KDE_roi.png)   

![Percent ROI](/Visualizations/percent_roi.png) 

![Average ROI](/Visualizations/averageroi_budget.png)  

It seems we have a really big difference between the rest of the movies.  

This will give us the perfect opportunity for an hypothesis testing.  

#### Let's try!   

## Hypothesis Testing  

#### H1 = The ROI of low budget movies is higher than the rest of movies.   

#### H0 = The ROI of low budget movies is not different from the rest of the movies  

# First we will named our variables   

mu = budgets['ROI'].mean()  
x_bar = low_budget['ROI'].mean()  
sigma = low_budget['ROI'].std()  
n = len(low_budget['ROI'])  
df = n-1  
diff = x_bar - mu   

t = (x_bar -  mu)/(sigma/np.sqrt(n))
t  

#### 3.362079435878072   

![T-test](/Visualizations/t_stat.png)   

Visually we could determined that is possible to reject our null hypothesis.  

### Yes! It is possible to reject our null hypothesis!  
## Our ROI is significantly higher on the low budget movies!  

# The Recommendation  

Based on our findings, there is a greater rate of success on high budget movies, despite this fact,  
the average roi is of only 1.6.  
At the other side, there is more risk with low budget movies, just 51% of them achieve a return of their ivestments,  
but they have a much higher *(statistically significant higher)* return of investment.   

So, what's the recommendation?   

### Diversify!   

You should be aware that low budget movies had a lower rate of success but there's a great chance of getting  
more than six times the money you spend! In the other hand, a couple of high budget movies will ensure you have  
more chances of succes. 
#### Something is better than nothing!! 

# Next Steps  

#### So, what is next?  

There are a lot to do now. 

Whats the ratio of low and high budget movies you shoould have on your portafolio?   
Why do some movie fail?    
Which kind of movies are the most profitable ones?    
Which genre gives you the better profits?    
There is a relation between popularity, ratings and profits?    

# Thank you!!  






 