In GACS, concepts are labeled with natural-language phrases.  Concept labels,
or "terms", are preferred or alternative.  Preferred terms can be used as tags
for subject indexing (as "descriptors").  The precision of term-based indexing
depends on the uniqueness of the strings used to encode the terms. In
production environments, for example when thesauri are used in complex
workflows, it is important that preferred terms also remain stable. 

Terms other than preferred terms are non-preferred, or alternative
("non-descriptors").  Because non-descriptors are used to direct users to
preferred terms, they are also known as "lead-in-terminology".  In standard
thesaurus practice, non-descriptors are not used to tag resources for indexing
and retrieval.

In accordance with thesaurus practice, SKOS prescribes that concepts not have
two preferred labels in a given language and recommends that preferred labels
in a given language be unique within the context of a given concept scheme
(e.g., that no two concepts share the prefLabel "lime"@en).  In accordance with
the SKOS specification, it is an error if a concept has a same literal both as
its preferred label and as an alternative label.

In GACS:

1. Preferred labels MUST be unique for the core languages of GACS. That 
   is, one concept MUST NOT have the same preferred label as another 
   concept in the same (core) language.
   Note: "unique" is case insensitive.

2. Preferred labels SHOULD be unique for the other (non-core) languages 
   of GACS. That is, one concept SHOULD NOT have the same preferred label as 
   another concept in the same (non-core) language.

3. In core languages, an alternate label MUST NOT be identical to a 
   preferred label of another concept.

4. In other (non-core) languages, an alternate label SHOULD NOT be 
   identical to a preferred label of another concept.

5. Alternate labels MUST be unique for the core languages of GACS. That 
   is, one concept MUST NOT have the same alternate label as another 
   concept in the same (core) language.

6. Alternate labels SHOULD be unique for the other (non-core) languages 
   of GACS. That is, one concept SHOULD NOT have the same alternate label as 
   another concept in the same (non-core) language.

