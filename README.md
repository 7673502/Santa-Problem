_This problem was written by Pramod Anandarao for the 2021 RMC Python and Machine Learning Course_

# Problem 1: Saving Christmas
**Warning! Challenging problem ahead, with a lot of reading!**

You are one of Santa's Elves on vacation and are returning to the workshop to help decide what type of present each and every person in the entire world is getting. Unfortunately, while you were gone a virulent strain of the Bubonic Plague went through Santa's workshop killing all of the other elves as well as Santa. You want to make sure Christmas still happens, but the task to decide what type of present each person should get is too difficult to perform manually as there are thousands of people. Luckily however, you have a bit of python experience and know that you can automate the process.

You have a csv containing all of the peoples names in the first column and their respective NI (naughtiness index) on a scale from 0 to 1 in the second column (you can ignore the third column unless you are doing the challenge). The rules for what present a person should receive, where  𝑛  is the NI, are as follows:

- If  0<𝑛≤0.25 , they get a `"big present"`
- If  0.25<𝑛≤0.50 , they get a `"medium present"`
- If  0.50<𝑛≤0.75 , they get a `"small present"`
- If  0.75<𝑛≤1.00 , they get `"coal"`

**Challenge:** The csv has a third column containing ages between  5  and  65 . As adults should be held to a higher standard than children, you must factor in age when deciding what present a person should get. Let the "present-determining-function" be defined as
𝑝(𝑛,𝑎)=𝑛^((85−𝑎)/40) 

where  𝑛  is the NI and  𝑎  is age. The new rules factoring in age are as follows:

- If  0<𝑝(𝑛,𝑎)≤0.25 , they get a `"big present"`
- If  0.25<𝑝(𝑛,𝑎)≤0.50 , they get a `"medium present"`
- If  0.50<𝑝(𝑛,𝑎)≤0.75 , they get a `"small present"`
- If  0.75<𝑝(𝑛,𝑎)≤1.00 , they get `"coal"`

```python
# this codeblock imports the csv and converts it to a pandas series
import pandas as pd

url = 'https://raw.githubusercontent.com/7673502/Santa-Problem/main/santaproblem.csv'
naughty_list = pd.read_csv(url) # converts csv file from url into a pandas DataFrame

# we can look at the series by printing it (we can't see the whole thing because it's so big - 250021 rows!)
print(naughty_list)
```

You must add an additional column titled "present" assigning the type of present each person is to recieve. You must write at the bottom the number of presents recieve in each category.

**Challenge Hints:**

Can you create a python function for the "present-determining-function"?
Exponents in python are written using two asterisks. For example `2**3` is  2^3 .
