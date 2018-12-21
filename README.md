# Naming Things
Content ([TL;DR][Detailed Guidance]) on tips, tricks, advice, practices for naming things in software/technology

## Drivers
Naming guidance like .NET Framework Guidelines are helpful, but they only help in minor situations and don't really a lot help solve the naming things problem in software.

## Vision
Detail research results around where some of the pain points in naming are, analyze potential solutions, and provide guidance for making naming things easier.

## Guiding Principles
- There are always exceptions, we can only mitigate their effect
- **Purposefulness** This
- **Consistency** Enough said
- **[Least Astonishment](https://en.wikipedia.org/wiki/Principle_of_least_astonishment)** Building on consistency, where a consistency of intuitiveness is important.

## Scope
These guidelines focus on wording over capitalization.  Capitalization is important, but that is an already-defined style.

## Detailed Guidance
[Detailed Guidance]: #detailed-guidance

### Principles
[Compartmentalization]: #compartmentalization
**Compartmentalization** Compartmentalize things that can be reasoned about; these are the things that require names.  One thing that makes naming hard is naming things that have no unique attributes or behavior.

[Assemblies]: #assemblies
### Assemblies; Class Libraries and Programs
Assemblies are the deployable binary groupings of compiled code.  As such, the context of these binaries is generally the file system or URIs.  Assemblies often travel in packages and thus have unique constraints that affect naming.  Assembly names can be scoped by directory, but that depends on deployment and choices outside of your control (names of 3<sup>rd</sup> party assemblies and packages).

[Namespaces]: #namespace
### Namespaces
Namespaces suit a couple of needs, both relating to the grouping of types.  Grouping is related to functionality, one is by related functionality, the other is by specific functionality.

Specific functionality is the easiest.  This effectively means grouping types that implement a particular interface or a particular hierarchy of interfaces.  In this case, the name of the enclosing interface can by the name of the interface, pluralized.  e.g. `Collections`.

The other case can cause some consternation because naming can easily feel subjective.  Randomly grouping types within a namespace is very subjective--you're subjectively groups types.  Perform grouping on purpose, only group types with similar attributes or similar behavior.  You can also group types by functional usage.  This type of grouping can be thought of as capability grouping.  In which case the namespace name can be a noun of action or a noun based on a verb.  The suffixes "-ion" and "-ing" come into play here.  e.g. `Processing` or `Administration`.

**Being successful**: despite being nouns, avoid using words that can act nouns of action (e.g. gerunds) to name other categories unless you absolutely have to.  The more different parts of speech and different subcategories of parts of speech are only used in one place, the less likely naming collisions will occur.

#### Summary
Group types in namespaces by a single common attribute: group by a particular interface/ability, or group by a common capability they contribute to.

**See also** [General](#general)

[Classes]: #classes
### Classes
[Prefer Common Nouns]: #prefer-common-nouns
**Prefer Common nouns** A common noun is a noun that isn't a proper noun: they are names for general things rather than names that identify specific things.

**Being Sucessful** Avoid proper, plural, mass, and collective nouns; as well as [words that act as nouns and other parts of speech]( # "unmarked plural form.")

**See also** [General](#general)

### Structs
**See also** [General](#general)

### Interfaces
**Prefer Adjectives Formed From Verbs** Adjectives describe attributes of something, like abilities.  Not all adjectives describe abilities, but as an interface is a representation of an ability it's name should represent an action. The suffixes -able, -ible, and -ive are important: these suffixes form adjectives from verbs (actions, abilities).  -able/-ible are used with verbs for interfaces representing an inherent ability of an implementation &#40;*Enumerable* in `IEnumerable`, to represents something that you can [enumerate]( # "first-preson present tense.")&#41; (or something that has the ability to be enumerated). -ive is used with verbs for interfaces that perform a type of functionality (*Transmissive* in `ITransmissive` for something that [transmits]( # "third-person past tense")).  

-able/-ible something that can have an action performed on it.  
-ive something that performs an action.

**See also** [General](#general)

### Members
**See also** [General](#general)

### Variables

### Parameters
**See also** [General](#general)

### General
**Avoid Ambiguity** Avoid using words that are prone to misinterpretation or are used to mean many things.

**Avoid _[Zero Derivation Words]( # "also called conversion, is a kind of word formation involving the creation of a word--of a new word class--from an existing word--of a different word class--")_** &#40;**Avoid _Homographs_** or **Avoid _[Metonyms]( # "e.g. 'Washington' to mean 'federal government' Also: nounification, e.g.: 'ask' in place of 'question'.  ")_**&#41; Zero derivation words are when a new "word" (meaning) is created from another word without using derivation (e.g. affixes are common in creating new meanings and words, _deriving_ them from a root word and adding the affix). 

*Homograph* is another name for words spelled the same, but different meaning.  
*Metonym* means a word substituted for another with a different meaning.

## References
[.NET Framework Guidelines - Naming](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/naming-guidelines)
