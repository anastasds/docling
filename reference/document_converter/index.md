# Document converter

This is an automatic generated API reference of the main components of Docling.

## document\_converter

Classes:

- DocumentConverter
          –
- ConversionResult
          –
- ConversionStatus
          –
- FormatOption
          –
- InputFormat
          –
          
A document format supported by document backend parsers.
- PdfFormatOption
          –
- ImageFormatOption
          –
- StandardPdfPipeline
          –
- WordFormatOption
          –
- PowerpointFormatOption
          –
- MarkdownFormatOption
          –
- AsciiDocFormatOption
          –
- HTMLFormatOption
          –
- SimplePipeline
          –
          
SimpleModelPipeline.

### DocumentConverter

Methods:

- convert
            –
- convert\_all
            –
- initialize\_pipeline
            –
            
Initialize the conversion pipeline for the selected format.

Attributes:

- allowed\_formats
          –
- format\_to\_options
          –
- initialized\_pipelines
              (Dict[Type[BasePipeline], BasePipeline])
          –

#### allowed\_formats

instance-attribute

#### format\_to\_options

instance-attribute

#### initialized\_pipelines

instance-attribute

#### convert

#### convert\_all

#### initialize\_pipeline

Initialize the conversion pipeline for the selected format.

### ConversionResult

Bases: BaseModel

Attributes:

- assembled
              (AssembledUnit)
          –
- document
              (DoclingDocument)
          –
- errors
              (List[ErrorItem])
          –
- input
              (InputDocument)
          –
- legacy\_document
          –
- pages
              (List[Page])
          –
- status
              (ConversionStatus)
          –
- timings
              (Dict[str, ProfilingItem])
          –

#### assembled

class-attribute
instance-attribute

#### document

class-attribute
instance-attribute

#### errors

class-attribute
instance-attribute

#### input

instance-attribute

#### legacy\_document

property

#### pages

class-attribute
instance-attribute

#### status

class-attribute
instance-attribute

#### timings

class-attribute
instance-attribute

### ConversionStatus

Bases: str, Enum

Attributes:

- FAILURE
          –
- PARTIAL\_SUCCESS
          –
- PENDING
          –
- SKIPPED
          –
- STARTED
          –
- SUCCESS
          –

#### FAILURE

class-attribute
instance-attribute

#### PARTIAL\_SUCCESS

class-attribute
instance-attribute

#### PENDING

class-attribute
instance-attribute

#### SKIPPED

class-attribute
instance-attribute

#### STARTED

class-attribute
instance-attribute

#### SUCCESS

class-attribute
instance-attribute

### FormatOption

Bases: BaseModel

Methods:

- set\_optional\_field\_default
            –

Attributes:

- backend
              (Type[AbstractDocumentBackend])
          –
- model\_config
          –
- pipeline\_cls
              (Type[BasePipeline])
          –
- pipeline\_options
              (Optional[PipelineOptions])
          –

#### backend

instance-attribute

#### model\_config

class-attribute
instance-attribute

#### pipeline\_cls

instance-attribute

#### pipeline\_options

class-attribute
instance-attribute

#### set\_optional\_field\_default

### InputFormat

Bases: str, Enum

A document format supported by document backend parsers.

Attributes:

- ASCIIDOC
          –
- DOCX
          –
- HTML
          –
- IMAGE
          –
- JSON\_DOCLING
          –
- MD
          –
- PDF
          –
- PPTX
          –
- XLSX
          –
- XML\_PUBMED
          –
- XML\_USPTO
          –

#### ASCIIDOC

class-attribute
instance-attribute

#### DOCX

class-attribute
instance-attribute

#### HTML

class-attribute
instance-attribute

#### IMAGE

class-attribute
instance-attribute

#### JSON\_DOCLING

class-attribute
instance-attribute

#### MD

class-attribute
instance-attribute

#### PDF

class-attribute
instance-attribute

#### PPTX

class-attribute
instance-attribute

#### XLSX

class-attribute
instance-attribute

#### XML\_PUBMED

class-attribute
instance-attribute

#### XML\_USPTO

class-attribute
instance-attribute

### PdfFormatOption

Bases: FormatOption

Methods:

- set\_optional\_field\_default
            –

Attributes:

- backend
              (Type[AbstractDocumentBackend])
          –
- model\_config
          –
- pipeline\_cls
              (Type)
          –
- pipeline\_options
              (Optional[PipelineOptions])
          –

#### backend

class-attribute
instance-attribute

#### model\_config

class-attribute
instance-attribute

#### pipeline\_cls

class-attribute
instance-attribute

#### pipeline\_options

class-attribute
instance-attribute

#### set\_optional\_field\_default

### ImageFormatOption

Bases: FormatOption

Methods:

- set\_optional\_field\_default
            –

Attributes:

- backend
              (Type[AbstractDocumentBackend])
          –
- model\_config
          –
- pipeline\_cls
              (Type)
          –
- pipeline\_options
              (Optional[PipelineOptions])
          –

#### backend

class-attribute
instance-attribute

#### model\_config

class-attribute
instance-attribute

#### pipeline\_cls

class-attribute
instance-attribute

#### pipeline\_options

class-attribute
instance-attribute

#### set\_optional\_field\_default

### StandardPdfPipeline

Bases: PaginatedPipeline

Methods:

- download\_models\_hf
            –
- execute
            –
- get\_default\_options
            –
- get\_ocr\_model
            –
- initialize\_page
            –
- is\_backend\_supported
            –

Attributes:

- artifacts\_path
          –
- build\_pipe
          –
- enrichment\_pipe
          –
- glm\_model
          –
- keep\_backend
          –
- keep\_images
          –
- pipeline\_options
              (PdfPipelineOptions)
          –

#### artifacts\_path

instance-attribute

#### build\_pipe

instance-attribute

#### enrichment\_pipe

instance-attribute

#### glm\_model

instance-attribute

#### keep\_backend

instance-attribute

#### keep\_images

instance-attribute

#### pipeline\_options

instance-attribute

#### download\_models\_hf

staticmethod

#### execute

#### get\_default\_options

classmethod

#### get\_ocr\_model

#### initialize\_page

#### is\_backend\_supported

classmethod

### WordFormatOption

Bases: FormatOption

Methods:

- set\_optional\_field\_default
            –

Attributes:

- backend
              (Type[AbstractDocumentBackend])
          –
- model\_config
          –
- pipeline\_cls
              (Type)
          –
- pipeline\_options
              (Optional[PipelineOptions])
          –

#### backend

class-attribute
instance-attribute

#### model\_config

class-attribute
instance-attribute

#### pipeline\_cls

class-attribute
instance-attribute

#### pipeline\_options

class-attribute
instance-attribute

#### set\_optional\_field\_default

### PowerpointFormatOption

Bases: FormatOption

Methods:

- set\_optional\_field\_default
            –

Attributes:

- backend
              (Type[AbstractDocumentBackend])
          –
- model\_config
          –
- pipeline\_cls
              (Type)
          –
- pipeline\_options
              (Optional[PipelineOptions])
          –

#### backend

class-attribute
instance-attribute

#### model\_config

class-attribute
instance-attribute

#### pipeline\_cls

class-attribute
instance-attribute

#### pipeline\_options

class-attribute
instance-attribute

#### set\_optional\_field\_default

### MarkdownFormatOption

Bases: FormatOption

Methods:

- set\_optional\_field\_default
            –

Attributes:

- backend
              (Type[AbstractDocumentBackend])
          –
- model\_config
          –
- pipeline\_cls
              (Type)
          –
- pipeline\_options
              (Optional[PipelineOptions])
          –

#### backend

class-attribute
instance-attribute

#### model\_config

class-attribute
instance-attribute

#### pipeline\_cls

class-attribute
instance-attribute

#### pipeline\_options

class-attribute
instance-attribute

#### set\_optional\_field\_default

### AsciiDocFormatOption

Bases: FormatOption

Methods:

- set\_optional\_field\_default
            –

Attributes:

- backend
              (Type[AbstractDocumentBackend])
          –
- model\_config
          –
- pipeline\_cls
              (Type)
          –
- pipeline\_options
              (Optional[PipelineOptions])
          –

#### backend

class-attribute
instance-attribute

#### model\_config

class-attribute
instance-attribute

#### pipeline\_cls

class-attribute
instance-attribute

#### pipeline\_options

class-attribute
instance-attribute

#### set\_optional\_field\_default

### HTMLFormatOption

Bases: FormatOption

Methods:

- set\_optional\_field\_default
            –

Attributes:

- backend
              (Type[AbstractDocumentBackend])
          –
- model\_config
          –
- pipeline\_cls
              (Type)
          –
- pipeline\_options
              (Optional[PipelineOptions])
          –

#### backend

class-attribute
instance-attribute

#### model\_config

class-attribute
instance-attribute

#### pipeline\_cls

class-attribute
instance-attribute

#### pipeline\_options

class-attribute
instance-attribute

#### set\_optional\_field\_default

### SimplePipeline

Bases: BasePipeline

SimpleModelPipeline.

This class is used at the moment for formats / backends
which produce straight DoclingDocument output.

Methods:

- execute
            –
- get\_default\_options
            –
- is\_backend\_supported
            –

Attributes:

- build\_pipe
              (List[Callable])
          –
- enrichment\_pipe
              (List[GenericEnrichmentModel[Any]])
          –
- keep\_images
          –
- pipeline\_options
          –

#### build\_pipe

instance-attribute

#### enrichment\_pipe

instance-attribute

#### keep\_images

instance-attribute

#### pipeline\_options

instance-attribute

#### execute

#### get\_default\_options

classmethod

#### is\_backend\_supported

classmethod