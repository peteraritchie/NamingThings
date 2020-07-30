**10-17-19 UPDATE: Techcon '19 version of the slides are [now available](https://github.com/peteraritchie/NamingThings/blob/master/Slides/Naming%20Things.pptx)**

# Naming Things
Content ([TL;DR][Detailed Guidance]) on tips, tricks, advice, practices for naming things in software/technology

## Drivers
Naming guidance like .NET Framework Guidelines are helpful, but they only help in minor situations and don't really do a lot to help solve the naming things problem in software.

## Vision
Detail research results around where some of the pain points in naming are, analyze potential solutions, and provide guidance for making naming things easier.

## Guiding Principles
- There are always exceptions, we can only mitigate their effect
- **Purposefulness** This means doing this "on purpose", or by design.
- **Consistency** Enough said
- **[Least Astonishment](https://en.wikipedia.org/wiki/Principle_of_least_astonishment)** Building on consistency, where consistency of intuitiveness is important.

## Scope
These guidelines focus on wording over capitalization.  "[Casing](https://en.wikipedia.org/wiki/Letter_case#Special-case-styles)" is important, but that is a separate, independent, style.

## Detailed Guidance
[Detailed Guidance]: #detailed-guidance
### Definitions
[Definitions]: #definitions
<dl>
  <dt><a name="countable-noun">countable noun</a></dt><dd>

/ˈkoun(t)əb(ə)l/  
_adjective_  
&nbsp;&nbsp;&nbsp;&nbsp;a noun that can form a plural or be used with the indefinite article.

Antonyms: _[uncountable noun](#uncountable-noun)_
  </dd>
  <dt><a name="mass-noun">mass noun</a></dt><dd>

/ˈmas ˌnoun/  
_noun_  
&nbsp;&nbsp;&nbsp;&nbsp;a noun that is usually uncountable but can be made plural or used with a or an when you are talking about different types of something.  
&nbsp;&nbsp;&nbsp;&nbsp;For example, bread is used as a mass noun in _the shop sells several different breads_.  
  </dd>
  <dt><a name="uncountable-noun">uncountable noun</a></dt><dd>

/ˌənˈkoun(t)əb(ə)l noun/  
_adjective_  
&nbsp;&nbsp;&nbsp;&nbsp;a noun that cannot form a plural or be used with the indefinite article.
</dd>
  <dt><a name="collective-noun">collective noun</a></dt><dd>

/kəˈlektiv noun/  
_noun_  
&nbsp;&nbsp;&nbsp;&nbsp;a singular noun, such as _committee_ or _team_, that refers to a group of people, animals or things. [In American English it must be used with a singular verb]
</dd>
  <dt><a name="deverbal">deverbal</a></dt><dd><span>  
/ˌdēˈvərb(ə)l/

_adjective_  
&nbsp;&nbsp;&nbsp;&nbsp;(of a noun or adjective) derived from a verb but behaves strictly as a noun or adjective and not a verb.

_noun_  
&nbsp;&nbsp;&nbsp;a deverbal noun or adjective.</span>

See also: _[verbal noun](#verbal-noun)_
</dd>
  <dt><a name="action-noun">action noun</a></dt><dd>

/ˈakSH(ə)n noun/  
_noun_  
&nbsp;&nbsp;&nbsp;&nbsp;A noun expressing action.

synonyms:  
&nbsp;&nbsp;&nbsp;&nbsp;_noun of action_
</dd>
  <dt><a name="verbal-noun">verbal noun</a></dt><dd>

/ˈvərbəl noun/  
_noun_  
&nbsp;&nbsp;&nbsp;&nbsp;A noun formed as an inflection of a verb and partly sharing its constructions[/forms. i.e. sometimes behave as a verb].

> "Verbal nouns contrast with deverbal nouns, that is, other kinds of nouns derived from verbs, such as attempt, destruction, and including nouns ending in -ing that do not have verbal force: building in _The building was empty_. They also contrast with the gerund, which also ends in -ing, but is syntactically a verb."  

See also: _[deverbal](#deverbal)_
</dd>  <dt><a name="zero-derivation-words">zero-derivation words</a></dt><dd>

_noun_  
&nbsp;&nbsp;&nbsp;&nbsp;A process of word-formation in which there is no change to the form that undergoes it.  
&nbsp;&nbsp;&nbsp;&nbsp;e.g. that by which the verb fish, seen as one lexical unit, is derived from the noun fish, seen as another lexical unit.

synonyms: _zero-affixation words_.
</dd>
  <dt><a name="metonym">metonym</a></dt><dd>

/ˈmedəˌnim/
_noun_
&nbsp;&nbsp;&nbsp;&nbsp;a word, name, or expression used as a substitute for something else with which it is closely associated.  
&nbsp;&nbsp;&nbsp;&nbsp;For example, _Washington_ is a metonym for _the federal government of the US_.

</dd>
  <dt><a name="homograph">homograph</a></dt><dd>

/ˈhäməˌnim,ˈhōməˌnim/
_noun_
&nbsp;&nbsp;&nbsp;&nbsp;each of two or more words spelled the same (homonym) but not necessarily  
&nbsp;&nbsp;&nbsp;&nbsp;pronounced the same and having different meanings and origins.  
&nbsp;&nbsp;&nbsp;&nbsp;Homonym is a type of homograph.

</dd>
</dl>

### Principles
[Compartmentalization]: #compartmentalization
**Compartmentalization** Compartmentalize things that can be reasoned about independently of other things; these are the things that require unique names.  One thing that makes naming hard is naming things that have no unique attributes or behavior.

[Namespaces]: #namespace
### Namespaces
Namespaces suit a couple of needs, both relating to the grouping of types.  Grouping types within a namespace should be based on functionality of implemented by those types.  

**Use a pluralized noun for namespaces that group types related by interface A namespace that contains types related by interface should be named with a pluralized noun**. One is a grouping of types that implement a specific interface.  A `Collections` suffix signifies the namespace contains types that implement interfaces that allow types to act as collections.

**Use a [mass](#mass-noun) [deverbal](#deverbal) noun for namespaces that group types related by functionality (but different)**.  The other grouping can cause some consternation because the grouping can easily feel subjective.  You can also group types by functional usage.  This type of grouping can be thought of as capability grouping.  In which case the namespace name can be a [noun of action](#action-noun) or a noun based on a verb.  The suffixes "-ion" and "-ing" come into play here.  e.g. `Processing` or `Administration`.

**Use [countable](#countable-noun) nouns or pluralized adjectives for namespaces that classify other namespaces** <code>System.<i>Diagnostics</i>.Tracing</code>

**Use adjectives or [mass](#mass-noun) nouns to sub-group types related by interface** <code>System.Collections.<i>Generic</i></code>, <code>System.ComponentModel.<i>Composition</i></code>.

**Being successful**: Perform grouping on purpose, only group types with similar attributes or similar behavior (randomly grouping types within a namespace is very subjective, and thus a _good_ name for it is subjective).  Prefer nouns that describe an act or responsibility. Avoid ending in "-ion", avoid words ending in "-tion" or "-sion.  A "[mass moun](#mass-noun)" is also called a [noncountable](#uncountable-noun) noun.  Avoid words that function as [mass](#mass-noun) [deverbal](#deverbal) nouns but often also function as adjectives (need example).

#### Summary
Namespace names should signify how the types in the namespaces are grouped.

**See also** [General](#general)

[Assemblies]: #assemblies
### Assemblies; Class Libraries and Programs
Assemblies are the deployable binary groupings of compiled code.  As such, the context of these binaries is generally the file system or URIs.  Assemblies often travel in packages and thus have unique constraints that affect naming.  Assembly names can be scoped by directory, but that depends on deployment and choices outside of your control (names of 3<sup>rd</sup> party assemblies and packages).

[Classes]: #classes
### Classes
[Prefer Common Nouns]: #prefer-common-nouns
**Prefer Common nouns** A common noun is a noun that isn't a proper noun: they are names for general things rather than names that identify specific things.

**Being Successful** Avoid plural, [mass](#mass-noun), and [collective](#collective-noun) nouns; as well as [words that act as nouns and other parts of speech]( # "unmarked plural form.")

**See also** [General](#general)

[Value Type]: #value-types
### Value Types
Avoid [deverbal](#deverbal) nouns for value types (nouns derived from verbs, e.g. words suffixed with -or, -ant, -ar -ian, -er, etc.)

**See also** [General](#general)

[Structs]: #structs
### Structs
Structs often function as [value types](#value-types), avoid [deverbal](#deverbal) nouns for structs (nouns derived from verbs, e.g. words suffixed with -or, -ant, -ian, -er, etc.)

**See also** [General](#general)

### Interfaces
**Prefer Adjectives Formed From Verbs** Adjectives describe attributes of something, like abilities.  Not all adjectives describe abilities, but as an interface is a _representation of an ability_ it's name should represent an action (formed from a verb).

The suffixes -able, -ible, and -ive are important: these suffixes form adjectives from verbs (actions, abilities).  -able/-ible are used with verbs for interfaces representing an inherent ability of an implementation &#40;*Enumerable* in `IEnumerable`, to represents something that you can [enumerate]( # "first-perrson present tense.")&#41; (or something that has the ability to be enumerated). -ive is used with verbs for interfaces that perform a type of functionality (*Transmissive* in `ITransmissive` for something that [transmits]( # "third-person past tense")).  

-able/-ible something that can have an action performed on it.  
-ive something that performs an action.

**See also** [General](#general)

### Variables

#### Members
**See also** [General](#general)

#### Parameters
**See also** [General](#general)

### General
<a name="avoid-ambiguity">**Avoid Ambiguity**</a>  
Avoid using words that are prone to misinterpretation or are used to mean many things.

**Avoid _[Zero Derivation Words]( # "also called conversion, is a kind of word formation involving the creation of a word--of a new word class--from an existing word--of a different word class--")_** &#40;**Avoid _Homographs_** or **Avoid _[Metonyms](#metonym) ("e.g. 'Washington' to mean 'federal government' Also: nounification, e.g.: 'ask' in place of 'question'.  ")_**&#41; [Zero derivation words](#zero-derivation-words) are when a new "word" (meaning) is created from another word without using derivation (e.g. affixes are common in creating new meanings and words, _deriving_ them from a root word and adding the affix). 

*Homograph* is another name for words spelled the same, but different meaning.  
*Metonym* means a word substituted for another with a different meaning.

### Idiosyncratic Guidelines
There get more into what you might call "non-generic" identifier guidelines, guidelines that complement the from-of-speech rules.

#### Messages - Events
An event is the embodiment of a significant change in state. (Event-driven architecture n.d.)  That fact (the occurrence) is recognized by software and represented by an instance of an event identifier.  It is a fact about something that happened in the past, it cannot be changed nor retracted. (Bonér 2017)  A _domain_ event signals something that has happened in the outside world that is of interest to the application. It's transmitted to the application in some data structure (event identifier), carrying with it the data that describes the event. (Fowler 2006)

**Prefer to name event identifiers with a _&lt;subject&gt;&lt;verb&gt;_ convention**.  _Subject_ is a common noun or a noun phrase and the _verb_ should have a tense in the past (past tense).  Not all past-tense verbs take this form, but typically past-tense verbs are a _simple present tense_ verb suffixed with "-ed".

**Prefer the subject name be the name of the _domain resource_ whose state changed**.  Resources should be domain-specific and should not relate to implementation detail
_avoid "record", "field"_, etc.

To [Avoid Ambiguity](#avoid-ambiguity) **Prefer to limit the number of past tense verbs used**.  Also **prefer to choose a single past tense verb for a particular circumstance**.  Without getting lost in philosophy, here's a list of past-tense verbs for use with common event/state-change scenarios in software:

#### Generic Outcome-based Event Name Suffixes
This is a fairly complete list of generic types of events; when used they should be consistent the meanings described here:
- **Created** signifies something new as come into existence (rather than Added).
- **Added** signifies something as been added to a container or collection.
- **Updated** signifies the value properties or attributes of an existing thing (entity) have been changed.
- **Changed** signifies an entire thing (entity) has been replaced with another.
- **Deleted** means something is no longer accessible in some context.
- **Destroyed** means removed from existence, no possible way to ever get it back.
- **Removed** means the opposite of Added, a thing has been moved out of, or removed from a container/collection
- **Modified** means structure or schema has changed and isn't related to instantiated entities.

There will, of course, be domain-specific past tense verbs.  For example _Qualified, Eligible_. Be faithful to the domain, if Qualified is an important event, model it in addition to the resource being updated: ClientQualified, ClientUpdated.

#### Messages - Commands

** in progres **

## References
[.NET Framework Guidelines - Naming](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/naming-guidelines)
