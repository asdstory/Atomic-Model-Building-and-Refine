#### From : 

- https://www.cgl.ucsf.edu/chimera/docs/UsersGuide/midas/frameatom_spec.html

- https://www.cgl.ucsf.edu/chimera/1.1700/docs/UsersGuide/midas/atom_spec.html

Subcategorizations are appended to the basic specification. The symbol for the relevant category (#, :, or @) must precede the subcategory specification, although they need not be immediately adjacent. Because commas are used only to separate values of the basic reference levels (model, residue, and atom), they cannot be used to separate values of the sublevels directly. For example,

#0.1-3,5

is interpreted as submodels 1-3 of model 0 and all of model 5, while

#0.1-3,.5

indicates submodels 1-3 of model 0 and submodel 5 of all models.

A subcategory specification applies only to the preceding category value(s) not separated from it by any commas. Thus,

:50.B,.D

indicates residue 50 in chain B and all residues in chain D;

:12-15,26-28.a,45.b@ca

specifies CA atoms in residues 12-15 in all chains (except the special chains het and water), 26-28 in chain A, and 45 in chain B. The following specifies residues 12-15 in no-ID chains only:

:12-15.

More examples:

:.b

- chain B

:.a@n,ca,c,o

- peptide backbone atoms in chain A

:195.a,221.a@n,ca,c,o

- peptide backbone atoms in residues 195 and 221 of chain A

:522.water

- water residue 522 (a HETATM residue named HOH or WAT without a chain ID in the input file)

@.a

- all atoms with alternate location identifier A

WILD CARDS

The global wild card * matches all atoms in a residue or all residues in a model. It stands alone as a symbol, that is, it cannot be used to match parts of names, such as G* or *A. The partial wild card = matches parts of atom or residue names but not parts of residue sequence numbers; similarly, the single-character wild card ? matches single characters within residue or atom names but not single digits within residue sequence numbers. For example:

#1:12@*

- or -

#1:12

- all atoms in residue 12 of model 1

#0,1,2:50-*@CA

- all alpha carbon atoms in residues 50 to the end of models 0, 1 and 2

#2:G??

- all residues which have three-letter names beginning with G in model 2

:fmn@?1

- atoms within residue FMN which have two-letter names ending with 1

@S=

- all atoms which have names beginning with S; in general, this will be all sulfur atoms

#0@H@H?@H??

- all atoms with one-, two-, or three-letter names beginning with H in model 0

### Zones

Zone specifiers indicate atoms and residues that are within or beyond a given distance of the referenced atom(s). z< and zr< specify all residues with any atom within the given distance from the referenced atoms. za< specifies all atoms within the given distance. z>, zr>, and za> yield the sets complementary to their < counterparts. For example,

#1:gtp za<10.5

specifies all atoms within 10.5 Å of any atom in residue GTP, model 1.
Zone specifiers refer to atoms only, not surfaces; however, the command zonesel allows basing zones on surfaces and including surfaces in zones.

Built-in Classifications
Any of the entries in the following sections of the Select menu can be used for command-line atom specification:

Chemistry
Residue... amino acid category
Structure
For example, Structure includes
type of molecule: protein, nucleic acid, markers
protein secondary structure: helix, strand, coil
automatic categories for surface calculation: main, ligand, solvent, ions
... whereas Chemistry includes all of the element symbols (C, Fe, etc.) and many functional groups (disulfide, phosphate, ether O, etc.). The same pattern of capitalization and spaces, if any, as shown in the Select menu should be used. Where there is ambiguity, the parent menu should be included in the specification, for example, “IDATM type.H” or “element.H” instead of “H” alone. The parent menu can be included in this manner even when not necessary.
One can also use custom amino acid categories that have been defined with ResProp and custom categories for surface calculation that have been defined with the command msms cat (surfcat). If a saved selection has the same name as a surface category, the saved selection will be used.

Some examples:

side chain/base.without CA/C1'

- or -

without CA/C1'

- atoms in amino acid side chains (not including CA) and atoms in nucleic acid bases (not including C1'); using “with” instead of “without” would include CA/C1'

#1 & Mg

- magnesium atoms/ions in model 1

helix & positive

- residues in helices that are also in the positive amino acid category

carboxylate

- atoms in carboxylate groups

solvent

- atoms automatically categorized as solvent



