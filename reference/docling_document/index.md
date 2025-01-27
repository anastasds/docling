# Docling Document

This is an automatic generated API reference of the DoclingDocument type.

## doc

Package for models defined by the Document type.

Classes:

- DoclingDocument
          –
          
DoclingDocument.
- DocumentOrigin
          –
          
FileSource.
- DocItem
          –
          
DocItem.
- DocItemLabel
          –
          
DocItemLabel.
- ProvenanceItem
          –
          
ProvenanceItem.
- GroupItem
          –
          
GroupItem.
- GroupLabel
          –
          
GroupLabel.
- NodeItem
          –
          
NodeItem.
- PageItem
          –
          
PageItem.
- FloatingItem
          –
          
FloatingItem.
- TextItem
          –
          
TextItem.
- TableItem
          –
          
TableItem.
- TableCell
          –
          
TableCell.
- TableData
          –
          
BaseTableData.
- TableCellLabel
          –
          
TableCellLabel.
- KeyValueItem
          –
          
KeyValueItem.
- SectionHeaderItem
          –
          
SectionItem.
- PictureItem
          –
          
PictureItem.
- ImageRef
          –
          
ImageRef.
- PictureClassificationClass
          –
          
PictureClassificationData.
- PictureClassificationData
          –
          
PictureClassificationData.
- RefItem
          –
          
RefItem.
- BoundingBox
          –
          
BoundingBox.
- CoordOrigin
          –
          
CoordOrigin.
- ImageRefMode
          –
          
ImageRefMode.
- Size
          –
          
Size.

### DoclingDocument

Bases: BaseModel

DoclingDocument.

Methods:

- add\_code
            –
            
add\_code.
- add\_group
            –
            
add\_group.
- add\_heading
            –
            
add\_heading.
- add\_list\_item
            –
            
add\_list\_item.
- add\_page
            –
            
add\_page.
- add\_picture
            –
            
add\_picture.
- add\_table
            –
            
add\_table.
- add\_text
            –
            
add\_text.
- add\_title
            –
            
add\_title.
- check\_version\_is\_compatible
            –
            
Check if this document version is compatible with current version.
- export\_to\_dict
            –
            
Export to dict.
- export\_to\_document\_tokens
            –
            
Exports the document content to a DocumentToken format.
- export\_to\_element\_tree
            –
            
Export\_to\_element\_tree.
- export\_to\_html
            –
            
Serialize to HTML.
- export\_to\_markdown
            –
            
Serialize to Markdown.
- export\_to\_text
            –
            
export\_to\_text.
- iterate\_items
            –
            
iterate\_elements.
- load\_from\_json
            –
            
load\_from\_json.
- num\_pages
            –
            
num\_pages.
- print\_element\_tree
            –
            
Print\_element\_tree.
- save\_as\_document\_tokens
            –
            
Save the document content to a DocumentToken format.
- save\_as\_html
            –
            
Save to HTML.
- save\_as\_json
            –
            
Save as json.
- save\_as\_markdown
            –
            
Save to markdown.
- save\_as\_yaml
            –
            
Save as yaml.
- validate\_document
            –
            
validate\_document.
- validate\_tree
            –
            
validate\_tree.

Attributes:

- body
              (GroupItem)
          –
- furniture
              (GroupItem)
          –
- groups
              (List[GroupItem])
          –
- key\_value\_items
              (List[KeyValueItem])
          –
- name
              (str)
          –
- origin
              (Optional[DocumentOrigin])
          –
- pages
              (Dict[int, PageItem])
          –
- pictures
              (List[PictureItem])
          –
- schema\_name
              (Literal['DoclingDocument'])
          –
- tables
              (List[TableItem])
          –
- texts
              (List[Union[SectionHeaderItem, ListItem, TextItem, CodeItem]])
          –
- version
              (Annotated[str, StringConstraints(pattern=VERSION\_PATTERN, strict=True)])
          –

#### body

#### furniture

#### groups

#### key\_value\_items

#### name

#### origin

#### pages

#### pictures

#### schema\_name

#### tables

#### texts

#### version

#### add\_code

add\_code.

Parameters:

- text
              (str)
          –
          
str:
- code\_language
              (Optional[CodeLanguageLabel], default:
                  None
)
          –
          
Optional[str]: (Default value = None)
- orig
              (Optional[str], default:
                  None
)
          –
          
Optional[str]:  (Default value = None)
- prov
              (Optional[ProvenanceItem], default:
                  None
)
          –
          
Optional[ProvenanceItem]:  (Default value = None)
- parent
              (Optional[NodeItem], default:
                  None
)
          –
          
Optional[NodeItem]:  (Default value = None)

#### add\_group

add\_group.

Parameters:

- label
              (Optional[GroupLabel], default:
                  None
)
          –
          
Optional[GroupLabel]:  (Default value = None)
- name
              (Optional[str], default:
                  None
)
          –
          
Optional[str]:  (Default value = None)
- parent
              (Optional[NodeItem], default:
                  None
)
          –
          
Optional[NodeItem]:  (Default value = None)

#### add\_heading

add\_heading.

Parameters:

- label
          –
          
DocItemLabel:
- text
              (str)
          –
          
str:
- orig
              (Optional[str], default:
                  None
)
          –
          
Optional[str]:  (Default value = None)
- level
              (LevelNumber, default:
                  1
)
          –
          
LevelNumber:  (Default value = 1)
- prov
              (Optional[ProvenanceItem], default:
                  None
)
          –
          
Optional[ProvenanceItem]:  (Default value = None)
- parent
              (Optional[NodeItem], default:
                  None
)
          –
          
Optional[NodeItem]:  (Default value = None)

#### add\_list\_item

add\_list\_item.

Parameters:

- label
          –
          
str:
- text
              (str)
          –
          
str:
- orig
              (Optional[str], default:
                  None
)
          –
          
Optional[str]:  (Default value = None)
- prov
              (Optional[ProvenanceItem], default:
                  None
)
          –
          
Optional[ProvenanceItem]:  (Default value = None)
- parent
              (Optional[NodeItem], default:
                  None
)
          –
          
Optional[NodeItem]:  (Default value = None)

#### add\_page

add\_page.

Parameters:

- page\_no
              (int)
          –
          
int:
- size
              (Size)
          –
          
Size:

#### add\_picture

add\_picture.

Parameters:

- data
          –
          
List[PictureData]: (Default value = [])
- caption
              (Optional[Union[TextItem, RefItem]], default:
                  None
)
          –
          
Optional[Union[TextItem:
- RefItem]]
          –
          
(Default value = None)
- prov
              (Optional[ProvenanceItem], default:
                  None
)
          –
          
Optional[ProvenanceItem]:  (Default value = None)
- parent
              (Optional[NodeItem], default:
                  None
)
          –
          
Optional[NodeItem]:  (Default value = None)

#### add\_table

add\_table.

Parameters:

- data
              (TableData)
          –
          
TableData:
- caption
              (Optional[Union[TextItem, RefItem]], default:
                  None
)
          –
          
Optional[Union[TextItem, RefItem]]:  (Default value = None)
- prov
              (Optional[ProvenanceItem], default:
                  None
)
          –
          
Optional[ProvenanceItem]:  (Default value = None)
- parent
              (Optional[NodeItem], default:
                  None
)
          –
          
Optional[NodeItem]:  (Default value = None)
- label
              (DocItemLabel, default:
                  TABLE
)
          –
          
DocItemLabel:  (Default value = DocItemLabel.TABLE)

#### add\_text

add\_text.

Parameters:

- label
              (DocItemLabel)
          –
          
str:
- text
              (str)
          –
          
str:
- orig
              (Optional[str], default:
                  None
)
          –
          
Optional[str]:  (Default value = None)
- prov
              (Optional[ProvenanceItem], default:
                  None
)
          –
          
Optional[ProvenanceItem]:  (Default value = None)
- parent
              (Optional[NodeItem], default:
                  None
)
          –
          
Optional[NodeItem]:  (Default value = None)

#### add\_title

add\_title.

Parameters:

- text
              (str)
          –
          
str:
- orig
              (Optional[str], default:
                  None
)
          –
          
Optional[str]:  (Default value = None)
- prov
              (Optional[ProvenanceItem], default:
                  None
)
          –
          
Optional[ProvenanceItem]:  (Default value = None)
- parent
              (Optional[NodeItem], default:
                  None
)
          –
          
Optional[NodeItem]:  (Default value = None)

#### check\_version\_is\_compatible

Check if this document version is compatible with current version.

#### export\_to\_dict

Export to dict.

#### export\_to\_document\_tokens

Exports the document content to a DocumentToken format.

Operates on a slice of the document's body as defined through arguments
from\_element and to\_element; defaulting to the whole main\_text.

Parameters:

- delim
              (str, default:
                  '\n'
)
          –
          
str:  (Default value = "\n\n")
- from\_element
              (int, default:
                  0
)
          –
          
int:  (Default value = 0)
- to\_element
              (int, default:
                  maxsize
)
          –
          
Optional[int]:  (Default value = None)
- labels
              (set[DocItemLabel], default:
                  DEFAULT\_EXPORT\_LABELS
)
          –
          
set[DocItemLabel]
- xsize
              (int, default:
                  100
)
          –
          
int:  (Default value = 100)
- ysize
              (int, default:
                  100
)
          –
          
int:  (Default value = 100)
- add\_location
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_content
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_page\_index
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_table\_cell\_label
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_table\_cell\_text
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)

Returns:

- str
          –
          
The content of the document formatted as a DocTags string.

#### export\_to\_element\_tree

Export\_to\_element\_tree.

#### export\_to\_html

Serialize to HTML.

#### export\_to\_markdown

Serialize to Markdown.

Operates on a slice of the document's body as defined through arguments
from\_element and to\_element; defaulting to the whole document.

Parameters:

- delim
              (str, default:
                  '\n'
)
          –
          
Delimiter to use when concatenating the various Markdown parts. (Default value = "\n").
- from\_element
              (int, default:
                  0
)
          –
          
Body slicing start index (inclusive). (Default value = 0).
- to\_element
              (int, default:
                  maxsize
)
          –
          
Body slicing stop index (exclusive). (Default value = maxint).
- labels
              (set[DocItemLabel], default:
                  DEFAULT\_EXPORT\_LABELS
)
          –
          
The set of document labels to include in the export.
- strict\_text
              (bool, default:
                  False
)
          –
          
bool: Whether to only include the text content of the document. (Default value = False).
- image\_placeholder
              (str, default:
                  '<!-- image -->'
)
          –
          
The placeholder to include to position images in the markdown. (Default value = "\<!-- image -->").
- image\_mode
              (ImageRefMode, default:
                  PLACEHOLDER
)
          –
          
The mode to use for including images in the markdown. (Default value = ImageRefMode.PLACEHOLDER).
- indent
              (int, default:
                  4
)
          –
          
The indent in spaces of the nested lists. (Default value = 4).

Returns:

- str
          –
          
The exported Markdown representation.

#### export\_to\_text

export\_to\_text.

#### iterate\_items

iterate\_elements.

Parameters:

- root
              (Optional[NodeItem], default:
                  None
)
          –
          
Optional[NodeItem]:  (Default value = None)
- with\_groups
              (bool, default:
                  False
)
          –
          
bool:  (Default value = False)
- traverse\_pictures
              (bool, default:
                  False
)
          –
          
bool:  (Default value = False)
- page\_no
              (Optional[int], default:
                  None
)
          –
          
Optional[int]:  (Default value = None)
- \_level
              (int, default:
                  0
)
          –
          
(Default value = 0)

#### load\_from\_json

load\_from\_json.

Parameters:

- filename
              (Path)
          –
          
The filename to load a saved DoclingDocument from a .json.

Returns:

- DoclingDocument
          –
          
The loaded DoclingDocument.

#### num\_pages

num\_pages.

#### print\_element\_tree

Print\_element\_tree.

#### save\_as\_document\_tokens

Save the document content to a DocumentToken format.

#### save\_as\_html

Save to HTML.

#### save\_as\_json

Save as json.

#### save\_as\_markdown

Save to markdown.

#### save\_as\_yaml

Save as yaml.

#### validate\_document

validate\_document.

#### validate\_tree

validate\_tree.

### DocumentOrigin

Bases: BaseModel

FileSource.

Methods:

- parse\_hex\_string
            –
            
parse\_hex\_string.
- validate\_mimetype
            –
            
validate\_mimetype.

Attributes:

- binary\_hash
              (Uint64)
          –
- filename
              (str)
          –
- mimetype
              (str)
          –
- uri
              (Optional[AnyUrl])
          –

#### binary\_hash

#### filename

#### mimetype

#### uri

#### parse\_hex\_string

parse\_hex\_string.

#### validate\_mimetype

validate\_mimetype.

### DocItem

Bases: NodeItem

DocItem.

Methods:

- get\_image
            –
            
Returns the image of this DocItem.
- get\_location\_tokens
            –
            
Get the location string for the BaseCell.
- get\_ref
            –
            
get\_ref.

Attributes:

- children
              (List[RefItem])
          –
- label
              (DocItemLabel)
          –
- model\_config
          –
- parent
              (Optional[RefItem])
          –
- prov
              (List[ProvenanceItem])
          –
- self\_ref
              (str)
          –

#### children

#### label

#### model\_config

#### parent

#### prov

#### self\_ref

#### get\_image

Returns the image of this DocItem.

The function returns None if this DocItem has no valid provenance or
if a valid image of the page containing this DocItem is not available
in doc.

#### get\_location\_tokens

Get the location string for the BaseCell.

#### get\_ref

get\_ref.

### DocItemLabel

Bases: str, Enum

DocItemLabel.

Methods:

- get\_color
            –
            
Return the RGB color associated with a given label.

Attributes:

- CAPTION
          –
- CHECKBOX\_SELECTED
          –
- CHECKBOX\_UNSELECTED
          –
- CODE
          –
- DOCUMENT\_INDEX
          –
- FOOTNOTE
          –
- FORM
          –
- FORMULA
          –
- KEY\_VALUE\_REGION
          –
- LIST\_ITEM
          –
- PAGE\_FOOTER
          –
- PAGE\_HEADER
          –
- PARAGRAPH
          –
- PICTURE
          –
- REFERENCE
          –
- SECTION\_HEADER
          –
- TABLE
          –
- TEXT
          –
- TITLE
          –

#### CAPTION

#### CHECKBOX\_SELECTED

#### CHECKBOX\_UNSELECTED

#### CODE

#### DOCUMENT\_INDEX

#### FOOTNOTE

#### FORM

#### FORMULA

#### KEY\_VALUE\_REGION

#### LIST\_ITEM

#### PAGE\_FOOTER

#### PAGE\_HEADER

#### PARAGRAPH

#### PICTURE

#### REFERENCE

#### SECTION\_HEADER

#### TABLE

#### TEXT

#### TITLE

#### get\_color

Return the RGB color associated with a given label.

### ProvenanceItem

Bases: BaseModel

ProvenanceItem.

Attributes:

- bbox
              (BoundingBox)
          –
- charspan
              (Tuple[int, int])
          –
- page\_no
              (int)
          –

#### bbox

#### charspan

#### page\_no

### GroupItem

Bases: NodeItem

GroupItem.

Methods:

- get\_ref
            –
            
get\_ref.

Attributes:

- children
              (List[RefItem])
          –
- label
              (GroupLabel)
          –
- model\_config
          –
- name
              (str)
          –
- parent
              (Optional[RefItem])
          –
- self\_ref
              (str)
          –

#### children

#### label

#### model\_config

#### name

#### parent

#### self\_ref

#### get\_ref

get\_ref.

### GroupLabel

Bases: str, Enum

GroupLabel.

Attributes:

- CHAPTER
          –
- COMMENT\_SECTION
          –
- FORM\_AREA
          –
- KEY\_VALUE\_AREA
          –
- LIST
          –
- ORDERED\_LIST
          –
- SECTION
          –
- SHEET
          –
- SLIDE
          –
- UNSPECIFIED
          –

#### CHAPTER

#### COMMENT\_SECTION

#### FORM\_AREA

#### KEY\_VALUE\_AREA

#### LIST

#### ORDERED\_LIST

#### SECTION

#### SHEET

#### SLIDE

#### UNSPECIFIED

### NodeItem

Bases: BaseModel

NodeItem.

Methods:

- get\_ref
            –
            
get\_ref.

Attributes:

- children
              (List[RefItem])
          –
- model\_config
          –
- parent
              (Optional[RefItem])
          –
- self\_ref
              (str)
          –

#### children

#### model\_config

#### parent

#### self\_ref

#### get\_ref

get\_ref.

### PageItem

Bases: BaseModel

PageItem.

Attributes:

- image
              (Optional[ImageRef])
          –
- page\_no
              (int)
          –
- size
              (Size)
          –

#### image

#### page\_no

#### size

### FloatingItem

Bases: DocItem

FloatingItem.

Methods:

- caption\_text
            –
            
Computes the caption as a single text.
- get\_image
            –
            
Returns the image corresponding to this FloatingItem.
- get\_location\_tokens
            –
            
Get the location string for the BaseCell.
- get\_ref
            –
            
get\_ref.

Attributes:

- captions
              (List[RefItem])
          –
- children
              (List[RefItem])
          –
- footnotes
              (List[RefItem])
          –
- image
              (Optional[ImageRef])
          –
- label
              (DocItemLabel)
          –
- model\_config
          –
- parent
              (Optional[RefItem])
          –
- prov
              (List[ProvenanceItem])
          –
- references
              (List[RefItem])
          –
- self\_ref
              (str)
          –

#### captions

#### children

#### footnotes

#### image

#### label

#### model\_config

#### parent

#### prov

#### references

#### self\_ref

#### caption\_text

Computes the caption as a single text.

#### get\_image

Returns the image corresponding to this FloatingItem.

This function returns the PIL image from self.image if one is available.
Otherwise, it uses DocItem.get\_image to get an image of this FloatingItem.

In particular, when self.image is None, the function returns None if this
FloatingItem has no valid provenance or the doc does not contain a valid image
for the required page.

#### get\_location\_tokens

Get the location string for the BaseCell.

#### get\_ref

get\_ref.

### TextItem

Bases: DocItem

TextItem.

Methods:

- export\_to\_document\_tokens
            –
            
Export text element to document tokens format.
- get\_image
            –
            
Returns the image of this DocItem.
- get\_location\_tokens
            –
            
Get the location string for the BaseCell.
- get\_ref
            –
            
get\_ref.

Attributes:

- children
              (List[RefItem])
          –
- label
              (Literal[CAPTION, CHECKBOX\_SELECTED, CHECKBOX\_UNSELECTED, FOOTNOTE, FORMULA, PAGE\_FOOTER, PAGE\_HEADER, PARAGRAPH, REFERENCE, TEXT, TITLE])
          –
- model\_config
          –
- orig
              (str)
          –
- parent
              (Optional[RefItem])
          –
- prov
              (List[ProvenanceItem])
          –
- self\_ref
              (str)
          –
- text
              (str)
          –

#### children

#### label

#### model\_config

#### orig

#### parent

#### prov

#### self\_ref

#### text

#### export\_to\_document\_tokens

Export text element to document tokens format.

Parameters:

- doc
              (DoclingDocument)
          –
          
"DoclingDocument":
- new\_line
              (str, default:
                  '\n'
)
          –
          
str:  (Default value = "\n")
- xsize
              (int, default:
                  100
)
          –
          
int:  (Default value = 100)
- ysize
              (int, default:
                  100
)
          –
          
int:  (Default value = 100)
- add\_location
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_content
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_page\_index
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)

#### get\_image

Returns the image of this DocItem.

The function returns None if this DocItem has no valid provenance or
if a valid image of the page containing this DocItem is not available
in doc.

#### get\_location\_tokens

Get the location string for the BaseCell.

#### get\_ref

get\_ref.

### TableItem

Bases: FloatingItem

TableItem.

Methods:

- caption\_text
            –
            
Computes the caption as a single text.
- export\_to\_dataframe
            –
            
Export the table as a Pandas DataFrame.
- export\_to\_document\_tokens
            –
            
Export table to document tokens format.
- export\_to\_html
            –
            
Export the table as html.
- export\_to\_markdown
            –
            
Export the table as markdown.
- export\_to\_otsl
            –
            
Export the table as OTSL.
- get\_image
            –
            
Returns the image corresponding to this FloatingItem.
- get\_location\_tokens
            –
            
Get the location string for the BaseCell.
- get\_ref
            –
            
get\_ref.

Attributes:

- captions
              (List[RefItem])
          –
- children
              (List[RefItem])
          –
- data
              (TableData)
          –
- footnotes
              (List[RefItem])
          –
- image
              (Optional[ImageRef])
          –
- label
              (Literal[DOCUMENT\_INDEX, TABLE])
          –
- model\_config
          –
- parent
              (Optional[RefItem])
          –
- prov
              (List[ProvenanceItem])
          –
- references
              (List[RefItem])
          –
- self\_ref
              (str)
          –

#### captions

#### children

#### data

#### footnotes

#### image

#### label

#### model\_config

#### parent

#### prov

#### references

#### self\_ref

#### caption\_text

Computes the caption as a single text.

#### export\_to\_dataframe

Export the table as a Pandas DataFrame.

#### export\_to\_document\_tokens

Export table to document tokens format.

Parameters:

- doc
              (DoclingDocument)
          –
          
"DoclingDocument":
- new\_line
              (str, default:
                  '\n'
)
          –
          
str:  (Default value = "\n")
- xsize
              (int, default:
                  100
)
          –
          
int:  (Default value = 100)
- ysize
              (int, default:
                  100
)
          –
          
int:  (Default value = 100)
- add\_location
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_caption
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_content
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_cell\_location
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_cell\_label
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_cell\_text
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_page\_index
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)

#### export\_to\_html

Export the table as html.

#### export\_to\_markdown

Export the table as markdown.

#### export\_to\_otsl

Export the table as OTSL.

#### get\_image

Returns the image corresponding to this FloatingItem.

This function returns the PIL image from self.image if one is available.
Otherwise, it uses DocItem.get\_image to get an image of this FloatingItem.

In particular, when self.image is None, the function returns None if this
FloatingItem has no valid provenance or the doc does not contain a valid image
for the required page.

#### get\_location\_tokens

Get the location string for the BaseCell.

#### get\_ref

get\_ref.

### TableCell

Bases: BaseModel

TableCell.

Methods:

- from\_dict\_format
            –
            
from\_dict\_format.

Attributes:

- bbox
              (Optional[BoundingBox])
          –
- col\_span
              (int)
          –
- column\_header
              (bool)
          –
- end\_col\_offset\_idx
              (int)
          –
- end\_row\_offset\_idx
              (int)
          –
- row\_header
              (bool)
          –
- row\_section
              (bool)
          –
- row\_span
              (int)
          –
- start\_col\_offset\_idx
              (int)
          –
- start\_row\_offset\_idx
              (int)
          –
- text
              (str)
          –

#### bbox

#### col\_span

#### column\_header

#### end\_col\_offset\_idx

#### end\_row\_offset\_idx

#### row\_header

#### row\_section

#### row\_span

#### start\_col\_offset\_idx

#### start\_row\_offset\_idx

#### text

#### from\_dict\_format

from\_dict\_format.

### TableData

Bases: BaseModel

BaseTableData.

Attributes:

- grid
              (List[List[TableCell]])
          –
          
grid.
- num\_cols
              (int)
          –
- num\_rows
              (int)
          –
- table\_cells
              (List[TableCell])
          –

#### grid

grid.

#### num\_cols

#### num\_rows

#### table\_cells

### TableCellLabel

Bases: str, Enum

TableCellLabel.

Attributes:

- BODY
          –
- COLUMN\_HEADER
          –
- ROW\_HEADER
          –
- ROW\_SECTION
          –

#### BODY

#### COLUMN\_HEADER

#### ROW\_HEADER

#### ROW\_SECTION

### KeyValueItem

Bases: DocItem

KeyValueItem.

Methods:

- get\_image
            –
            
Returns the image of this DocItem.
- get\_location\_tokens
            –
            
Get the location string for the BaseCell.
- get\_ref
            –
            
get\_ref.

Attributes:

- children
              (List[RefItem])
          –
- label
              (Literal[KEY\_VALUE\_REGION])
          –
- model\_config
          –
- parent
              (Optional[RefItem])
          –
- prov
              (List[ProvenanceItem])
          –
- self\_ref
              (str)
          –

#### children

#### label

#### model\_config

#### parent

#### prov

#### self\_ref

#### get\_image

Returns the image of this DocItem.

The function returns None if this DocItem has no valid provenance or
if a valid image of the page containing this DocItem is not available
in doc.

#### get\_location\_tokens

Get the location string for the BaseCell.

#### get\_ref

get\_ref.

### SectionHeaderItem

Bases: TextItem

SectionItem.

Methods:

- export\_to\_document\_tokens
            –
            
Export text element to document tokens format.
- get\_image
            –
            
Returns the image of this DocItem.
- get\_location\_tokens
            –
            
Get the location string for the BaseCell.
- get\_ref
            –
            
get\_ref.

Attributes:

- children
              (List[RefItem])
          –
- label
              (Literal[SECTION\_HEADER])
          –
- level
              (LevelNumber)
          –
- model\_config
          –
- orig
              (str)
          –
- parent
              (Optional[RefItem])
          –
- prov
              (List[ProvenanceItem])
          –
- self\_ref
              (str)
          –
- text
              (str)
          –

#### children

#### label

#### level

#### model\_config

#### orig

#### parent

#### prov

#### self\_ref

#### text

#### export\_to\_document\_tokens

Export text element to document tokens format.

Parameters:

- doc
              (DoclingDocument)
          –
          
"DoclingDocument":
- new\_line
              (str, default:
                  '\n'
)
          –
          
str:  (Default value = "\n")
- xsize
              (int, default:
                  100
)
          –
          
int:  (Default value = 100)
- ysize
              (int, default:
                  100
)
          –
          
int:  (Default value = 100)
- add\_location
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_content
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_page\_index
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)

#### get\_image

Returns the image of this DocItem.

The function returns None if this DocItem has no valid provenance or
if a valid image of the page containing this DocItem is not available
in doc.

#### get\_location\_tokens

Get the location string for the BaseCell.

#### get\_ref

get\_ref.

### PictureItem

Bases: FloatingItem

PictureItem.

Methods:

- caption\_text
            –
            
Computes the caption as a single text.
- export\_to\_document\_tokens
            –
            
Export picture to document tokens format.
- export\_to\_html
            –
            
Export picture to HTML format.
- export\_to\_markdown
            –
            
Export picture to Markdown format.
- get\_image
            –
            
Returns the image corresponding to this FloatingItem.
- get\_location\_tokens
            –
            
Get the location string for the BaseCell.
- get\_ref
            –
            
get\_ref.

Attributes:

- annotations
              (List[PictureDataType])
          –
- captions
              (List[RefItem])
          –
- children
              (List[RefItem])
          –
- footnotes
              (List[RefItem])
          –
- image
              (Optional[ImageRef])
          –
- label
              (Literal[PICTURE])
          –
- model\_config
          –
- parent
              (Optional[RefItem])
          –
- prov
              (List[ProvenanceItem])
          –
- references
              (List[RefItem])
          –
- self\_ref
              (str)
          –

#### annotations

#### captions

#### children

#### footnotes

#### image

#### label

#### model\_config

#### parent

#### prov

#### references

#### self\_ref

#### caption\_text

Computes the caption as a single text.

#### export\_to\_document\_tokens

Export picture to document tokens format.

Parameters:

- doc
              (DoclingDocument)
          –
          
"DoclingDocument":
- new\_line
              (str, default:
                  '\n'
)
          –
          
str:  (Default value = "\n")
- xsize
              (int, default:
                  100
)
          –
          
int:  (Default value = 100)
- ysize
              (int, default:
                  100
)
          –
          
int:  (Default value = 100)
- add\_location
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_caption
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)
- add\_content
              (bool, default:
                  True
)
          –
          
bool:  (Default value = True)

#### export\_to\_html

Export picture to HTML format.

#### export\_to\_markdown

Export picture to Markdown format.

#### get\_image

Returns the image corresponding to this FloatingItem.

This function returns the PIL image from self.image if one is available.
Otherwise, it uses DocItem.get\_image to get an image of this FloatingItem.

In particular, when self.image is None, the function returns None if this
FloatingItem has no valid provenance or the doc does not contain a valid image
for the required page.

#### get\_location\_tokens

Get the location string for the BaseCell.

#### get\_ref

get\_ref.

### ImageRef

Bases: BaseModel

ImageRef.

Methods:

- from\_pil
            –
            
Construct ImageRef from a PIL Image.
- validate\_mimetype
            –
            
validate\_mimetype.

Attributes:

- dpi
              (int)
          –
- mimetype
              (str)
          –
- pil\_image
              (Optional[Image])
          –
          
Return the PIL Image.
- size
              (Size)
          –
- uri
              (Union[AnyUrl, Path])
          –

#### dpi

#### mimetype

#### pil\_image

Return the PIL Image.

#### size

#### uri

#### from\_pil

Construct ImageRef from a PIL Image.

#### validate\_mimetype

validate\_mimetype.

### PictureClassificationClass

Bases: BaseModel

PictureClassificationData.

Attributes:

- class\_name
              (str)
          –
- confidence
              (float)
          –

#### class\_name

#### confidence

### PictureClassificationData

Bases: BasePictureData

PictureClassificationData.

Attributes:

- kind
              (Literal['classification'])
          –
- predicted\_classes
              (List[PictureClassificationClass])
          –
- provenance
              (str)
          –

#### kind

#### predicted\_classes

#### provenance

### RefItem

Bases: BaseModel

RefItem.

Methods:

- get\_ref
            –
            
get\_ref.
- resolve
            –
            
resolve.

Attributes:

- cref
              (str)
          –
- model\_config
          –

#### cref

#### model\_config

#### get\_ref

get\_ref.

#### resolve

resolve.

### BoundingBox

Bases: BaseModel

BoundingBox.

Methods:

- area
            –
            
area.
- as\_tuple
            –
            
as\_tuple.
- from\_tuple
            –
            
from\_tuple.
- intersection\_area\_with
            –
            
intersection\_area\_with.
- normalized
            –
            
normalized.
- scaled
            –
            
scaled.
- to\_bottom\_left\_origin
            –
            
to\_bottom\_left\_origin.
- to\_top\_left\_origin
            –
            
to\_top\_left\_origin.

Attributes:

- b
              (float)
          –
- coord\_origin
              (CoordOrigin)
          –
- height
          –
          
height.
- l
              (float)
          –
- r
              (float)
          –
- t
              (float)
          –
- width
          –
          
width.

#### b

#### coord\_origin

#### height

height.

#### l

#### r

#### t

#### width

width.

#### area

area.

#### as\_tuple

as\_tuple.

#### from\_tuple

from\_tuple.

Parameters:

- coord
              (Tuple[float, ...])
          –
          
Tuple[float:
- ...]
          –
- origin
              (CoordOrigin)
          –
          
CoordOrigin:

#### intersection\_area\_with

intersection\_area\_with.

Parameters:

- other
              (BoundingBox)
          –
          
"BoundingBox":

#### normalized

normalized.

Parameters:

- page\_size
              (Size)
          –
          
Size:

#### scaled

scaled.

Parameters:

- scale
              (float)
          –
          
float:

#### to\_bottom\_left\_origin

to\_bottom\_left\_origin.

Parameters:

- page\_height
              (float)
          –

#### to\_top\_left\_origin

to\_top\_left\_origin.

Parameters:

- page\_height
              (float)
          –

### CoordOrigin

Bases: str, Enum

CoordOrigin.

Attributes:

- BOTTOMLEFT
          –
- TOPLEFT
          –

#### BOTTOMLEFT

#### TOPLEFT

### ImageRefMode

Bases: str, Enum

ImageRefMode.

Attributes:

- EMBEDDED
          –
- PLACEHOLDER
          –
- REFERENCED
          –

#### EMBEDDED

#### PLACEHOLDER

#### REFERENCED

### Size

Bases: BaseModel

Size.

Methods:

- as\_tuple
            –
            
as\_tuple.

Attributes:

- height
              (float)
          –
- width
              (float)
          –

#### height

#### width

#### as\_tuple

as\_tuple.