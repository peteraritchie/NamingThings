# Naming Things
Content ([TL;DR][Detailed Guidance]) on tips, tricks, advice, practices for naming things in software/technology

## Drivers
Naming guidance like .NET Framework Guidelines are helpful, but they only help in minor situations and don't really a lot help solve the naming things problem in software.

## Vision
Detail research results around where some of the pain points in naming are, analyze potential solutions, and provide guidance for making naming things easier.

## Guiding Principles
- There are always exceptions, we can only mitigate their effect
- **Purposefulness** This means doing this on purpose, or by design.
- **Consistency** Enough said
- **[Least Astonishment](https://en.wikipedia.org/wiki/Principle_of_least_astonishment)** Building on consistency, where consistency of intuitiveness is important.

## Scope
These guidelines focus on wording over capitalization.  Capitalization is important, but that is an externally-defined style.

## Detailed Guidance
[Detailed Guidance]: #detailed-guidance
### Definitions
[Definitions]: #definitions
<dl>
  <dt>countable noun</dt><dd>...coming soon...</dd>
  <dt>mass noun</dt><dd>...coming soon...</dd>
  <dt>uncountable noun</dt><dd>...coming soon...</dd>
  <dt>collective noun</dt><dd>...coming soon...</dd>
  <dt>deverbal noun</dt><dd>...coming soon...</dd>
  <dt>noun of action</dt><dd>...coming soon...</dd>
  <dt>Zero Derivation Words</dt><dd>...cmming soon...</dd>
  <dt>metonym</dt><dd>...coming soon...</dd>
  <dt>homograph</dt><dd>...coming soon...</dd>
</dl>

### Principles
[Compartmentalization]: #compartmentalization
**Compartmentalization** Compartmentalize things that can be reasoned about independently of other things; these are the things that require names.  One thing that makes naming hard is naming things that have no unique attributes or behavior.

[Namespaces]: #namespace
### Namespaces
Namespaces suit a couple of needs, both relating to the grouping of types.  Grouping types within a namespace should be based on functionality.  

**Use a pluralized noun for namespaces that group types related by interface A namespace that contains types related by interface should be named with a pluralized noun**. One is a grouping of types that implement a specific interface.  A `Collections` suffix signifies the namespace contains types that implement interfaces that allow types to act as collections.

**Use a mass deverbal noun for namespaces that group types related by functionality (but different)**.  The other grouping can cause some consternation because the grouping can easily feel subjective.  You can also group types by functional usage.  This type of grouping can be thought of as capability grouping.  In which case the namespace name can be a noun of action or a noun based on a verb.  The suffixes "-ion" and "-ing" come into play here.  e.g. `Processing` or `Administration`.

**Use countable nouns or pluralized adjectives for namespaces that classify other namespaces** <code>System.<i>Diagnostics</i>.Tracing</code>

**Use adjectives or mass nouns to sub-group types related by interface** <code>System.Collections.<i>Generic</i></code>, <code>System.ComponentModel.<i>Composition</i></code>.

**Being successful**: Perform grouping on purpose, only group types with similar attributes or similar behavior (randomly grouping types within a namespace is very subjective).  Prefer nouns that describe an act or responsibility. Avoid ending in "-ion", avoid words ending in "-tion" or "-sion.  A "mass noun" is also called a noncountable noun.  Avoid words that function as mass deverbal nouns but often also function as adjectives (need example).

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

**Being Successful** Avoid plural, mass, and collective nouns; as well as [words that act as nouns and other parts of speech]( # "unmarked plural form.")

**See also** [General](#general)

### Value Types
Avoid deverbal nouns for value types (nouns derived from verbs, e.g. -or, -ant, -ar -ian, 
**See also** [General](#general)
[Structs]: #structs
### Structs
Structs often function as value types, avoid deverbal nouns for structs (nouns derived from verbs, e.g. -or, -ant, -ian, -er, etc.)

**See also** [General](#general)

### Interfaces
**Prefer Adjectives Formed From Verbs** Adjectives describe attributes of something, like abilities.  Not all adjectives describe abilities, but as an interface is a representation of an ability it's name should represent an action. The suffixes -able, -ible, and -ive are important: these suffixes form adjectives from verbs (actions, abilities).  -able/-ible are used with verbs for interfaces representing an inherent ability of an implementation &#40;*Enumerable* in `IEnumerable`, to represents something that you can [enumerate]( # "first-perrson present tense.")&#41; (or something that has the ability to be enumerated). -ive is used with verbs for interfaces that perform a type of functionality (*Transmissive* in `ITransmissive` for something that [transmits]( # "third-person past tense")).  

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
