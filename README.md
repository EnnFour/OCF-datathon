### OCF Datathon

The Open Computational Facility (OCF) at UC Berkeley hosted a datathon on November 11, 2017 
which was open to all OCF staffers. In this datathon, several sets of data were released to us:
1) Lab usage data exclusively from staff members
2) Anonymized lab usage data from all users
3) Anonymized printer usage data from all users
4) A set of emails directed to help@ocf.berkeley.edu

After learning how to acquire these datasets, we were instructed to come up with a project 
and develop something interesting and cool.


### My Project


After the datasets were revealed, I chose to investigate the question "How long do users spend 
in the lab when they are printing something?" To help me answer this question, I used the anonymized
lab usage data in addition to the anonymized printing data. The first thing I did was to trim the data 
down to size because the two sets had different start dates. I then attempted to merge the two datasets 
based on items that matched between the two (the user, the time of a print job, and the session times).
After cleaning up the post-merge data I computed a brief summary of the data and plotted it in a histogram

### Overcoming Challenges

The first challenge I needed to overcome related to the times in the different datasets. Printer data stored 
times in the US/Pacific timezone while the session data was stored in UTC. It took a couple hours for me to 
resolve these time zone issues since my first attempts were'nt playing nicely with the pandas dataframe.
I worked through all of these issues and learned plenty about how the datetime object works in python 
(especially when it comes to timezone manipulation).

Another challenge I encountered was the issue of merging the tables. Each table had between 150,000 and 200,000 rows
which meant I needed to merge efficiently. My first instinct was to write an algorithm that efficiently merged
the two tables based on sorting and matching, however this algorithm didn't provide enough of an efficiency reduction.
It was later suggested to me that I merge these tables in SQL -- since pandas provides a framework for doing so
I chose to go down this path. After spending some time figuring out how to write SQL queries to perform
my operations, I was able to merge and group large data sets incredibly efficiently.

### Conclusion

After perservering through several difficulties, I was able to answer my original question. The data shows us 
that half of the users printing during their OCF session are in and out in just over 5 minutes. By plotting a
line on a histogram, we are also able to see that 70% of users printing leave the lab within 10 minutes of 
beginning their session.

This project taught me a lot about data analysis in the real world and the importance of playing around with data. 
I needed to ask myself which columns I wanted to keep, which columns correlated well with others, and what I
was trying to investigate with the data. During the project I was constantly printing out brief summaries of tables
to ensure I had the data I needed to answer questions in addition to helping me understand the limits of my data.
All in all, the OCF Datathon was a wonderful experience that helped me grow as a data scientist while also providing
a framework in which I could complete a difficult but rewarding project.
