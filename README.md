# Assignment4

install.packages("ggrepel")

library(ggrepel)
library(scales)
library(tidyverse)

movies<-read.csv("Top_10000_Popular_Movies.csv")
str(movies)

movies$year <- format(as.Date(movies$release_date), format = "%Y")
movies <- movies[which(movies$year>="2020" & movies$year<="2021"),]

F <- ggplot(data = movies, mapping = aes(x = release_date, y = popularity))

F + geom_point()
install.packages("ggplot2")
library(ggplot2)
F + geompoint()+ geom_text_repel(data = subset(movies, popularity > 500, max.overlaps = Inf), mapping = aes(label = original_title)) + labs(x = "Date", y = "Score for Popularity", title = "Top 10,000 Most Popular Movies") + scale_y_continous(labels = scientific) *.csv
