# Multi-Verb-Labels
Repo containing the multiple verb, verb-only labels from the paper Learning Visual Actions Using Multiple Verb-Only Labels, [Michael Wray](http://mwray.github.io)(1) and Dima Damen(1), BMVC 2019.

(1) University of Bristol

**contact:** [michael.wray@bristol.ac.uk](mailto:michael.wray@bristol.ac.uk)

## Citing
When using the annotations, kindly reference:

```
@INPROCEEDINGS{wray2019learning,
    title={Learning Visual Actions Using Multiple Verb-Only Labels},
    author={Wray, Michael and Damen, Dima},
    booktitle={British Machine Vision Conference (BMVC)},
    year={2019}
}
```

## Annotation Details
This repo provides multi-verb, verb-only annotations for three datasets: BEOID [1], CMU-MMAC [2] and GTEA Gaze+ [3]. Each ground truth class was annotated by between 30-50 annotators from a list of 90 verbs and normalised giving a value between 0 and 1 for each verb (see paper for more details).



## Important Files/Folders
* `README.md (this file)`
* [`LICENSE.txt`](LICENSE.TXT)([info](#license))
* [`BEOID.pkl`](BEOID.pkl) ([info](#beoidpkl))
* [`CMU.pkl`](CMU.pkl) ([info](#cmupkl))
* [`GTEA.pkl`](GTEA.pkl) ([info](#gteapkl))
* [`class_order`](class_order.csv) ([info](#class_ordercsv))
* `raw_annotations` ([info](#raw_annotations))


## Class Names
The original class names are given in the form of verb_noun[+noun] where the hyphen (-) character separates multi-word verbs/nouns. Therefore the class `pour baking pan bowl` is represented as `pour_baking-pan+bowl`.

## File Structure

### BEOID.pkl
Python Pickle file containing the normalised annotations for the 34 different annotated classes in BEOID. The information is stored inside a dictionary with the keys representing the original verb-noun class labels and the values a 90 length vector of floats which represent the normalised values for each verb. The verb order can be found in [class_order.csv](#class_ordercsv).

### CMU.pkl
Python Pickle file containing the normalised annotations for the 30 different annotated classes in CMU-MMAC. The information is stored inside a dictionary with the keys representing the original verb-noun class labels and the values a 90 length vector of floats which represent the normalised values for each verb. The verb order can be found in [class_order.csv](#class_ordercsv).

### GTEA.pkl
Python Pickle file containing the normalised annotations for the 32 different annotated classes in GTEA Gaze+. The information is stored inside a dictionary with the keys representing the original verb-noun class labels and the values a 90 length vector of floats which represent the normalised values for each verb. The verb order can be found in [class_order.csv](#class_ordercsv).

### class_order.csv
Comma Separated Value file with the order of verbs which are used in the pickle files for each dataset and the order used in the raw annotations files.

### raw_annotations
Directory containing the raw annotations that were collected from Amazon Mechanical Turk (AMT). It has the following directory structure:
```
.
└── raw_annotations
    ├── BEOID
    │   ├── fill_cup
    │   ├── ...
    │   └── turn_tap
    ├── CMU
    │   ├── close_fridge
    │   ├── ...
    │   └── twist-on_cap
    └── GTEA
        ├── close_freezer
        ├── ...
        └── turn-on_tap
```

Each class is a directory which contains the annotations from AMT as csv files (one per annotator) with the following format:

| Column Name  | Type       | Example          | Description                                  |
| ------------ | ---------- | ---------------- | -------------------------------------------- |
| `Verb`       | string     | `"Put_down"`     | The string representation of the verb.       |
| `Present`    | boolean    | 1                | Whether the annotator chose the verb or not. |

The verb column in each file is ordered with the same order in [class_order.csv](#class_ordercsv).

## License
All files in this dataset are copyright by us and published under the 
Creative Commons Attribution-NonCommerial 4.0 International License, found 
[here](https://creativecommons.org/licenses/by-nc/4.0/).
This means that you must give appropriate credit, provide a link to the license,
and indicate if changes were made. You may do so in any reasonable manner,
but not in any way that suggests the licensor endorses you or your use. You
may not use the material for commercial purposes.

##  References
[1] D. Damen, T. Leelasawassuk, O. Haines, A. Calway, and W. Mayol-Cuevas. You-do, I-learn: Discovering task relevant objects and their modes of interaction from multi-user egocentric video. In BMVC, 2014.

[2] F. De La Torre, J. Hodgins, A. Bargteil, X. Martin, J. Macey, A. Collado, and P. Beltran. Guide to the Carnegie Mellon University Multimodal Activity (CMU-MMAC) database. Robotics Institute, 2008.

[3] A. Fathi, Y. Li, and J. Rehg. Learning to recognize daily actions using gaze. In ECCV, 2012.
