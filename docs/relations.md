#### Defining concepts with semantic relations

A GACS concept is formally defined by its "semantic neighborhood", a web of
associative and hierarchical relations with other concepts in GACS.  The
concept
[_alfalfa_](http://tester-os-kktest.lib.helsinki.fi/gacsdemo/gacs/en/page/C1235),
for example, is defined by relations such as:

* _alfalfa_ `hasType` _Product_
* _alfalfa_ `BT` _legumes_
* _alfalfa_ `RT` _fodder plants_ 
* _fodder plants_ `RT` _livestock feeding_
* _fodder plants_ `RT` _forage_
* _fodder plants_ `RT` _hay_

These relations are reflected in the GACS definition of _alfalfa_ as: "A
valuable _leguminous crop_ for _forage_ or _hay_ used in _livestock feeding_".
However, less than 20% of the concepts in GACS have definitions, and crafting
definitions for the other 80% would be expensive, especially across
translations in multiple languages.  Moreover, narrative definitions are less
useful than semantic relations for automated processing because relations
between concepts can only roughly be computed from label strings, sentence
parsing, and the co-occurrence of words.  

Explicit semantic relations provide a basis for browsing broader, narrower, or
related concepts and for expanding queries.  They can be used to disambiguate
meanings and to check concept hierarchies for consistency.  Because they
cluster related examples, they are less vulnerable than definitions to
misinterpretation by translators.  In GACS, definitions are "nice to have", but
semantic relations are essential.  For maintainability, the set of semantic
relations used in GACS has been kept as simple and obvious as possible.

#### Broader, narrower, and related concepts

GACS concepts are linked among themselves with _related_, _broader_, and
_narrower_ relations as defined in SKOS, which are themselves based on standard
thesaurus relations (_RT_, _BT_, and _NT_).  _Broader_ and _narrower_ do not
formally distinguish between "is a" and "part of" relations. In GACS, _broader_
and _narrower_ are generally intended to imply general-to-specific "is a"
relations, though not in a formally strict ontological sense, and there are
plenty of exceptions (for example,
[Maryland](http://tester-os-kktest.lib.helsinki.fi/gacsdemo/gacs/en/page/C10429),
which is "part of" the [North Eastern States
(USA)](http://tester-os-kktest.lib.helsinki.fi/gacsdemo/gacs/en/page/C20128)).

#### Top-level concepts

All concepts in GACS are grouped under three concepts that have no broader
concepts (top-level concepts): 

* _Objects_: material things that can be seen, touched, visited (locations),
  including conceptual objects such as ideas and models.
* _Events and actions_: things that happen, such as processes or phenomena.
* _Properties_: attributes, characteristics, or qualities of things.

In thesaurus practice, top concepts are typically intended for use in faceted
browsing or in creating microthesauri.  In GACS, the top concepts can be used
as entry points for browsing GACS by thematic group in the Hierarchy tab of the
Skosmos browser.  The top concepts are too abstract to be used for indexing.
Concepts further down in the hierarchy are more concrete and more useful both
for indexing and for clarifying meanings (disambiguation).  While a certain
amount of polyhierarchy (where concepts have more than one broader concept) may
be inevitable, even desirable, it seems unrealistic to expect that a complex
polyhierarchy could be enforced and maintained in a principled way and at
scale.  For GACS, the goal is to to keep the hierarchy simple, and as close to
the ideal of cascading "is a" relations, as pragmatically possible.

#### Concept types

Differentiating between types of concept can help clarify the meaning of
concepts across the hierarchy.  While top concepts, with their hierarchies,
might in principle be used to group concepts by the type of thing they
represent, such as "organisms", the GACS hierarchy does not follow the
principle of general-to-specific (hyponymy) strictly enough to ensure that "is
a" ("type of") relations always hold; the hierarchy also contains "part of"
(meronym) relations.  The GACS Working Group opted to explore the usefulness of
concept types by creating types of SKOS concept for just four particularly
obvious and clearly defined types of things: _Chemical_, _Geographical_,
_Organism_, and _Product_, with _Topic_ as a fifth "catch-all" type for all
concepts not otherwise covered (and with the expectation that _Topic_ might be
further differentiated over time).

#### Custom (non-SKOS) relations between concepts

Some thesauri, such as AGROVOC and CAB Thesaurus, use semantic relations beyond
standard SKOS properties to express more specific relations between concepts.
However, efforts to "ontologize" thesauri with such additional relations
struggle to ensure that the properties would be applied consistently,
comprehensively, and maintainably.  The GACS Working Group decided that custom
relations should only be created for use cases important enough to justify the
effort.  Two properties qualified: _hasProduct_ and _productOf_, for relating
[fish as a product](http://id.agrisemantics.org/gacs/C2986) to [fish as an
organism](http://id.agrisemantics.org/gacs/C1089).

#### Mapping to concepts in external vocabularies

GACS was created at the intersection of three existing thesauri, and each
concept in GACS has a SKOS "exact match" relation back to the concept or
concepts in AGROVOC, CABT, and NALT from which it was created.  

In addition, the 540 concepts of type _Geographical_ have SKOS "close match"
relations to entities in Wikidata.  These mappings facilitate access from GACS
to Wikidata information about geographic places (such as coordinates,
population, language, and religions); to Wikidata mappings out to other
geo-oriented vocabularies such as GeoNames and OpenStreetMap; and to mappings
out to library-oriented authority files such as the Library of Congress Name
Authority File, GND (German union authority), BNF, VIAF and ISNI. As an
example, see the Wikidata entry for
[Alberta](https://www.wikidata.org/wiki/Q1951)) and the corresponding [GACS
concept](http://tester-os-kktest.lib.helsinki.fi/gacsdemo/gacs/en/page/C15421).

This exercise suggests a model by which GACS might, in the future, devolve or
delegate responsibility for specific types of GACS concepts to external
authorities.  Geographic places are an obvious candidate for delegation because
they are not specific to agriculture and because they have been given URIs in
so many other sources.  Once mapped to a external source, a given set of GACS
concepts could be reduced to a set of URIs clearly marked as dependent on the
external URIs, and the GACS community could promote the use of the external
URIs.  GACS concepts cannot simply be deleted because their URIs must be
credibly persistent, in accordance with explicit policies, if GACS itself is to
be credibly deployable.  On the other hand, the GACS URIs also provide a
fallback option should the external authority ever cease operation, a
contingency that would be prudent to anticipate by policy.

