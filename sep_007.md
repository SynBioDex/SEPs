SEP 007 -- combinatorial assemblies initial draft
===================================

SEP                     | <leave empty>
----------------------|--------------
**Title**                | combinatorial assemblies
**Authors**           | Matthew Pocock (author1mail at xxmail com)
**Editor**            | Raik Gruenberg
**Type**               | Data Model
**SBOL Version** | 2.2
**Status**             | Draft
**Created**          | 19-Aug-2016
**Last modified**  |

Abstract
-----------

Describe combinatorial DNA assemblies. This is an early draft taken from an ongoing discussion on sbol-dev@.

1. Rationale <a name="rationale"></a>
----------------

See: SBOL-Specification/#31 and SBOL-Specification/#61
https://github.com/SynBioDex/SBOL-specification/issues/31

2. Specification <a name="specification"></a>
----------------------------------------------

I propose introducing a `CombinatorialDesign` top-level class. Combinatorial designs would then be described as follows:

  (1) define a ComponentDefinition with the skeleton of your design. Add subcomponents for each of the sub-parts. 

  > You'd use the most specific (abstract) sub-part that makes sense. For example, you may have a child that is any glucose 
  > inducible promoter, any RBS at all, a GFP, any terminator.

  (2) Create a CombinatorialDesign referring to this ComponentDefinition. 
  
  (3) Provide an `alternatives` object inside the CombinatorialDesign that links between any subcomponent and a bag 
  of ComponentDefinitions. 
  
  (4) Generate any number of ComponentDefinitions from this by picking single alternatives from the CombinatorialDesign.
  
**Advantages:**

We have a complete log of the expansion options and of the individual expansions. 
You can also use provo annotations to document that a ComponentDefinition was made by expanding
a CombinatorialDesign. It also gives you a separation between the abstract design and the strategy 
used to refine it into a concrete design. You could take the same template and expand it with 
several different CombinatorialDesign instances with different sets of alternatives, 
or expand out that same template manually.


3. Example or Use Case <a name='example'></a>
-------------------------------

< Describe brief examples or use cases >

4. Backwards Compatibility <a name='compatibility'></a>
-----------------

New class, no issues anticipated.

5. Discussion <a name='discussion'></a>
-----------------

### 5.1 discussion point

To be added after initial proposal.


6. Competing SEPs <a name='competing_seps'></a>
-----------------

Currently none.


References <a name='references'></a>
----------------

[SBOL]: http://sbolstandard.org
[1]: https://www.python.org/dev/peps/pep-0001

Copyright <a name='copyright'></a>
-------------
<p xmlns:dct="http://purl.org/dc/terms/" xmlns:vcard="http://www.w3.org/2001/vcard-rdf/3.0#">
  <a rel="license"
     href="http://creativecommons.org/publicdomain/zero/1.0/">
    <img src="http://i.creativecommons.org/p/zero/1.0/88x31.png" style="border-style: none;" alt="CC0" />
  </a>
  <br />
  To the extent possible under law,
  <a rel="dct:publisher"
     href="sbolstandard.org">
    <span property="dct:title">SBOL developers</span></a>
  has waived all copyright and related or neighboring rights to
  <span property="dct:title">SEP 007</span>.
This work is published from:
<span property="vcard:Country" datatype="dct:ISO3166"
      content="US" about="sbolstandard.org">
  United States</span>.
</p>
