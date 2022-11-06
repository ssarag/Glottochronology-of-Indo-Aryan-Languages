# Glottochronology of Indo Aryan Languages. 

Data science has had a significant impact on linguistics. Having a thorough understanding of the true extent of variety among languages, within dialects, and among dialects is essential to all areas of the subject. With the invention of computers, the subfield of corpus linguistics—which is probably as old as the field itself—gave birth to many fundamental techniques used in data science. When the first huge search engines appeared in the late 1990s, linguists immediately began utilizing them to identify examples, investigate trends, and reveal subtle patterns in usage that emerge only at a very large scale. Even the largest corpora seemed little in relation to the open Web; this is arguably the first big data application in the linguistic sector. Data Science methods like Natural Language Processing and 
Machine learning have emerged as important counterparts to traditional and comparative method in linguistics. The goal of this research is to study the Glottochronology of Indo-Aryan (Indic) languages using modern Data Science techniques.

# Research Objectives
The main goal of this research is to Reconstruct phylogenetic tree for Indic languages. The research 
is divided into three parts.

1. In the first part, cognates of all the 18 languages are determined by using Automatic 
Cognate Detection Methods, Natural Language Processing and clustering algorithms.

2. The cognates identified from the first objective, will be then used to generate phylogenetic 
tree using Machine Learning techniques.

3. Comparison of the Phylogenetic tree obtained from Machine learning technique with the 
phylogenetic tree obtained by historical linguistics. Here we will consider the phylogenetic 
tree obtained by the linguistics as the gold standard. In Data Science “Gold Standard” is 
considered the ground truth and accepted as the most accurate result. Figure below, represents 
the Gold Standard tree obtained by historical linguistics for Indo-Aryan (Indic) Languages.


![image](https://user-images.githubusercontent.com/103538049/200193967-1298b39c-73d0-4769-b9f0-2071a85b9a4f.png)



# Understanding the terms 

# Cognates

In historical linguistics, cognates, also known as lexical cognates, are groups of words in distinct 
languages that have been inherited in direct lineage from an etymological predecessor in a shared 
parent language. In order to determine if two lexemes are cognate or not, one must frequently 
conduct a thorough analysis of historical sources and employ the comparative approach because 
linguistic change can have extremely radical consequences on both the sound and meaning of a word. 
The meanings of cognates do not necessarily have to be the same; they could differ as a result of 
divergent linguistic development. For example, the English word ‘starve’, German word ‘sterben’ (to 
die) and Dutch word ‘sterven’ (die) are derived from the same Proto-Germanic root ‘sterbana. 
Cognates are distinguished from other kinds of relationship. Cognates differ from other types of 
relationships between words like loanwords or doublets. Words that have been borrowed from one 
language to another are called loanwords. For example, the English word ‘beef’ is borrowed from Old 
French word ‘ boef ‘(meaning "ox"). Despite belonging to the same etymological stemma, linguists do 
not typically refer to these words as cognates. Doublets are paired terms from the same language that 
share a common etymology but may have different but related usage and meanings. Frequently, one 
is a loanword while the other is the native term, or they have co-occurred in a current standard 
language after first developing in separate dialects. The old French word ‘boef’, for example, is cognate 
with the English word ‘cow’, hence English cow and beef are doublets.

![image](https://user-images.githubusercontent.com/103538049/200194073-eba891f4-994f-4133-9b41-06886537bd44.png)


# Phylogenetic Trees

A phylogenetic tree, also called a phylogeny, is a diagram that shows the evolutionary branches 
from which various species, creatures, languages, or genes have descended from one another. 
Phylogenies are helpful for classifying organisms, and languages, organizing knowledge of biological 
diversity, and shedding light on evolutionary processes.

![image](https://user-images.githubusercontent.com/103538049/200194103-cb494335-a794-4dc3-83f9-141abbab04dc.png)

A tree's leaves, often known as its tips, might represent species, populations, people, languages, or 
even DNA. Taxa are used when the tips represent a formally identified group (singular: taxon). A 
group of organisms at any level of the hierarchy, such as a family, genus, or species, is referred to 
as a "taxon." The endpoints of extinct lineages, proto-language or fossils may alternatively be 
represented as the tips of a phylogenetic tree. A branch may contain one or more leaves and stands 
for the continuity of a lineage over time. Branches connect to other branches at nodes, which reflect 
the last shared ancestors of taxa at the tips of descendent lineages. An internal branch is one that 
connects two nodes, whereas an exterior branch connects a tip to a node.
A node and all of the lineages that are descended from it are grouped together as "clades" [8] on a 
tree. When a clade is said to be "monophyletic," it means that it contains every member of an 
ancestor lineage's line of offspring. In Figure below, we may state that the tree supports taxa C, D, and E 
forming a clade or, to put it another way, that C, D, and E are monophyletic.

![image](https://user-images.githubusercontent.com/103538049/200194160-64a28e88-5206-48ca-ad48-7bff93c77e8e.png)


# Workflow of the Research

![image](https://user-images.githubusercontent.com/103538049/200194204-e2a34b5a-9920-4115-8079-6ee2eba6e9c6.png)


# Dataset

In the research, words from Indic (Indo-Aryan) languages are used for classification and reconstruction 
of phylogenetic trees. To keep the data at manageable level, Swadesh list of Indic languages from 
Wiktionary is used. The Swadesh list is compiled by Morris Swadesh and consists of carefully chosen 
words for the purpose of linguistic study majorly in lexicostatistics and glottochronology. The list 
consists of 207 words which are basic root morphemes obtained by translating English words into 
most common words which are used in everyday language. These words in the Swadesh list are the 
words which are universal in every language and likely to be found in every culture like body parts, 
numerals, geographical terms, simple activities, etc. The Swadesh list words are already converted to 
IPA transliterations. The International Photonic Alphabet (IPA) gives visual representations of speech 
sounds by the means of symbols. The IPA was first devised by International Phonetic Association in 
the 19th century as the standardized representation of speech sounds in written format. The IPA 
was created to represent phonetics, phonemes, intonation, and the division of words and syllables as 
they appear in lexical sounds in oral language. The 18 languages in the below table are taken into 
account to study glottochronology. These languages represent the primary languages spoken by Indo-Aryans.

![image](https://user-images.githubusercontent.com/103538049/200194252-d4e3095d-8f2e-47dd-87ce-1a2205fe1378.png)



# Methodology and Implementation

# 1. Data Collection
To collect the data from the Wiktionary website, web scraping with beautiful soup library is used to 
iterate over the Swadesh list and saved the dataset in a tsv (Comma-separated format) file format. 
Figure below shows the data extracted by web scraping for the word ‘I’ in all the Indic languages.
The procedure to collect data with web scraping is completed in 4 steps.

1. In the Wiktionary website all the data is given in table format. Therefore, first, all the words 
from the table were extracted in a list. There were a few missing entries for the words in the 
‘Kashmiri’ language, these missing entries were replaced by ‘None’. All of these words in the 
table have a hyperlink that redirects the page to another page that contains the IPA of that 
particular word. To collect the IPA, all such hyperlinks were found and appended to another 
list. A tuple of list is created for every concept which consists of 3 entries for every concept-Language, word, and the link to IPA. 

2. In the second step we create a file to store IPA for each word we found in step 1. For this, 
every word and the link in the tuple of list is iterated and IPA entry for each word is extracted 
with web scraping’s beautiful soup method from the page and stored in text file. 

3. In step 3, we read this IPA file and join the IPA entries with the Cognancy, Concept, Word, and 
dialect extracted from the above steps together in a list. This list is created for every word. 
Here to select the words, which can be treated as concepts, words from the Sanskrit language
were chosen. 

4. In step 4 we create a tsv file that contains all the entries from step 3. Throughout the research, 
we will use this file for analysis. 

5. IPA entries for some of the words were not present in the Wiktionary website, therefore in 
the last step, the IPA entries with None value were replaced to their proginal IPA format 
manually. To calculate the IPA for such words, Wikipedia was utilized and a deep study of 
grammar was done

![image](https://user-images.githubusercontent.com/103538049/200194358-b481a1a1-65f9-4e7b-8ae9-386b2e98c90c.png)


The details of all the entries in the file are given below

Cognacy 
The column ‘COGNACY’ is used to store ID number for each concept. As there are 18 languages for 
evaluation, each concept is given an ID which will be common for all the words belonging to the 
same concept. Therefore, as seen in Figure 7, all the words belonging to the concept ‘ahám’ have 
cognacy 0. 

Concept
A concept is a linguistic and philosophical unit that categorizes and specifies each potential meaning 
of a word and its evolution. Here the words in Sanskrit language are chosen as concepts as it is the 
Proto-language of all the Indic languages. 

Counterpart
The column counterpart represents the words in Indo-Aryan languages for each concept. In this 
column, the words are also given with their IPA transliterations.

IPA
In this column, IPA of each word is extracted from the Wiktionary website. There were few missing 
entries for IPA, which were then filled manually after a thorough research and learning grammar 
rules of all the Indic languages.

Doculect
This column represents the Dialect (language) for every entry. There are total 18 languages taken 
from the Swadesh list. All these languages are primary languages of Indo-Aryan language family.

# 2. Automatic Cognate Detection

The cognates are found using two different techniques given below.
1. Automatic Detection of Cognates using Lingpy library
  • Sound Class Based Alignments
  • LexStat Method with three different clustering techniques- UPGMA, edit-distance 
  and Infomap

2. Automatic Detection of Cognates using Pointwise Mutual Information

The results obtained from all these methods are then evaluated to determine the most accurate 
method. 

# Results and Implementation of Automatic Cognate Detection Methods

# Sound Class Based Alignment

The sound class-based alignment algorithm begins with an input file containing concept, words, IPA, 
Language and the concept ID. This input file is created during web scraping which is in TSV file format. 
The Lingpy file was then given to the SCA algorithm, which first converted the words present in the 
file into their respective tokens of sound class. After the sound classes are created, pairwise alignment 
was carried out for each pair of words in the file using Needleman-Wunsch algorithm. During this 
process the SCA module creates a scoring system. The gap penalty for scoring system was set to -1. 
Therefore, for giving the scores to the word pairs Word1 and Word2, a score of -1 was given if w1 (ith
element of Word1) and w2 (jth element of Word2) are different and a score of 1 was given if w1 and 
w2 are similar and an alignment matrix was created. The output of the scoring system calculated was 
then imported into a CSV file. The figure below shows example of the scoring system created, for the 
concept ‘agni’ which means fire in English. 

![image](https://user-images.githubusercontent.com/103538049/200194503-ea0ad36e-1970-43f8-8ee2-283ac7e2aff9.png)


After creating a scoring system, a pairwise similarity for all the words in the list was calculated to form 
a distance matrix. The distance matrix determines the distance between two phonetic sequences. In 
the next step, Neighbor-joining algorithm is used for clustering the sound class strings calculated in 
the previous steps. To cluster the strings, Lingpy has built-in library in the module for Neighbor-joining 
algorithm. The threshold for clustering the cognates was kept at 0.55 which gave the best results. For 
the thresholds > 0.55 the results did not give better results than 0.55.

![image](https://user-images.githubusercontent.com/103538049/200194546-215485ea-9068-42c3-ae7a-7f582f589bb3.png)


# Automatic Cognate Detection with LexStat

The LexStat Method for detecting cognates is used with 2 different types of clustering Methods.
LexStat takes the same kind of input file as that of SCA, and therefore the same Lingpy file with 207 
words with their IPA, Language, Concept and ID is given to LexStat. Similar to SCA, LexStat also first 
the input sequence is tokenized and transformed into tuples of prosodic strings and sound classes
and created a scoring system. The output of the scoring system by LexStat is given below.

![image](https://user-images.githubusercontent.com/103538049/200194605-fec5180c-3458-437f-b15e-cd5d1d77dd40.png)


The scoring system created by LexStat is exactly similar to the scoring system created by the SCA 
method. All the information regarding the columns is given in the section of SCA implementation. The 
output of the scoring system was then used by the LexStat Algorithm to calculate a preliminary list of 
cognates. With the result of the preliminary cognates, LexStat calculates the pairwise alignments as 
well as performs shuffling the wordlist by iterating 1000 times. After this step, the LexStat method 
calculates the log-odds of the preliminary cognates and the expected cognates and computes the 
pairwise distance to compute cognates. After this step, to cluster the cognates into groups, two 
methods are used. First the cognates are clustered with edit-distance clustering algorithm with a 
threshold of 0.75, which gave the best cognate results. 

For clustering the cognates with Infomap Clustering, all the above steps are followed first, followed 
by Infomap algorithm. The threshold values tried here were 0.55, 0.6, 0.75 out of which threshold 0.55 
gave the best and efficient results. Both the clustering libraries are included in the Lingpy library, and 
hence in the cognate detection, this library is used to cluster. The results of cognate detection by both 
the methods are then imported to a TSV/CSV file. 

As compared to the SCA method, the LexStat Algorithm could determine the cognates more precisely, 
but the borrowing/loan detection results remained the same. The figures below show the cognate 
judgements for the word ‘agni’ for both LexStat-edit-distance and LexStat-Infomap.


# Automatic Cognate Detection with Pointwise Mutual Information
The below process was employed to detect cognates with PMI method

1. In the first step, the input file we generated with web scarping was first converted into ASJP 
format, and the data was cleaned as per ASJP standards. 

2. Apply normalized Levenshtein distance algorithm to obtain the list of possible word pairs from 
Swadesh list which as most likely cognates. In the research we considered all the word pairs 
with a length normalized Levenshtein distance (LDN) of less than 0.5 to be plausible cognates.

3. Used the Needleman-Wunsch technique to align the list of possible cognates.
4. We take advantage of this trait to create a partial graph and feed the subsequent network 
into the InfoMap method. 

5. Using the Needleman-Wunsch algorithm and result obtained from step 2, created a new set 
of alignments.

6. Steps 2 and 3 were repeated until the average similarity between repetitions remained 
constant.

7. After completing the above steps, a PMI based score was generated for each word pair. To 
get the PMI score in the range of [0, 1], the score was transformed into distance score using 
the formula of sigmoid transformation described above. 

8. The word distance matrix is then supplied to the label propagation algorithm with a threshold 
of 0.5


# Evaluating the Performace of Automatic Cogante Detection Methods

For evaluating the methods and performance of cognate detection, bcubes method is used. In this 
method, the performance is evaluated based on the Precision, Recall and F1 Scores of the cognate 
detection results. To compare the cognates, a gold standard cognate judgement was necessary. As it 
is difficult to create a gold stand cognate judgement list, In the research the cognate judgements 
carried out by the author. The research contains manually curated cognate IDs for Swadesh 
List of 100 words. This list of cognate ID’s is considered gold standard list. Now to evaluate the 
performance of our methods, with gold standard metrics, first another Swadesh list of 100 words was 
created which consisted of only those words which were present in the gold standard list. Below figure 
shows the gold standard cognate IDs for 100 words of Swadesh list, which were taken from the 
research of the author. 

With the help of Pandas, a new Swadesh file of 100 words was created which consisted of the columns, 
Cognacy, Concept, Word, IPA, Language, ID, gold standard cognate ID. The figure below shows an 
example of such file. This file was then given as input to all the automatic cognate detection methods 
described above and the performance for each method was evaluated using bcubes which calculates 
Precision, Recall and F1-score. Precision is a measure of how many of the positive predictions are 
correctly identified. Recall is a measure of how many of the positive cases are identifies correctly and 
F1-score combines both precision and recall and known as harmonic mean of the two

![image](https://user-images.githubusercontent.com/103538049/200194765-d1b21d8e-891b-4ccc-8dd1-6cf1b18be398.png)


![image](https://user-images.githubusercontent.com/103538049/200194785-c4d324bc-104f-4b5f-9e02-93339db2ca98.png)


From the above evaluation scores, it can be seen that The Pointwise Mutual Information approach 
outperforms all the other methods. The Lingpy based methods SCA, LexStat-Edit-Distance performs 
good at separating loan words and cognates but fails to detect a large number of cognates correctly. 
The Pointwise Mutual Information and LexStat-Infomap have a very close score with all the 
performance metrics and were able to detect most of the loan words correctly as well. One 
disadvantage of evaluating the performance on small dataset (100 words) is that, if the dataset is very 
small and the distance between languages is large it is quite difficult to prove the cognacy between 
words. While the LexStat method also performs very well, it lacks in determining borrowings as it 
creates a language specific scoring system. With language independent scoring system LexStat can 
handle borrowings more accurately. To manage the False cognate Identification, the threshold can be 
minimized for all the Automatic Cognate detection methods we utilized. Hence, the PMI approach 
with a threshold of 0.5 performed best, but after minimizing the threshold to 0.45, 0.4, the results remained same. This may mean that the dataset was overfitted and hence could not classify the cognates more accurately.

As the PMI and LexStat-Infomap methods performed best, further these methods were used to 
calculate the distance between two languages. This distance was calculated as a correlation matrix, 
which consisted of text file, with one language and its distances on each line, separated by spaces, 
and the number of languages in the first row.The below figure shows the distance of the languages 
with each other.


![image](https://user-images.githubusercontent.com/103538049/200194839-12d442f1-15b3-4c8c-83b6-1d60bcc7288d.png)


# Reconstruction of Pylogenetic Tree

To reconstruct the phylogenetic tree, Bayesian Inference using Markov Chain Monte Carlo method is 
used. The methods in Bayesian inference in historical linguistics are based on the below formula, 

![image](https://user-images.githubusercontent.com/103538049/200194867-3f6f28a6-59cc-47f9-ba58-7ab9d9188351.png)


In the first step for reconstructing Phylogenetic tree, the Data Matrix X is created. The matrix 
created is of N*K dimension, in which there are N (207) different words from 18 Indic languages and 
they can be put into K clusters in a language family. As we need a binary data matrix, we construct 
the data matrix with elements 𝑖𝑖𝑗. If the element is 1 it states language i is could be classified into 
cognate cluster j, and if the element is 0, it indicates that language i cannot be classified into cognate 
cluster j. This data matrix is crated using python library and converted into a nexus file. The example 
of such Data matrix is given below.

![image](https://user-images.githubusercontent.com/103538049/200194883-35f54e8b-b9fd-4956-90da-05f205c45056.png).


As the Automatic Cognate detection gave best results for LexStat Infomap and PMI, we will use 
these data of cognates to reconstruct the phylogenetic tree. The output of both the methods, in 
transformed into a matrix with the help of Python and stored in nexus file type. This file contains 
matrix of language and cognates as discussed in above section. For reconstructing phylogenetic tree, 
Markov Chain Monet Carlo Method is utilized. The procedure of MCMC is described as follows.

1. In the first Step a Random Tree A is selected 

2. Then we use Bayes rule to evaluate the Probability of A, P(A)

3. In this step, Tree A is modified in a small amount randomly and second tree B is created
4. Then again Bayes rule is used to calculate the probability of B, P(B)

5. If P(B) > P(A), which suggests that the new tree P(B) is more likely to represent data than 
tree A, then step 1 is repeated. Here instead of starting with a random tree, the algorithm 
uses tree B

If P(A) > P(B), then algorithm chooses any two options between starting with tree B or tree A 
and select to start with tree A randomly which has the probability of 1-P(B). 

The likelihood that the created trees accurately represent the data increases when the process is 
done numerous times. In order to prevent getting stuck in local maxima and missing a region of the 
search space with even higher probability, the final step gives these algorithms a way to transition 
from a higher-probability tree to a lower-probability tree.

To implement reconstruction of Phylogenetic tree, MRBAYES software package is utilized. The MRBAYES package accepts the nexus we created as an 
input the run the MCMC analysis. To start the analysis, we need to first create a data encoding file in 
nexus format as discussed above. 

The issue with MYBAYES package is that additional than leaves, no other tree node can be directly 
specified. As a result, it is difficult to directly declare retentions as the root node of the tree.
Therefore, to overcome this, we will set ‘Sanskrit’ language as the outgroup as it is related to every 
other language in Indo-Aryan language family. The next step of the algorithm is to reduce the 
distance between the outgroup language and the root node language.

The Input file for MRBAYES has 18 languages with the data encoding. The MRBAYES then takes the 
file as input, add few users selected configuration options, and begins the process of Bayesian 
Markov Chain Monte Carlo. In this research, the configuration options used as as follows

1. Generations = one million
2. Chains = 6 (Markov chains for initial random trees)

3. Sampling frequency and burn-in were set to default
4. Outgroup was set as Sanskrit

After putting these settings, the package starts running the analysis. The below code is used to run 
the analysis.

![image](https://user-images.githubusercontent.com/103538049/200194968-eec9c283-a36c-4d7d-b644-7a121e5ef7c8.png)


For running the analysis for one million generations it takes 10-12 mins, after which the trees are 
generated and summarized. The trees are also downloaded automatically in a tree file after the 
analysis is completed. To summarize the tree and the standard deviations results in the software, 
the below code is utilized. 

MrBayes > sumt burnin 250.


# Results of MCMC Analysis with input LexStat-Infomap


![image](https://user-images.githubusercontent.com/103538049/200195004-ff14be75-063f-4fa1-a15f-2b02d4028f82.png)


# Results of MCMC Analysis with input PMI approach

  ![image](https://user-images.githubusercontent.com/103538049/200195024-60147ed3-e56a-4c78-baa2-97ffef3a67f7.png)
  
  
The tree obtained by MCMC analysis took 10 minutes to generate one million generations. All the 
settings like burnin, outgroup, etc are kept exactly similar to the previous method .The tracer plots 
and histograms generated for this run are given in appendix. The phylogenetic tree obtained by the input of PMI method and MCMC analysis looks more detained 
and accurate than the tree obtained by LexStat-Infomap and MCMC


# More research and dicussions is available in the report attcahed above.

The files above contain the following

Code - Complete pythoon code for the Analysis
Input data sets - Contains all the input files required by the code
Evaluation Output - Contains output files generated by automatic cognate detection methods and their evaluation
Nexus Files and MRBAYES Files - Contains input for phylogenetic tree in nexus format and the output abtained from MRBAYES software
Output_full_list - Contains output of all the methods of Automatic cognate detection 
Report - Research report
