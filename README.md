# App Market Analysis

# Table of contents
1. [Introcduction](#introduction)
2. [Understand data](#understand)
3. [Check data format](#format)
4. [Check data type](#type)
5. [Check data validation](#validation)
6. [Check null value](#null)
7. [Show correlation](#correlation)
8. [Problem statment](#problem)

## 1. Introduction <a name="introduction"></a>
People nowadays own a smartphone. That leads we to believe that app market has a numerous potential to invest. And Playstore
is a wonderful resource to gain more insights about that market. 
!["@"](https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png)

##  2. Understand data <a name="understand"></a>
Here is my `explaination` about data:

!["@"](images/understand-data/explain-data.png)

And here is about the `number` of `rows` and `columns`:

!["@"](images/understand-data/row-and-column.png)


##  3. Check data format <a name="format"></a>
After checking all unique values from each column, I find out:

### **`Size`, `Installs`, `Price` have a wrong format** ###

- Size<br></br>
!["@"](images/check-data-format/size.png)

- Installs<br></br>
!["@"](images/check-data-format/install.png)

- Price<br></br>
!["@"](images/check-data-format/price.png)

- We know that 1MB = 1024KB and we agree that  all units of `Size` into `MB`. Here is my result:<br></br>
!["@"](images/check-data-format/result-fix-format.png)

### **`Genres` based on `Category`, but they don't match each other** ###

- Genres<br></br>
!["@"](images/check-data-format/genres.png)

- Category<br></br>
!["@"](images/check-data-format/category.png)

- Here is my result:<br></br>
!["@"](images/check-data-format/result-category-genre.png)

##  4. Check data type <a name="type"></a>
- Let's see data type of all columns:<br></br>
!["@"](images/check-data-type/data-type.png)
- We only need to solve `Installs`, `Size`, `Price`, `Last Updated`. Here is my result:<br></br>
!["@"](images/check-data-type/result.png)

##  5. Check data validation <a name="validation"></a>
With the basic rule we know such as: `Rating` must be in `[0-5]` and `Reviews`, `Size`, `Installs` must be `positive number`. Here is my progress:

!["@"](images/check-data-validation/result.png)

##  6. Check null value <a name="null"></a>
- Let's glance over the following picture:<br></br>
!["@"](images/check-null-value/data-info.png)

- Here is my key findings:<br></br>
!["@"](images/check-null-value/key-findings.png)

- Now we solve null value in `Type`:<br></br>
!["@"](images/check-null-value/type.png)<br></br>
Because this is a `categorical` data which just has `two` groups. So we will `replace` with its `mode`.

- It's `Android Ver`'s turn:<br></br>
!["@"](images/check-null-value/android-ver.png)<br></br>
Because this is a `categorical` data and there is` no particular` data that we can replace with it. Furthermore, it only takes `0.02%` of total rows from the given dataset so we can `remove` it.<br></br>
- We can handle `Current Ver` likes the way we handle Android Ver<br></br>
!["@"](images/check-null-value/current-ver.png)<br></br>
- For `Size`:<br></br>
!["@"](images/check-null-value/size.png)<br></br>
Becasue this is a `numerical` data and it takes `12.7%` of total rows. If we drop them, it may `impact` the `data quality`. So we will replace them by `mean` / `median`. We need to check `data distribution`:<br></br>
!["@"](images/check-null-value/size-distribution.png)<br></br>
It's clear that the Size is `Positive skew` / `right-skewed` -> we will `replace` null value in Size column with its `median` 

- For `Rating`:<br></br>
!["@"](images/check-null-value/rating.png)<br></br>
Becasue this is a `numerical` data and it takes `15%` of total rows. If we drop them, it may `impact` the `data quality`. So we will replace . We need to check `data distribution`:<br></br>
!["@"](images/check-null-value/rating-distribution.png)<br></br>
It's clear that the Size is `Negative skew` / `left-skewed` -> we will `replace` null value in Size column with its `median` 

##  7. Show correlation <a name="correlation"></a>
Here is a heat map chart:

!["@"](images/check-correlation/correlation.png)

And this is my key findings:

!["@"](images/check-correlation/key-findings.png)

## 8. Problem statement <a name="problem"></a>

**Question 1:** How much is maximum potential users for each target user that we can reach ? How much is maximum capacity that each target's device have ?
- The answer for the first question:<br></br>
!["@"](images/problem-statement/1/maximum-potential-user.png)<br></br>
- The answer for the second question:<br></br>
!["@"](images/problem-statement/1/maximum-capacity.png)

**Question 2:** Ratio of Free Apps vs Paid Apps ?

!["@"](images/problem-statement/2/ratio.png)

**Question 3:** How user consider "Affordable App" ?<br></br>
!["@"](images/problem-statement/3/affordable-price.png)<br></br>
- Here is my key findings:<br></br>
!["@"](images/problem-statement/3/key-findings.png)

**Question 4:** Which category attracts user most ?

!["@"](images/problem-statement/4/popular-category.png)<br></br>
- Here is my key findings:<br></br>
!["@"](images/problem-statement/4/key-findings.png)

**Question 5:** Most popular apps will probably have a high rating ?

!["@"](images/problem-statement/5/rating-installs.png)
- Here is my key findings:

!["@"](images/problem-statement/5/key-findings.png)