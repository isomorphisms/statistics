Due to the data-science craze, statisticians are now getting their wish and everyone is learning a little bit of statistics. Unfortunately statistics has been, for a long time, taught upside-down—with numeracy and ability to . If you don't believe me, try making money outside academia with the things statisticians [bang on](http://www.datatau.com "Just one example. Leo Breiman identified what I am talking about as a problem in his “two cultures” paper.") about. Or you can read
in `info -f R-data` (written in 1988) that then, as now, statisticians needed to load data into the computer before they could perform regressions upon it, and statisticians then were also not well-enough trained in the practical use of computers (not algorithms or data-structures or compilers—the facility to move stored text and numbers around to answer the questions you want to).

There is a long way between messy client data and `data(msleep)`.



After wasting a lot of time barking up the wrong trees, I want to save everybody else some time. What have I really used to answer clients' questions, for money? It was not a load of sophisticated machine-learning techniques or asymptotic formulae for special distributions.



There are alternative ways to do all these things—for example I won't talk about Python, but afaik it can replace both bash and `R` in most ways. My toolkit is `R` installed on a cheapish laptop running Ubuntu. I think it makes sense to learn new kit if the people you are collaborating with can't understand what you are doing with what you currently use. However, spending time learning new kit comes at the cost of spending time on productive work or on fun.

In the world I see around me, people are buying master and PhD degrees in hopes of getting a good job. [They](http://stats.stackexchange.com/questions/91863/what-to-learn-after-casella-berger/) are purchasing learning from scholars rather than practitioners.



## Getting, cleaning, storing, and loading data


### Getting: scraping



### Getting: AWS S3 website visit logs

### Getting: Mailgun email logs

` <january.2016.log.2 jq '.[]' | jq '.[] | {hap: .hap, what: .message, when: .created_at} | select(.hap=="opened")'`



### Cleaning: perl / ruby / python / bash


#### grep

#### grep -v

#### sed 's/useless//'


### Cleaning: nasty encodings




### Storing: 

#### csvlook

#### postgres




### Looking:

#### head

#### (head -2; tail -n +10000 | head) <infile.csv

#### inspect (some / subsampling)

#### cut -f1,4,5,7,8

#### wc -l
The `man` pages for Unix tools don't tell you that you will use some flags a lot more than others.

I regularly use `wc -l` in two ways: an obvious one, and a clever one. The obvious way is simply to ask how big my data file is. (How many observations? Should I print it to screen with `cut` or poke through with `cut | less`?)

The clever way is to combine `wc -l` with `tr`, `sed`, `grep -v`, `uniq -c`, etc,  to spit out individual lines of some datum I'm interested in (for example, using my AWS S3 website logs, print one line for every `GET` 



#### uniq -c
unix for poets

#### dplyr


#### jq

` <january.2016.log.2 jq '.[]' | jq '.[] | {hap: .hap, what: .message, when: .created_at} | select(.hap=="opened")'`




### Loading:

#### tail -F

#### read.csv

#### scan

#### arrow, spark, parquet, data.table





## Parsing data: splitting and looking


### csvcut -n

How many columns is a lot or a little?

```
i@scheherezade:~/humility/statistics$ csvcut -n city_data.csv 
  1: id
  2: name
  3: county
  4: created_at
  5: updated_at
  6: income
  7: violent_crime
  8: latitude
  9: longitude
 10: weather_high
 11: weather_low
 12: diversity_score
 13: women_score
 14: hs_score
 15: population
 16: politics
 17: cost_of_living
 18: car_dependency
 19: transit
 20: trees
 21: fips
 22: state_abbr
 23: density
 24: state
 25: pop_white
 26: pop_black
 27: pop_amerind
 28: pop_asian
 29: pop_other
 30: pop_mix
 31: pop_hawpac
 32: pop_race_tot
 33: is_oil
 34: is_tech
 35: is_defense
 36: unemployment_rate
 37: mean_commute_time
 38: education
 39: photo_url
 40: photo_credit
 41: photo_title
 42: households_with_kids
 43: median_list_price
 44: household_size
 45: percent_renters
 46: home_price_sqft
 47: housing_score
```



### dplyr


### cut


### some data structures

#### zoo, xts

#### POSIXlt, POSIXct

Dates and times are hard.

`lubridate`

#### lists in R

@contravariant finance example

##### dput


#### csv (flatfile) vs JSON

see @jq

` <january.2016.log.2 jq '.[]' | jq '.[] | {hap: .hap, what: .message, when: .created_at} | select(.hap=="opened")'`











## What is a regression and why is it useful?

http://isomorphism.es/post/41446182725/regression-beta-p

Numerically you have two columns of data (plus an id or key). For example 

```
i@scheherezade:~/humility/statistics$ csvcut -n city_data.csv 
  1: id
  2: name
  3: county
  4: created_at
  5: updated_at
  6: income
  7: violent_crime
  8: latitude
  9: longitude
 10: weather_high
 11: weather_low
 12: diversity_score
 13: women_score
 14: hs_score
 15: population
 16: politics
 17: cost_of_living
 18: car_dependency
 19: transit
 20: trees
 21: fips
 22: state_abbr
 23: density
 24: state
 25: pop_white
 26: pop_black
 27: pop_amerind
 28: pop_asian
 29: pop_other
 30: pop_mix
 31: pop_hawpac
 32: pop_race_tot
 33: is_oil
 34: is_tech
 35: is_defense
 36: unemployment_rate
 37: mean_commute_time
 38: education
 39: photo_url
 40: photo_credit
 41: photo_title
 42: households_with_kids
 43: median_list_price
 44: household_size
 45: percent_renters
 46: home_price_sqft
 47: housing_score
```







# Inspiring analyses

Todd W Schneider analysing $2tn of mortgages (200GB of loan-level data)

Treasury earnings.csv

City-data.csv (a data-vis master student in California)





# Valuable information your government is providing you with that you previously couldn't process

citizen journalism
