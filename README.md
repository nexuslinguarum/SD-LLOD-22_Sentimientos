# SD-LLOD-22 Sentimientos

This repository contains the scripts and resources developped in the Sentimientos team at SDLLOD22.

The Sentimientos miniproject aims to enrich, convert and release lexicographical data with sentiment information using the Linked Data information. 

The project is composed of three major components:

1. Starting from a list of lemmata, it collects lexicographical data from [Dbnary](http://kaiko.getalp.org/about-dbnary/) using SPARQL queries.
2. The lexicographical data containing lemma, part-of-speech and senses is then enriched with information from polarity datasets. In this miniproject, we use the following two datasets respectively for German and Serbian: [German Polarity Lexicon ("PolArt"-Lexicon)](https://sites.google.com/site/iggsahome/downloads) and a Serbian polarity dataset. The following is an example:

```
	<http://kaiko.getalp.org/dbnary/deu/miserabel__Adjektiv__1> a ontolex:lexicalEntry;
	    lexinfo:partOfSpeech <http://www.lexinfo.net/ontology/2.0/lexinfo#adjective>;
	    rdfs:label 'miserabel'@de;
	    ontolex:lexicalSense <http://kaiko.getalp.org/dbnary/deu/__ws_1_miserabel__Adjektiv__1>, <http://kaiko.getalp.org/dbnary/fra/__ws_3__deu__miserabel__adj__1>, <http://kaiko.getalp.org/dbnary/fra/__ws_1__deu__miserabel__adj__1>, <http://kaiko.getalp.org/dbnary/fra/__ws_2__deu__miserabel__adj__1>.

	<http://kaiko.getalp.org/dbnary/deu/miserabel__Adjektiv__1/opinion> marl:describesObject <http://kaiko.getalp.org/dbnary/deu/miserabel__Adjektiv__1>;
	    marl:hasPolarity marl:negative.
```

3. The enriched file (in `.ttl`) is then imported on a SPARQL endpoint where queries are run from a website. The website is purely in Javascript and can be run locally [index.html].


