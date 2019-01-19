Data processing project

Using data from Global Terrorism Database https://www.start.umd.edu/gtd/
From 2014-2018

Trying to predict two things

First - number of casualties given basic info about attack, that is possible to gather before the attack happens.

Second - probability of an attack in a given place at a given date.

Going to update readme with notes of interesting stuff as I find it

For example, half of all attacks have 0 casualties and half of all attacks are bombings, interesting coincidence, gonna check how these halves intersect

Upd. Half of bombings have no casualties

Also there have been 1115 succesful bombings that have 0 casualties and 0 property damage

###############################################################################################################

Doing survey on data I found 2 most popular studies and read through them

https://towardsdatascience.com/global-terrorism-database-with-a-bayesian-inference-7d6e23ae5024

https://www.kaggle.com/laurenstc/global-terrorism-analysis

In short these works are focused on analyzing the data and finding general trends. There is already a lot of visualisation and because of it I decided not to focus on it as there already are great works done before.

Instead I chose to predict casualties of specific attacks as I did not see works done on it.

As I later found out there probably are no works on it as it's not possible to predict it using only GTD data

###############################################################################################################

By doing all the processing I came to the conclusion that it is not possible to achieve adequate results with this data as terrorist attacks are too random and unique to predict outcome based only on general data
The project can be expanded with incorporation of supporting dataset such as fullyear holiday schedule and population density, but I did not manage to find those for general cases,for example only population density data I found was for some countries and major cities but it wasn't feasible to collect all of them and get global data. There maybe exists global dataset but I failed to find it.

With data I had I did stuff I learned during semester to at least maximize results.
Next is cut out from poster as there is already most of my work explained

After analyzing the whole dataset I stripped
it from all columns that have no value to the
project. All longtext column (for example:
summary), subcolumns that have most of
values missing(weapontype_3), unrelated to
attack data(eventid, dbsourse) and the data
which cannot be gathered prior to an
attack(claim. Not the columns with number
of casualties though as it is what will be
predicted)

Then i proceeded with cleaning the missing
values in data. As the dataset was quite large
it seemed reasonable to drop all the rows
with missing values as it was only a small
portion of data and it would speed up the
calculations

Using one-hot encoding for categorical variables I end
up with unreasonable amount of columns so I used 2
approaches of Feature Selection

First idea was to apply PCA and Forward
Stepwise Selection as they are powerful and
simple to use methods. It allowed to shorten
dataset to 10% of initial size and in theory it gives
as accurate predictions as starting dataset

Another thing i done is manual picking of columns based on my
subjective opinion of their relevance. The categorical columns with
hundreds of possible values as well as some unimportant binary
variables were dropped. Interestingly, final accuracy was higher than
of a first FA method.
