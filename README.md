# PyG
PyG is has been written to help produce Gantt charts from spreadsheets using Python. It is in a very rough-and-ready state...be gentle with it!



---



To-do:

- Split into smaller functions.
- Extract data from spreadsheet and re-package as a <u>hierarchical dictionary</u> (rather than a series of lists).
- Export dictionary as JSON (for debug checking).
- Include flags at the top of the notebook to modify settings (such as annotation with appended roman numerals).





## Defining the Gantt data

The minimum requirement for the spreadsheet is that it has the following column (titled on row 1):

- `Start`...of type datetime
- `End`...of type datetime
- `LineTitle`...of type string

When `Start`, `End` and `LineTitle` are specified, then a new activity (line) is created... however, if:

- one of either `Start` or `End` is not specified, then the `LineTitle` is assumed to be a Group Title
- `LineTitle` is not specified (but both `Start` or `End` are specified), then the work package is considered to be part of the same activity and therefore sits on the same line.

Additional information can be included in columns titled:

- `Color`...of type string, used to look-up hex colour defined in `ColorScheme`
- `Annotation`...of type string
- `ResourceAllocation`