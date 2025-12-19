print("Welcome to PSTAT123")
print(Welcome to PSTAT123) # note error message
print("Welcome to PSTAT10", quote = FALSE) # the print function

# Create an R object 'OurString' assigned the value "Welcome to PSTAT10"
OurString <-"Welcome to PSTAT10"
OurString

# Calculator
3*4
4**2

# Enter test scores. These are scalars.
Test_Scores <-c(8,7,8,10,5) 
Test_Scores

class(Test_Scores)
mean(Test_Scores)
median(Test_Scores)

# Bob, Alice, Alex, Juan and Amy have test scores 8,7,8,10,5 respectively.
Test_Results <-c("Bob" = 8, "Alice" = 7, "Alex" = 8, "Juan" = 10, "Amy" = 5)

# How many elements are there in Test_Results?
length(Test_Results)
? length()

# Create a vector of the mileages.
MILEAGE<- c(65311,65624,65908)
MILEAGE

# Use the diff function to show the number of miles between fill-ups
x <- diff(MILEAGE)
x

# 둘 차이
MILEAGE2 <- c(66200, 66533, 66856)
MILEAGE3 <- c(MILEAGE, MILEAGE2)
z <- diff(MILEAGE3)
z

# Combining objects with different types
both <- c("dog",3,"cat","mouse",7,12,9,"chicken")
class(both)

# a deliberate error
mean(both)

# Construct the sequence 1-10 as a vector, using the colon operator
series <- 1:10
series

is.vector(series) # a new function

# Use the sequence function to construct the vector 1 2 3 4 5 6 7 8 9 10
x <- seq(1, 10)
is.vector(x)

# Construct a sequence starting at 1 and ending at 10 by increments of 0.5
seq(1, 10, by = 0.5)

# sequence of a given length
seq(10, 20, length = 7 )

# shows the syntax of the repetition function
?rep() 
help("rep")

rep(3, times=5)
rep(x=3, times=5)
rep(1:4, 2)
rep(1:4, each = 2)
rep(1:4, each = 2, length = 4)

# Sorting a vector using the sort function
Test_Scores <- c(8,7,8,10,5)
sort(Test_Scores, decreasing=FALSE)

sort(Test_Scores)
# increasing is the default

sort(Test_Scores, decreasing=TRUE)
# decreasing

# the 'any' function. Testing a logical condition.
any(Test_Scores<7)

# the 'all' function. Testing a logical condition.
all(Test_Scores<7) 

#Accessing Elements of a Vector
x <- c(1,7,3,10,5)

# return the 4th element.
x[4]

# return every element except the 2nd
x[-2]

x[2:4]

#Load the dataset 'state'
data("state")

# Remove unwanted datasets
rm(state.center)

rm(state.division)

rm(state.region)

rm(state.x77)

# Is state.area a vector?
is.vector(state.area)

# histogram
hist(state.area , breaks = "Sturges", col="YELLOW", xlab= "STATE AREAS (sq. miles)", main = paste("Histogram of State Areas"))

# options(scipen = 999) turns off scientific notation
hist(state.area , breaks = "Sturges", col="ORANGE", xlab= "STATE AREAS (sq. miles)", border = "BLUE", main = paste("Histogram of State Areas")) options(scipen = 0)

# stem plot
x <- c(12,15,24,29,30,31,52,58,60,63)
stem(x, scale=2)

# library(statip)
y <- c(1,1,1,6,7,4)
mfv(y)

range(y)

sd(y)

# quantiles

df <- c(12,3,4,56,78,18,46,78,100)
quantile(df)

IQR(df)

summary(df)

fivenum(df)

#summary
G <- c(12,3,4,56,78,18,46,78,100,2000,1789)

summary(G)
# five number summary

fivenum(G)

# outliers

# boxplot.stats()returns several results including the five number summary,

#length of the vector, confidence interval and outliers.

# We are not concerned with confidence intervals at present.

boxplot.stats(G)

#improved boxplot of 'state area'
boxplot(state.area, col="YELLOW", border="BLUE", main="Boxplot of state area data", horizontal = TRUE)

options(scipen = 999)
# turns off scientific notation

# boxplot
boxplot(wt~cyl, data=mtcars, main=toupper("compare Vehicle Weight to number of cylinders"), xlab= "Number of Cylinders", ylab="Weight",col="pink")

# Charting qualitative data: Bar Chart
Dogs <- c(1,4,6,10)
Breed_name <- c("Alsatian", "Collie", "Pug", "Beagle")
barplot(dogs,names.arg = breed_name, xlab="BREED", ylab="Number of Dogs", col= "GREEN", main="DOG CHART",border="BLACK")

# Charting qualitative data: Pie Chart

X <- c(4,5,6,1,4)
Labels <- c("Comedy", "Action", "Romance", "Drama", "SciFi")
pie (x, labels, radius=0.8, main="Movies", col= rainbow(length(x)), clockwise = TRUE)

# Missing Values denoted by NA. 
Test_Results <- c("Bob" = 8, "Alice" = 7, "Alex" = 8, "Juan" = 10, "Amy" = 5)
mean(Test_Results)

# Add student Jim, who was excused the test.
Test_Results_1 <- c("Bob" = 8, "Alice" = 7, "Alex" = 8, "Juan" = 10, "Amy" = 5, Jim = NA)

mean(Test_Results_1) # Ignore missing values
mean(Test_Results_1, na.rm = TRUE)


# The intersect() function

x <- c(10, 20, 30, 20, 20, 25, 29, 26)
y <- c(10, 50, 30, 20, 20, 35, 19, 56)
z <- c(10, 40, 30, 20, 20, 25, 49, 26)

# Print Common elements from above vectors)
Result1 <- intersect(x,y)

# Deliberate error
Result2 <- intersect(x,y,z)

result3 <- intersect(intersect(x,y),z)
print(result)

# EXAMPLE generate a 5 x 4 numeric matrix
Y <- matrix(1:20, nrow=5,ncol=4, byrow=FALSE)
y

y[,3]
# 3rd column of the matrix

y[3,]
# 3rd row of the matrix

y[2:4,1:3] # rows 2,3,4 of columns 1,2,3

dim(y) # the dimensions of a matrix. Row by column.

HEC <- c(32, 11, 10, 3, 53, 50, 25, 15, 3, 30, 5, 8)

# Construct the matrix.
HairEyeColor <- matrix(HEC, nrow=3, ncol=4, byrow=TRUE) # fill by row
HairEyeColor
dim(HairEyeColor)

#Add appropriate row names and column names
rnames <- c("Black Hair", "Brown Hair", "Blond Hair")
cnames <- c("Brown Eyes", "Blue Eyes", "Hazel Eyes", "Green Eyes")

HairEyeColor <- matrix(HEC, nrow=3, ncol=4, byrow=TRUE,
dimnames=list(rnames, cnames) )
HairEyeColor
rowSums(HairEyeColor)

# Determine how many people with Blond hair have Blue eyes.

HairEyeColor["Blond Hair","Blue Eyes"]

# Sum rows, sums colmns

HairEyeColor <- addmargins(HairEyeColor)
HairEyeColor

# the apply() function

x <- apply(HairEyeColor, 1, sum) # sum the rows
print(x)

y <- apply(HairEyeColor, c(1,2), sum) # rows and columns

# LECTURE 4 DEMO 3 Modifying a Matrix

# Use rbind and cbind functions to create a matrix from three vectors

a <- c(1,2,4,5,6)
b <- c(3,2,4,1,9)
d <- c(7,5,5,6,4)

CC <- cbind(a,b,d) # Combine by Column
CR <- rbind(a,b,d) #Combine by Row

## Remove column 'a' from matrix named 'CC'
CC <- subset(CC, select=-a) 

#Replace the first row of 'CC' with the sequence 1:2
CC[1,] <- 1:2

# Replace the second column of matrix CR with the sequence 4:6
CR[,2] <- 4:6

# create an array
vector1 <- c(5,9,3)
vector2 <- c(10,11,12,13,14,15)
result <- array(c(vector1,vector2),dim = c(3,3,2))
print(result)

# add names

column.names <- c("COL1","COL2","COL3")
row.names <- c("ROW1","ROW2","ROW3")
matrix.names <- c("Matrix1","Matrix2")
result <- array(c(vector1,vector2), dim = c(3,3,2), dimnames =list(row.names,column.names,matrix.names))
print(result)

# Calculations Across Arrays
aaa <- c(2,3,4,6)
bbb <- c(5,6,10,12,45)
new.array <- array(c(aaa,bbb),dim = c(3,3,2))
print(new.array)

# sum the rows
result <- apply(new.array, 1, sum) # sum the rows in new.array
print(result)

# sum the columns
result <- apply(new.array, 2, sum)

print(result)

# sum each of the cells

result <- apply(new.array, c(1,2), sum)
print(result)

# ensures type integer
w <- as.integer(c(0:10, 48))

# Use the vector w to construct a 4*3 matrix
new_matrix <- matrix(w, 4) # data is the vector w. number of rows is 4
new_matrix2 <- matrix(w, 4, 3) # same result

# change the column names to x, y, z; the row names to a, b, c, d.
colnames(new_matrix) <- c("x", "y", "z") ;
rownames(new_matrix) <- c("a", "b", "c", "d") ;

# byrow is an option, or argument, in matrix(). The default is FALSE. change to TRUE
new_matrix <- matrix(new_matrix, 4, byrow = TRUE) ; print(new_matrix)

# Create a list of the scalars 7,8,17
My_List <- list(7,8,17)
is.list(My_List)

length(My_List)

# return the 2nd element of the list.
My_List[2]

# returns the 2nd and 3rd elements of the list.
My_List[c(2,3)]

# Member reference using DOUBLE square bracket notation.

# changing list elements
My_List[[2]]+3 # NOTICE: My_List[2]+3 returns an error

# Add to an element in the list
My_List[[3]]

# references element 3 of My_List
My_List[[3]] <- paste(My_List[[3]], " MATH") # adds math to element 3 of MyList


# LECTURE 5: LOGICAL VALUES and FACTORS

x <- c(1:9)
y <- c(1:12)
z <- c(1:15)

my_list <- list(x,y,z)

# use lapply() used on a list. Returns a list
lapply(my_list, sum)

# use sapply() on a list. Returns a vector of the data.
sapply(my_list, sum)

# How many US states have an area less than 10 000 sq miles?
SmallState <- state.area < 10000

# How many US states have an area greater than 100 000 square miles?
LargeState<- state.area > 100000

# SmallState | LargeState # use the OR operator from the table.
sum(SmallState | LargeState)

# How many US states have an area greater than 100 000 square miles AND

# less than 10 000 square miles?

# Notice: this is impossible so the answer should be 0.

sum(SmallState & LargeState) # an impossibility

x <- sort(state.area)
which(x >= 158693)
which(state.area==5009)

# Create a factor with elements: male, female, female, male
gender <- factor(c("male","female","female","male"))

levels(gender)

# How many levels are there?
nlevels(gender)

# table returns a frequency table
table(gender)

# plot returns a bar chart
plot(gender)

Class_grades <- factor(c("A", "B"))
Class_grades <- ordered(c("A", "B"))

nlevels(Class_grades)

is.factor(Class_grades)


# Using sub() to replace the first match only in a string

# syntax: sub(old, new, string)
y <- c("Hello, PSTAT 10")
sub("PSTAT 10", "MATH 8", y)

# gsub function in R (global replacement)
x <- c("Hello, Hello World") # notice this is a single string
gsub("Hello", "Hi", x)

which(LETTERS == "X") # X is position 24 in the alphabet

# Assignment operator: local and global
x = 5

# This assigns the value 5 to x locally
X <- 5

# This assigns the value 5 to x globally
x == 5 # This checks to see if x equals 5

# Assignment operator (local)
# Delete x
rm(x)
mean(x=1:10)
sum(x)
x

# Assignment operator (global)

# Delete x
rm(x)
mean(x <- 1:10)
sum(x)
x

# Mode again. We installed install statip.
x <- c(10, 20, 30, 20, 20, 25, 29, 26)
mfv(x)

# install DescTools
Mode(x)

# note: mode() in lower-case
mode(x)

# Construct a data frame named 'My_DF'using these 3 vectors.
d <- c(2,3,4,6)
e <- c("red", "white", "red", "green")
f <- c(TRUE,TRUE,TRUE,FALSE)
My_DF <- data.frame(d,e,f )

# define row names
my_row_names <- c("one", "two", "three", "four")

# add row names
My_DF <- data.frame(d,e,f, row.names = my_row_names)

#select columns d and f only and name this object My_DF2
My_DF2 <- My_DF[, c("d","f")]

#select column e and name this object My_DF3
My_DF3 <- My_DF[, c(1,2)]

#select row "one" and name this object My_DF4
My_DF4 <- My_DF[c("one", "two"),]

# is 'iris' a data frame?
dim(iris)

# the dimensions of 'iris'. 150 observations of 5 variables
ls(iris)

# Shows the names of objects (variables) in 'iris'
names(iris)

# also shows the names of objects (variables) in 'iris'

# Print the first 5 rows of data
head(iris, n=5)
tail(iris, n=5)

# Remove petal Width from iris.
my_iris_data1 <- subset(iris, select= -Petal.Width)
head(my_iris_data1, n=5)

# Remove petal Width and species iris.
my_iris_data2 <- subset(iris, select=-c(Petal.Length, Species))
head(my_iris_data2, n=5)

#Keep only PetalLength and Species
my_iris_data3 <- subset(iris, select= c(Petal.Length, Species))
head(my_iris_data3, n=5)

#Removing (or keeping) many colums.
my_iris_data4 <- subset( iris, select =-c(Sepal.Width:Species) )
head(my_iris_data4, n=5)

# numeric summary
summary(iris)

names(iris)

#histogram of petal length. Note the use of $.
hist(iris$Petal.Length)
mean(iris$Petal.Length)
median(iris$Petal.Length)
sd(iris$Petal.Length)

# create side-by-side boxplots comparing
#petal length for each species
boxplot(Petal.Length~Species, data=iris, main=toupper("Petal.Length~ to Species"), xlab= "Species", ylab="Petal.Length",col="pink")

FirstName <- c("Ann", "Paul", "Bob")
LastName <- c("Smith", "Liu","Lopez")
Department <- c("Math", "Physics", "Biology")

# Combine into an R object
Faculty_Profile <- cbind(FirstName,LastName,Department)
Faculty_Profile

New_Faculty_Profile <- data.frame(FirstName = c("John","Sara","Jane"), LastName = c("Day", "Brown","Green"), Department = c("History", "English", "PSTAT"))
New_Faculty_Profile
is.data.frame(New_Faculty_Profile)

# a data frame

# Join Faculty_Profile and New_faculty_profile
All_Faculty_Profile <- rbind(Faculty_Profile, New_Faculty_Profile)
All_Faculty_Profile

# Export All_Faculty_Profile to your working directory as a csv file
write.csv(All_Faculty_Profile, "All_Faculty_Profile2.csv")

getwd()

# Import All_Faculty_Profile
read.csv("All_Faculty_Profile2.csv")

# Missing Values in a data frame
Missing_Values <- data.frame(x=c("PSTAT",2, TRUE), y=c(5, NA, 8))
Missing_Values

is.data.frame(Missing_Values)

na.omit(Missing_Values)

data("faithful")
is.data.frame(faithful)
head(faithful, n=10)

# two different ways of producing the histogram.
duration <- faithful$eruptions
hist(duration)
hist(faithful$eruptions)

# Improve the histogram of 'duration'.
# define your own color palette.
color <- c("red", "orange", "yellow", "blue", "green", "red", "orange", "yellow")
hist(duration, col=color)

# Generate a stem and lef plot of the eruption durations
duration <- faithful$eruptions
stem(duration, scale=2)

# summary statistics
summary(duration)
boxplot(duration)

# a simple scatterplot of petal length vs. petal width
#petal length is column 3, petal width is column 4
plot (iris[ , 3], iris[ , 4])

plot(iris$Petal.Length, iris$Petal.Width, main="Edgar Anderson's Iris Data")
#Choose 3 colors for the 3 different species. Use pch, which means 'plot character'.
# pch=21 for filled circles, pch=22 for filled squares,
plot(iris$Petal.Length, iris$Petal.Width, pch=21, bg=c("red","green3","blue"), main="Edgar Anderson's Iris Data")

head(iris, n=10) # show a few rows of the dataset

cor(iris$Petal.Length, iris$Petal.Width)

scatter.smooth(iris$Petal.Length,iris$Petal.Width)

# As petal length increases, petal width increases

# an alternative way of producing a scatterplot. Data looks linear. Positive slope

# Next We would check for outliers. There are tests to do this but we will not go

# into details at this point. By observation, there appear to be no outliers)

# Fit a simple linear regression model using iris$Petal.Length as the explanatory variable

# and score as the iris$Petal.Width variable:
BestFit <- lm(iris$Petal.Width ~ iris$Petal.Length, data=iris)







오답노트

#1
2차원 인덱싱 ([,]) = 벡터에는 차원이 없어서 이러면 오류남

#2
X[-3] = 세 번째 원소(30)를 제외한 나머지 전부 추출
	뒤에서 세번째를 추출하고 싶으면 x[length(x) - 2]

#3
unique() 함수는 벡터에서 중복을 제거하고 순서를 유지해서 반환함

#4
nums <- c(10, 20, 30, 40)
Nums <= 40 
40보다 작은 숫자를 반환함

#5
mean(x, na.rm = TRUE)

#6
 data <- data.frame(name = c("A", "B", "C"), score = c(80, 90, 70)) "score" 열만 추출하는 코드로 올바른 것은?
data["score"]
data$score
data[, "score"]

#7
cor(x, y)는 x와 y 사이의 **상관계수(correlation coefficient)**를 구해줘.
값이 1에 가까우면 강한 양의 상관
-1에 가까우면 강한 음의 상관
0에 가까우면 상관 거의 없음 이라는 뜻이야.

#8
x <- c("a" = 1, "b" = 2, "c" = 3)
x["b"]
x["b"]는 이름이 "b"인 요소를 가져옴
R에서 []는 항상 벡터를 반환하거든.
그리고 벡터는 원소에 이름이 있으면 같이 보여줘.
이름이 붙어 있지 않으면 그냥 숫자만 나와



#9
my_list[2] 두 번째 요소를 리스트 형태로 반환
list(10) my_list[[2]] 두 번째 요소의 값만 추출
[]는 리스트 안에 담긴 상태 그대로 주고 [[ ]]는 안에 있는 것만 꺼내는 느낌

#10
list() 는 서로 다른 타입의 값들을 한 덩어리로 묶을 수 있는 구조
my_list <- list(5, "hello", TRUE, c(1, 2, 3))
vector 하나의 타입(예: 숫자만, 문자만 등)만 저장 가능 list 모든 타입 혼합 가능 (숫자 + 문자 + 벡터 등)
리스트는 "리스트 안에 상자 여러 개"가 있는 구조

my_list = [
  [[1]] = 5,
  [[2]] = 10,
  [[3]] = 15
]

My_list[2] = list(10)
My_list[[2]] = 10

#11
matrix(1:6, nrow = 2)

     [,1] [,2] [,3]
[1,]    1    3    5
[2,]    2    4    6

apply(m, 1, sum) 은 행 기준으로 sum 수행 = 9, 12
각 행의 합: 1행: 1 + 3 + 5 = 9 , 2행: 2 + 4 + 6 = 12

#12
x <- c(4, 8, NA, 6)
mean(x)

= NA

#13
x <- c(5, 12, 8, 20, 3)
x > 10

결과 : [1] FALSE  TRUE FALSE  TRUE FALSE

TRUE는 1, FALSE는 0 으로 간주되어
sum(c(FALSE, TRUE, FALSE, TRUE, FALSE))
== sum(c(0, 1, 0, 1, 0))
== 2

#14
df <- data.frame(x = c(1, 2, 3), y = c("a", "b", "c"))
subset(df, x > 1)

  x y
1 1 a
2 2 b
3 3 c

subset(df, x > 1) 은 x가 1보다 큰 행만 선택해줘 = 

  x y
2 2 b
3 3 c

#15
gender <- factor(c("male", "female", "female", "male"))
nlevels(gender)

factor()는 범주형 자료를 만든다
"male"과 "female" → 총 2개의 레벨이 존재해
gender를 **범주형 변수(factor)**로 저장하고
자동으로 중복을 제거한 고유값 = 레벨(level) 로 저장해

nlevels()란? "이 factor에는 레벨(level)이 몇 개 있나요?" 를 알려주는 함수야! = 2 출력
levels() 레벨 이름들을 문자벡터로 보여줌 "female" "male"
nlevels() 레벨의 개수만 숫자로 보여줌 2

벡터는 그냥 데이터들 ("apple", "apple", ...)
factor는 그 안에 "이 데이터는 총 몇 가지 종류야" 라는 정보까지 갖고 있음!
("값 + 범주 정보(= level)"를 가진 벡터)
이때 level은 "가능한 고유 값들(범주)"을 의미해!


#16
grades <- factor(c("A", "B", "A", "C", "B", "A"))
table(grades)

table() 함수는 각 레벨별로 등장 횟수를 세서 출력해줌 = 
A B C 
3 2 1

Factor () 은 범주형 데이터(categorical data)를 표현할 때 사용하는 특별한 데이터 타입을 만드는 함수
gender <- c("male", "female", "female", "male") 는 그냥 문자 벡터일 뿐인데
gender <- factor(gender) 로 바꾸면 "이건 문자이기도 하지만, 고유한 그룹 2개를 가진 범주형 데이터야!" 라고 인식함 (문자데이터를 범주형 데이터로 바꿔줌)

#17
m <- matrix(1:9, nrow = 3)
m[2, 3] = 6

     [,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9

#18
my_list <- list(score = 95, grade = "A")
my_list$score

$score
[1] 95

$grade
[1] "A"

#19
df[행번호, 열번호]
df <- data.frame(name = c("Ann", "Bob", "Cara"),
                 score = c(80, 90, 85))
df[2, ]
=
  name score
2  Bob     90


#19
df <- data.frame(name = c("Ann", "Bob"), score = c(85, 90))
df[["score"]]

= [1] 85 90


#20
df <- data.frame(name = c("Ann", "Bob", "Cara"),
                 score = c(80, 90, 85))
subset(df, score >= 85)

= 
  name score
2  Bob     90
3 Cara     85

#21

subset(data, 조건, select = 열이름들)

조건으로 행 추출 subset(df, score > 80) = 
  name score
2  Bob     90
3 Cara     85

특정 열만 보기 subset(df, select = name) =
  name
2  Bob
3 Cara

조건 + 열 둘 다 subset(df, score > 80, select = name) =
  score
1    80
2    90
3    85


#22
cor() 함수는 **상관계수(correlation coefficient)
1 완벽한 양의 상관관계
0.5 약한 양의 상관관계
0 거의 무관함 (상관 없음)
-1 완벽한 음의 상관관계

#23
data <- c(1, 2, 3, 4, 5, 100)
boxplot(data)

R의 boxplot()은 자동으로 이상치(outlier) 를 판단해서 따로 점으로 찍어줘 = 100
출력 결과는: 중간값(Median), 사분위수(Q1~Q3), 그리고 100은 이상치로 따로 점(⚫️) 표시됨

#24
sapply(리스트, 함수)
리스트의 각 요소에 함수를 적용하고, 가능하면 벡터로 반환해주는 함수야!

#25
v <- c("a", "b", "c", "a", "b", "a")
다음 중 "a"의 개수를 세는 올바른 방법은? sum(v == "a")

#26
apply()는 행렬에,
sapply()는 리스트에 사용

m <- matrix(1:6, nrow = 2)
#      [,1] [,2] [,3]
# [1,]    1    3    5
# [2,]    2    4    6

apply(m, 1, sum)  # 행별 합
# [1] 9 12

apply(m, 2, sum)  # 열별 합
# [1] 3 7 11

my_list <- list(c(1,2), c(3,4,5), c(10))

sapply(my_list, length)
# [1] 2 3 1

#27
Dim이란?
dim = dimension = 차원
R에서 배열(array)이나 행렬(matrix)을 만들 때 **크기(형태)**를 지정해주는 옵션
m <- array(1:6, dim = c(2, 3))  # 2행 3열짜리 행렬

     [,1] [,2] [,3]
[1,]    1    3    5
[2,]    2    4    6

a <- array(1:12, dim = c(2, 2, 3))

, , 1
     [,1] [,2]
[1,]    1    3
[2,]    2    4

, , 2
     [,1] [,2]
[1,]    5    7
[2,]    6    8

, , 3
     [,1] [,2]
[1,]    9   11
[2,]   10   12

#28
paste()란?
여러 값을 문자열로 합쳐서 하나로 만드는 함수
숫자든 문자든 다 문자열처럼 연결시켜줘.

paste(10, "points")
# 결과: "10 points"

#29
subset(df, score >= 80, select = c(name, score))

조건: score >= 80 → 행 필터
선택: select = c(name, score) → 열 선택
결과:
   name score
1  Anna    85
3 Cathy    92

subset(데이터, 행 조건, select = c(선택할 열))

#30
dataframe[ , c("열1", "열2")] ➜ 원하는 열만 고를 수 있어.
dataframe[c(행번호), ] ➜ 원하는 행만 고를 수 있어.


#31
select = c(...) 옵션으로 필요한 열만 골라줘.

subset(iris, select = c(Petal.Length, Species))
이건 말 그대로 "Petal.Length"와 "Species" 열만 선택하겠다는 뜻이야.

#32
iris$Petal.Length는 iris 데이터에서 Petal.Length 열만 뽑은 벡터.
따라서 mean(iris$Petal.Length)은 그 열의 평균을 구해주는 코드야!

#33
A) 산점도 (scatter plot) =plot()
B) 막대그래프 (barplot) =barplot()
C) 박스플롯 (boxplot) (=중앙값 (median), 사분위수 (Q1, Q3), 이상치 (outliers), 전체 범위)
D) 선그래프 (line plot)

#34
iris 데이터에서 Petal.Width 열을 제거하고 싶은 경우, 가장 적절한 코드는?
subset(iris, select = -Petal.Width)

subset()은 R에서 데이터프레임이나 벡터에서 특정 조건이나 열만 뽑고 싶을 때 사용하는 아주 유용한 함수야.

#35
All_Faculty_Profile을 현재 작업 디렉토리에 CSV 파일로 저장하기 위한 코드로 알맞은 것은?
= write.csv(All_Faculty_Profile, "All_Faculty_Profile2.csv")

#36
결측값이 들어 있는 행 전체를 제거해줘.
na.omit(df)

#37
write.csv(All_Faculty_Profile, "All_Faculty_Profile2.csv")
read.csv("All_Faculty_Profile2.csv")


