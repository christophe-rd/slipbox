[2024-07-08]
##### Different types of dormancy
Physical dormancy.
Physiological (chemical )
	Deep
	Non-deep
Morphological 
Combination
Non-dormant (seeds that can germinate right away)

##### About question 2:
Should be believe the dormancy classes? Are the seeds getting cues such as chilling, or a shorter forcing time. 

In OSPREE, they got 3 concept papers (on photoperiod, experimental designs 
and 3 data papers. For egret, we aim writing mostly \

Concept papers do have data. They are papers that address perspectives or problems on the data itself.


rows data, species, experiment and paper
check the baskin book and check the order
Divide 

What is common in egret and chat about it
What is common in USDA

Check in at 2, at 3pm we're done.


**Notes on Baskin:**
Some species mentionned p.33 are subjected to cool temperature, but the only effect is to delay germination. 
Whereas somme species are disperced in spring, thus seeds are exposed to warm (summer) followed by cold (winter) stratifying temperatures before they can germinate
	To test this, seeds are given a warm strat before a cool start and are compared to  a cold (only) stratification treatment

**Move along experiment:**
1. Select an appropriate temperature regime (e.g. Spring, Summer, Autumn, Winter), e.g.:
	1. **Early** spring and **early** autumn are the same (15/6 Celsius;12/12h)
	2. **Late** spring and **late** autumn are the same (20/10 Celsius ;12/12h)
	3. Summer regime (25/15 Celsius)
	4. Winter regime (5/1 Celsius)
2. Seeds are kept on a wet substrate
3. Treatments:
	1. Control: kept at each temperature regime until the experiment is finished (4 weeks/temperature regime)
	2. Start at summer temperature (12 weeks) 
		a. moved along to the other temperature regimes
	3. Start at winter temperature (12 weeks)
		a. moved along to the other temperature regimes

#### On coordinate cleaning: 
Remove the mapping to another script 
Change gsub to which functions

grep warm, cool, dark, light, etc.

##### to check
when temperature is in a column treatment, check if there are unique entries in germ duration, germ temp, germ length. 


##### Treatment
1. Create a warm strat column
2. We want to see how many studies have warm incubation, cool incubation
We want to know which experiments have only variation in germination temperature

for every column, dataset by experiment, create the outer loop, subset


subset for each datasetID and experiment number and see if they manipulated any of the temperature data
Question: new script for warmstrat? new script for 


### Questions:
1. What priority is changing gsub to which?
2. I haven't yet added my cleaning treatment file to the repo
	1. change the if else statement at the beginning of my files
3. rename it studydesign
#### Separate issue to work on
add a photoperiod column

[2024-07-10]
#### Notes 
**Questions**: 
1. What are the germination responses to different cues

**Response variables:**
mean germination time
	*** Dan: we can get it by taking the max germination and divide it by the time it took to get there 
max germination

How can we avoid confounded for studies that let the seeds to germinate for 2 weeks after trial. 

If we are getting max germination %, is that getting in beta correlation land?
Answer: we can convert max germination to how many seeds germinated. 

ABA is the inhibitor, GA3 up regulates


To do: 
- scarification: how many, what types
- warm strats: what's out there. Is it short/long. etc. 
scariff
- finish cleaning clean coordinates
- make sure the new columns are not messing with my data
- find out a way to show the scarification 
- Add NAs in my graph

we'll meet at 9:30 tomorrow to check in on what needs to be done for the rest of the day

im in zsh, I should change 

find the studies that have multiple provenances, I can use the output of the study design. 
Use Deirdre's code, her massive ID

Loop over all response variables on the x axis and y axis (%germination).
subset down all the studies that have multiple studies. 


For further meeting notes starting on 25 July 2024:
[[Egret meeting notes]]

## 10 February 2025
Seed dormancy. Different class, so we want to know if they germinate between the different dormancy groups. Kinda a secondary question. 

#### Goals:
1. Update the document with the methods. 

Tasks:
- Read the methods of romero05 in detail to figure out whats going on. 
- Numeric 
- Skim source.population

#### Questions
- 2 months warm (20C), then 2 months cold (4C). Is that all cold strat? Yes
- Make sure that chillTempCycle is a number of days.
- Change in **cleanRespVar** for schutz02 for number days to 1 perc germ for table 3. ok
- pritchard93: clean miscellaneous change year for figure 2. It's 1990 instead of 1989. Figure 4 is 1990 instead of 1988. And Table 4 to NA.  OK
- pritchard93: what's up with germination perc probability? Ok
- zhou03: there is a 1344 in chill temp cycle which brings up a question of whether we should keep that column. What does it tell us? Chat on issue if we should get rid of it. OK
- I need to flag the high values for chillTemp e.g. 44 or 20 and 40. 
-
Table 1 not relevant. Figure 2 relevant.
Figure 3 relevant. I think that is the one that has been scraped but has been labeled figure 1.
- What to do with ave
- **cousins10**: should we keep ave if they pooled accross the previous treatments? they chill temp X duration treatments and then pool across treatments to check each factor for their perc germination

##### Questions for Ken:
- ChilltempCycle: done it's hours. Go back to october 9
- Big chunk of code at the end of the script. Ken will fix it.
- Why is it sometimes it's then and sometimes it's and? Done.
- Why sometimes ave instead of taking the average temperature with an uncertainty like most of them? For cousins, they chill temp X duration treatments and then pool across treatments to check each factor for their perc germination. wytsalucy21: one is temperature and the other is hormone and they pooled because interaction between temperature and treatment wasn't significant. So we used ave because we don't know the exact temp value for the chillTemp.
- What are the questions at the start of the script. Done
- 

## 11 February 2025
## Goals for today
- Write up methods in the latex file done
## 12 February 2025
- Finish chillTempDuration
- Put columns of chillTemp duration. In the metadata. 
- Go find Tolu's code and commits. Don't work on it for more than 1/2 hour and create a new issue about it and reference it in clean coordinates. Didn't find anything.
- Update the issue for clean coordinates
- CleanChillTemp duration.

While cleaning coordinates --> #21, if a paper didn't explicitly mention the source.population coordinates, but mentioned the name of that location (E.g. Artvin Region, Turkey) I extracted lat and long and explicitly mentioned it in the code 

## 13 February2025
-  **yang08**: resolve storage temp figure 2, 3, 4. It was entered in chill temp but the paper explicitly mentions that it's storage.
What to do about figure 2 where reponseVar is moisture content?
-  **ma18**: will look at it on the projector
- **zhou08**: missing one row of data for table 2 for MGT the one that's missing is 8.4:  OK
d$responseValue[which(d$datasetID == "zhou08" & d$treatment == "stratification")] 
[1] "50"   "15.4" "50"   "14.1" "58.3"
d$figure[which(d$datasetID == "zhou08" & d$treatment == "stratification")] 
[1] "table 2" "table 2" "table 2" "table 2" "table 2"
copy the row from the original source and add it in my csv file. 
- **mattana16**: figure misslabeled. It's input as figure 1, but figure 3 was scraped because it had a cold strat treatment. Figure 1 seems to be relevant. Plus, it's a Chill temp at 5C then an incubation at 10. Don't know how to input that data.
- **yang18_2**: may need to be rescraped. 
1. Figure 2: think germ duration is wrong. It's 24 weeks, so it should be 140 days, not 720. Plus, I don't undertstand if it averages the chill duration or if there was none. See table 1.
2. Figure 3: I think they assume it was a germ temp of 20/30 and duration of 20 weeks from the methods, but I am not sure. In any case, it's 720 days which is probably wrong.
3. Figure 6. same for figure 3.

Figure 6 --> 5.

forcing, germination temperature and incubation temperature are the synonyms. 
Stratificaiton and chilling are synonyms.

## 14 February 2025
- Ask Ken to double check song20 and mamut20

nin17: they stratified for 15,30,60 days and presented the mean values without providing responseVal for each single durations. What to do?
	cousins 10

phyllagenyfig.R
analyses

## 15 February 2025
Finish cleaning species for phylogeny. Don't do USDA yet.