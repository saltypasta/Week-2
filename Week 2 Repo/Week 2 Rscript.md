install.packages("RCurl")
library("RCurl")
x <- getURL("https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv", .opts = list(ssl.verifypeer = FALSE))
x <- getURL("https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv", .opts = list(ssl.verifypeer = FALSE))
y <- "https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv"
documents2 <- read.csv(y)
y <- "https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv"documents2 <- read.csv(y)
x <- "https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv"
documents <- read.csv(x)
x
counts <- table(documents$Newspaper.City)
counts
x
documents <- read.csv(text = x, col.names=c("Article_ID", "Newspaper Title", "Newspaper City", "Newspaper Province", "Newspaper Country", "Year", "Month", "Day", "Article Type", "Text", "Keywords"), colClasses=rep("character", 3), sep=",", quote="")
View(documents)
counts <- table(documents$Newspaper.City)
counts
documents <- read.csv(x)
counts <- table(documents$Newspaper.City)
counts
write.csv(counts, "counts.csv")
getwd()
barplot(counts, main="Cities", xlab="Number of Articles")
years <- table(documents$Year)
barplot(years, main="Publication Year", xlab="Year", ylab="Number of Articles")
barplot(years, main="Keywords", xlab="Year", ylab="Keywords")
