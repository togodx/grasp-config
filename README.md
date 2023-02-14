# grasp-config

Install [rdf-config](https://github.com/dbcls/rdf-config) and run the following command to generate config files for grasp under the `togodx-grasp` directory.

```
% rdf-config --config rdf-config/* --grasp togoid-grasp
```

Install [Grasp](https://github.com/dbcls/grasp) and point the above directory to launch the Grasp server.

```
RESOURCES_DIR=./togodx-grasp npm run watch
```

Example query:

```
query {
  ChEBI(id: "CHEBI:17232") {
    label
    inchi
    mass
    smiles
  }
  Rhea(id: "13973") {
    label
  }
  ClinVar(id: "18390") {
    label
  }
}
```

Notes:
* Currently, `type` in GraphQL is prefixed with capitalized config directory name (e.g., even UniProt is represented as the subject class in rdf-config/uniprot/model.yaml, UniprotUniProt will be used for `type`)
