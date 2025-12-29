# Modern Assyrian Lexicon

## What is a Lexicon?
The collection of words, phrases, or symbols in a specific language. Includes the various linguistic attributes with each word, part of speech tags, semantic information, pronunciation among others. It is a comprehensive repository of linguistic knowledge to help NLP systems process and understand natural language text.

## Components of a Lexicon
1. **Words and their meanings**
    1. What is the corresponding meaning(s)?
2. **Part-of-speech (POS) tags**
    1. **Categories**
	    1. Noun
    	    1. Proper
    	    2. Demonym
	    2. Verb
    	    1. Denominative
    	3. Pronoun
	        1. Demonstrative
    	    2. Interrogative
    	    3. Personal
    	    4. Relative
    	    5. Unspecified
	    4. Adjective
	    5. Adverb
	    6. Preposition
	    7. Numeral
	        1. Ordinal
	        2. Cardinal
	        3. Literal
	        4. Unspecified
	    8. Particle
	    6. Conjunction
	    7. Interjection
	    8. Idiom
	2. **Sub-categories**
	    1. Gender
	        * Masculine
	        * Feminine
	        * Common
	        * Unspecified
	    2. Number
	        * Single
	        * Plural
	        * Dual
	        * Dual and plural
	        * Singular and plural
	        * Unspecified
	    4. Person
	        * First
	        * Second
	        * Third
	        * Unspecified
	    3. State
	        * Absolute
	        * Emphatic
	        * Construct
	        * Determined
	        * Absolute and construct
	        * Unspecified
	    4. Tense
	        * Active participle
	        * Imperative
	        * Imperfect
	        * Infinitive
	        * Participle
	        * Passive participle
	        * Perfect
	        * Unspecified
3. **Pronunciation**
    1. What is the pronunciation of word(s)?
4. **Semantic information**
    1. Senses
    2. Synonyms
    3. Hypernyms

## Lexical Semantics
1. **Lexical normalization**
    * Word standardization through a process of transforming words or phrases into their **canonical or base form**
2. **Lexical disambiguation**
    * Determining the correct meaning or sense of the word in a given context
3. **Bilingual lexicons**
    * Resources that provided translation equivalents between words or phrases in different languages

## Frameworks
1. **Lexicon model**
    * Propose using the [Lemon Model](https://lemon-model.net/)
2. **Automatic mapping**
	* Create a set of heuristic rules to discover mappings and semi-automate the process
	    * **Rule 1**: Lemma should be fully diacritized
	    * **Rule 2**: Given two words, _w1_ and _w2_, we should consider them diacritic compatible if:
	        1. Both words have the same letters
	        2. No contradictions between the diacritics of the same, pair-wise, letters of these words
3. **Grammar annotation** 
    * Propose using the [Universal Dependencies (UD) Framework](https://universaldependencies.org/) as it is universally used and applicable across different human languages
4. **File Format**
    * Propose using the [CoNLL-U Format](https://universaldependencies.org/format.html). 
    * Annotations are encoded in plain text files (**UTF-8**, **normalized to NFC**, **using only the LF character as line break, including an LF character at the end of file**) with three types of lines:
        - Word lines containing the annotation of a word/token/node in 10 fields separated by single tab characters; see below
        - Blank lines marking sentence boundaries. The last line of each sentence is a blank line.
        - Sentence-level comments starting with hash (#). Comment lines occur at the beginning of sentences, before word lines.


	**ID**: Word index, integer starting at 1 for each new sentence; may be a range for multiword tokens; may be a decimal number for empty nodes (decimal numbers can be lower than 1 but must be greater than 0).

	**FORM**: Word form or punctuation symbol.

    **LEMMA**: Lemma or stem of word form.

    **UPOS**: Universal part-of-speech tag.

    **XPOS**: Optional language-specific (or treebank-specific) part-of-speech / morphological tag; underscore if not available.

    **FEATS**: List of morphological features from the universal feature inventory or from a defined language-specific extension; underscore if not available.

    **HEAD**: Head of the current word, which is either a value of ID or zero (0).

    **DEPREL**: Universal dependency relation to the HEAD (root iff HEAD = 0) or a defined language-specific subtype of one.

    **DEPS**: Enhanced dependency graph in the form of a list of head-deprel pairs.

    **MISC**: Any other annotation.


## POS Tags = Universal Dependencies
See [POS definitions](https://universaldependencies.org/u/pos/).

[Open classes](https://languagetools.info/grammarpedia/partsofspeech.htm#openclasses) allow new members through borrowing (for example, the _noun_ **cafe**) and derivation (for example, the _adjective_ **bounteous** from the _noun_ **bounty**).

[Closed classes](https://languagetools.info/grammarpedia/partsofspeech.htm#closedclasses) do not allow new members and usually involve grammatical rather than lexical words (such as **to**, **before**, **although**)

| Tag | Definition | Class |
| --- | --- | --- |
| ADJ 	| adjective						| open		|
| ADP 	| adposition					| closed	|
| ADV 	| adverb						| open		|
| AUX 	| auxiliary						| closed	|
| CCONJ | coordinating conjunction		| closed	|
| DET	| determiner					| closed	|
| INTJ 	| interjection					| open		|
| NOUN 	| noun							| open		|
| NUM	| numeral						| closed	|
| PART 	| particle						| closed	|
| PRON 	| pronoun						| closed	|
| PROPN | proper noun					| open		|
| PUNCT | punctuation					| other		|
| SCONJ | subordinating conjunction		| closed	|
| SYM 	| symbol						| other		|
| VERB 	| verb							| open		|
| X 	| other							| other		|

## Tool development
1. Transliteration
2. Morphological segmentation
3. POS tagging
4. Stemming / lemmatization
