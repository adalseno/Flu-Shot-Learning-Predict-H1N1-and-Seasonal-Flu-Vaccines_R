![flushot](https://drivendata-public-assets.s3.amazonaws.com/flu-vaccine.jpg)
# Flu Shot Learning: Predict H1N1 and Seasonal Flu Vaccines in R

This is a R markdown version of the [benchmark file in python](https://www.drivendata.co/blog/predict-flu-vaccine-data-benchmark/) by [Jay Qi](https://www.drivendata.co/#jay-qi) for [Flu Shot DrivenData competition](https://www.drivendata.org/competitions/66/flu-shot-learning/).
I'm pretty confident in python but I'm a newbie in R so I thought that translating some python code would have been a good way to practise and improve my skills. I did my best to mimic the output of python code wherever possible. For example I reversed the factor order in ggplot (actually ggplot2). Please note that ggplot wants data in long format not in wide one so I had to change some code for plotting. I haven't been able to plot the graphs side by side like in python (if some R expert wants to give me a hint he's more than welcome).

I haven't been able to reproduce everything though. I could not find something similar to `MultiOutputClassifier` in R so I made the predictions separately. Anyway it worked fine with the same final result.

Obviusly there will be more elegant and effective way of coding and I hope I didn't make too many mistakes (I don't think one would have followed the same approach in R, though). I stuggled when it came to pass the variables to the plotting function: the difference among sym, ensym and {{}} is not completely clear to me (in this way I find python more consistent).

There are some weird things, I know, for example I tried to mimic pandas behaviour for index when I loaded `submission.csv`
```
  submission_df <- read.csv('submission_format.csv', header=TRUE, row.names="respondent_id")
```
The problem is that row.names in R are strings so I had to convert it back to column and then to integer. It doesn't make much sense, but helped me to learn new functions that might be useful in the future. Similar things for DataFrames: R and pyton use diferent approaches and I had to adapt while trying to keep close to the original code. Probably not very R friendly (is there a word like pythonic in R?).

I didn't upload the data files. You can get them from DrivenData or in another [repository of mine](https://github.com/adalseno/Flu-Shot-Learning-Predict-H1N1-and-Seasonal-Flu-Vaccines). My advice is to create a project in RStudio in a new folder with the Rmd file and the data files.

The text is taken as is from the original file even where R has a completely different approach. The code is simple and straighfoward so it should be easy to understand everything. The html file is the kintr version of the Rmd file with code and output, give it a look. I hope you will enjoy.
