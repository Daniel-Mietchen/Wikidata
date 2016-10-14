# About
This file collects examples for using [Quick statements](http://tools.wmflabs.org/wikidata-todo/quick_statements.php) to create or edit Wikidata. For instructions, see the "How to" section there.

# Creating an item
* Make sure it does not already exist
* Adapt the following code snippets accordingly (note the separation by tabs):
   * For an item about a scientific article ([Q13442814](https://www.wikidata.org/wiki/Q13442814)), with [P31](https://www.wikidata.org/wiki/Property:P31), [P1433](https://www.wikidata.org/wiki/Property:P1433), [P1476](https://www.wikidata.org/wiki/Property:P1476), [Q219980](https://www.wikidata.org/wiki/Q219980). Note that [Source, M.D.](https://tools.wmflabs.org/sourcemd/?) automates the process for scientific articles that have at least one of (DOI/PMID/PMCID).
```
CREATE
LAST	Len	"One hundred and one new species of Trigonopterus weevils from New Guinea"
LAST	Den	"scholarly article"
LAST	P31	Q13442814
LAST	P1433	Q219980
LAST	P1476	en:"One hundred and one new species of Trigonopterus weevils from New Guinea"
```
   * For an item about an author of a journal article (with [P31](https://www.wikidata.org/wiki/Property:P31), [P106](https://www.wikidata.org/wiki/Property:P106), [Q5](https://www.wikidata.org/wiki/Q5), [Q1650915](https://www.wikidata.org/wiki/Q1650915), [Q482980](https://www.wikidata.org/wiki/Q482980)). Note that not every author of a scientific article can or should be represented as an item (which would translate into a [P50](https://www.wikidata.org/wiki/Property:P50) statement on the item of the article) &mdash; for most authors, a representation of their name string would be the way to go (i.e. by adding a [P2093](https://www.wikidata.org/wiki/Property:P2093) statement to the item of the article; Source, M.D. does this automatically).
```
CREATE
LAST	Len	"Cahyo Rahmadi"
LAST	Den	"researcher"
LAST	P31	Q5
LAST	P106	Q1650915
LAST	P106	Q482980
```
   * For items about a taxon
     * Example: [Q19897576](https://www.wikidata.org/wiki/Q19897576), with [P31](https://www.wikidata.org/wiki/Property:P31), [P105](https://www.wikidata.org/wiki/Property:P105), [P225](https://www.wikidata.org/wiki/Property:P225), [P171](https://www.wikidata.org/wiki/Property:P171), [P1746](https://www.wikidata.org/wiki/Property:P1746), [Q16521](https://www.wikidata.org/wiki/Q16521), [Q35409](https://www.wikidata.org/wiki/Q35409), [Q2963928](https://www.wikidata.org/wiki/Q2963928)
```
CREATE
LAST	Len	"Chiropsellidae"
LAST	Den	"family of jellyfish"
LAST	P31	Q16521
LAST	P105	Q35409
LAST	P225	"Chiropsellidae"
LAST	P171	Q2963928
LAST	P1746	"7690E036-F8BD-4B62-A7BB-EF9DD1D6DE87"
```

   * Example: [19897577](https://www.wikidata.org/wiki/19897577)
```
CREATE
LAST	Len	"Meteorona"
LAST	Den	"genus of jellyfish"
LAST	P31	Q16521
LAST	P105	Q34740
LAST	P225	"Meteorona"
LAST	P171	Q19897576
LAST	P1746	"E3AA7CD7-8DE7-4BEE-9151-2D6EAAD54793"
```

   * Example: [19945831](https://www.wikidata.org/wiki/19945831)
```
CREATE
LAST	Len	"Xenoderus basquini"
LAST	Den	"species of beetle"
LAST	P31	Q16521
LAST	P105	Q7432
LAST	P225	"Xenoderus basquini"
LAST	P171	Q12010852
```

* Paste it into Quick statements
* Do a test run with one item
* Check results
* If OK, then run the entire batch
* Checking in from time to time may be useful

# Adding statements to items
* There is a Wikidata Sandbox item ([Q4115189](https://www.wikidata.org/wiki/Q4115189)) for testing
* Some examples that I actually ran through Quick statements
   * Adding authors to paper item ([Q19982505](https://www.wikidata.org/wiki/Q19982505))
```
Q19982505	P50	Q19966975
Q19982505	P50	Q19966978
Q19982505	P50	Q19966927
Q19982505	P50	Q19982682
Q19982505	P50	Q19982684
```
   * Adding further statements to paper item
```
Q19982505	P1433	Q219980
Q19982505	P373	"Media from Riedel et al. 2014 - 10.3897/zookeys.467.8206"
Q19982505	P478	"467"
Q19982505	P304	"1-162"
Q19982505	P577	+00000002014-12-22T00:00:00Z/11
Q19982505	P364	Q1860
Q19982505	P356	"10.3897/zookeys.467.8206"
Q19982505	P698	"25610340"
Q19982505	P932	"4296478"
Q19982505	P921	Q7019837
```
   * Adding ZooBank nomenclatural act to taxon item
```
Q18746310	P1746	"0199A885-5EB4-417E-AFFA-2366842AB040"	S248	Q19982505
```
   * Adding taxon rank to taxon item, with reference
```
Q18669852	P105	Q7432	S248	Q19982505
```
   * Adding parent taxon to taxon item, with reference
```
Q18669851	P171	Q7019837	S248	Q19982505
```
   * Adding "instance of" "taxon" to taxon item, with reference
```
Q19612966	P31	Q16521	S248	Q19982505
```
   * Adding taxon name, author and date to taxon item, with reference
```
Q19659024	P225	"Trigonopterus tujuh"	P405	Q19966975	P574	+00000002014-12-22T00:00:00Z/11	S248	Q19982505
```
   * Adding image to taxon item, with reference
```
Q19636648	P18	"Trigonopterus fulgidus holotype - ZooKeys-467-035.tif"	S248	Q19982505
```
   * Adding Commons category to taxon item
```
Q19659061	P373	"Trigonopterus wallacei"
```
