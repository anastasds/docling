# Pipeline options

Pipeline options allow to customize the execution of the models during the conversion pipeline.
This includes options for the OCR engines, the table model as well as enrichment options which
can be enabled with do\_xyz = True.

This is an automatic generated API reference of the all the pipeline options available in Docling.

## pipeline\_options

Classes:

- AcceleratorDevice
          –
          
Devices to run model inference
- AcceleratorOptions
          –
- EasyOcrOptions
          –
          
Options for the EasyOCR engine.
- OcrEngine
          –
          
Enum of valid OCR engines.
- OcrMacOptions
          –
          
Options for the Mac OCR engine.
- OcrOptions
          –
          
OCR options.
- PdfBackend
          –
          
Enum of valid PDF backends.
- PdfPipelineOptions
          –
          
Options for the PDF pipeline.
- PipelineOptions
          –
          
Base pipeline options.
- RapidOcrOptions
          –
          
Options for the RapidOCR engine.
- TableFormerMode
          –
          
Modes for the TableFormer model.
- TableStructureOptions
          –
          
Options for the table structure.
- TesseractCliOcrOptions
          –
          
Options for the TesseractCli engine.
- TesseractOcrOptions
          –
          
Options for the Tesseract engine.

### AcceleratorDevice

Bases: str, Enum

Devices to run model inference

Attributes:

- AUTO
          –
- CPU
          –
- CUDA
          –
- MPS
          –

#### AUTO

class-attribute
instance-attribute

#### CPU

class-attribute
instance-attribute

#### CUDA

class-attribute
instance-attribute

#### MPS

class-attribute
instance-attribute

### AcceleratorOptions

Bases: BaseSettings

Methods:

- check\_alternative\_envvars
            –
            
Set num\_threads from the "alternative" envvar OMP\_NUM\_THREADS.

Attributes:

- device
              (AcceleratorDevice)
          –
- model\_config
          –
- num\_threads
              (int)
          –

#### device

class-attribute
instance-attribute

#### model\_config

class-attribute
instance-attribute

#### num\_threads

class-attribute
instance-attribute

#### check\_alternative\_envvars

classmethod

Set num\_threads from the "alternative" envvar OMP\_NUM\_THREADS.
The alternative envvar is used only if it is valid and the regular envvar is not set.

Notice: The standard pydantic settings mechanism with parameter "aliases" does not provide
the same functionality. In case the alias envvar is set and the user tries to override the
parameter in settings initialization, Pydantic treats the parameter provided in init()
as an extra input instead of simply overwriting the evvar value for that parameter.

### EasyOcrOptions

Bases: OcrOptions

Options for the EasyOCR engine.

Attributes:

- bitmap\_area\_threshold
              (float)
          –
- confidence\_threshold
              (float)
          –
- download\_enabled
              (bool)
          –
- force\_full\_page\_ocr
              (bool)
          –
- kind
              (Literal['easyocr'])
          –
- lang
              (List[str])
          –
- model\_config
          –
- model\_storage\_directory
              (Optional[str])
          –
- recog\_network
              (Optional[str])
          –
- use\_gpu
              (Optional[bool])
          –

#### bitmap\_area\_threshold

class-attribute
instance-attribute

#### confidence\_threshold

class-attribute
instance-attribute

#### download\_enabled

class-attribute
instance-attribute

#### force\_full\_page\_ocr

class-attribute
instance-attribute

#### kind

class-attribute
instance-attribute

#### lang

class-attribute
instance-attribute

#### model\_config

class-attribute
instance-attribute

#### model\_storage\_directory

class-attribute
instance-attribute

#### recog\_network

class-attribute
instance-attribute

#### use\_gpu

class-attribute
instance-attribute

### OcrEngine

Bases: str, Enum

Enum of valid OCR engines.

Attributes:

- EASYOCR
          –
- OCRMAC
          –
- RAPIDOCR
          –
- TESSERACT
          –
- TESSERACT\_CLI
          –

#### EASYOCR

class-attribute
instance-attribute

#### OCRMAC

class-attribute
instance-attribute

#### RAPIDOCR

class-attribute
instance-attribute

#### TESSERACT

class-attribute
instance-attribute

#### TESSERACT\_CLI

class-attribute
instance-attribute

### OcrMacOptions

Bases: OcrOptions

Options for the Mac OCR engine.

Attributes:

- bitmap\_area\_threshold
              (float)
          –
- force\_full\_page\_ocr
              (bool)
          –
- framework
              (str)
          –
- kind
              (Literal['ocrmac'])
          –
- lang
              (List[str])
          –
- model\_config
          –
- recognition
              (str)
          –

#### bitmap\_area\_threshold

class-attribute
instance-attribute

#### force\_full\_page\_ocr

class-attribute
instance-attribute

#### framework

class-attribute
instance-attribute

#### kind

class-attribute
instance-attribute

#### lang

class-attribute
instance-attribute

#### model\_config

class-attribute
instance-attribute

#### recognition

class-attribute
instance-attribute

### OcrOptions

Bases: BaseModel

OCR options.

Attributes:

- bitmap\_area\_threshold
              (float)
          –
- force\_full\_page\_ocr
              (bool)
          –
- kind
              (str)
          –
- lang
              (List[str])
          –

#### bitmap\_area\_threshold

class-attribute
instance-attribute

#### force\_full\_page\_ocr

class-attribute
instance-attribute

#### kind

instance-attribute

#### lang

instance-attribute

### PdfBackend

Bases: str, Enum

Enum of valid PDF backends.

Attributes:

- DLPARSE\_V1
          –
- DLPARSE\_V2
          –
- PYPDFIUM2
          –

#### DLPARSE\_V1

class-attribute
instance-attribute

#### DLPARSE\_V2

class-attribute
instance-attribute

#### PYPDFIUM2

class-attribute
instance-attribute

### PdfPipelineOptions

Bases: PipelineOptions

Options for the PDF pipeline.

Attributes:

- accelerator\_options
              (AcceleratorOptions)
          –
- artifacts\_path
              (Optional[Union[Path, str]])
          –
- create\_legacy\_output
              (bool)
          –
- do\_code\_enrichment
              (bool)
          –
- do\_formula\_enrichment
              (bool)
          –
- do\_ocr
              (bool)
          –
- do\_picture\_classification
              (bool)
          –
- do\_table\_structure
              (bool)
          –
- document\_timeout
              (Optional[float])
          –
- generate\_page\_images
              (bool)
          –
- generate\_picture\_images
              (bool)
          –
- generate\_table\_images
              (bool)
          –
- images\_scale
              (float)
          –
- ocr\_options
              (Union[EasyOcrOptions, TesseractCliOcrOptions, TesseractOcrOptions, OcrMacOptions, RapidOcrOptions])
          –
- table\_structure\_options
              (TableStructureOptions)
          –

#### accelerator\_options

class-attribute
instance-attribute

#### artifacts\_path

class-attribute
instance-attribute

#### create\_legacy\_output

class-attribute
instance-attribute

#### do\_code\_enrichment

class-attribute
instance-attribute

#### do\_formula\_enrichment

class-attribute
instance-attribute

#### do\_ocr

class-attribute
instance-attribute

#### do\_picture\_classification

class-attribute
instance-attribute

#### do\_table\_structure

class-attribute
instance-attribute

#### document\_timeout

class-attribute
instance-attribute

#### generate\_page\_images

class-attribute
instance-attribute

#### generate\_picture\_images

class-attribute
instance-attribute

#### generate\_table\_images

class-attribute
instance-attribute

#### images\_scale

class-attribute
instance-attribute

#### ocr\_options

class-attribute
instance-attribute

#### table\_structure\_options

class-attribute
instance-attribute

### PipelineOptions

Bases: BaseModel

Base pipeline options.

Attributes:

- accelerator\_options
              (AcceleratorOptions)
          –
- create\_legacy\_output
              (bool)
          –
- document\_timeout
              (Optional[float])
          –

#### accelerator\_options

class-attribute
instance-attribute

#### create\_legacy\_output

class-attribute
instance-attribute

#### document\_timeout

class-attribute
instance-attribute

### RapidOcrOptions

Bases: OcrOptions

Options for the RapidOCR engine.

Attributes:

- bitmap\_area\_threshold
              (float)
          –
- cls\_model\_path
              (Optional[str])
          –
- det\_model\_path
              (Optional[str])
          –
- force\_full\_page\_ocr
              (bool)
          –
- kind
              (Literal['rapidocr'])
          –
- lang
              (List[str])
          –
- model\_config
          –
- print\_verbose
              (bool)
          –
- rec\_keys\_path
              (Optional[str])
          –
- rec\_model\_path
              (Optional[str])
          –
- text\_score
              (float)
          –
- use\_cls
              (Optional[bool])
          –
- use\_det
              (Optional[bool])
          –
- use\_rec
              (Optional[bool])
          –

#### bitmap\_area\_threshold

class-attribute
instance-attribute

#### cls\_model\_path

class-attribute
instance-attribute

#### det\_model\_path

class-attribute
instance-attribute

#### force\_full\_page\_ocr

class-attribute
instance-attribute

#### kind

class-attribute
instance-attribute

#### lang

class-attribute
instance-attribute

#### model\_config

class-attribute
instance-attribute

#### print\_verbose

class-attribute
instance-attribute

#### rec\_keys\_path

class-attribute
instance-attribute

#### rec\_model\_path

class-attribute
instance-attribute

#### text\_score

class-attribute
instance-attribute

#### use\_cls

class-attribute
instance-attribute

#### use\_det

class-attribute
instance-attribute

#### use\_rec

class-attribute
instance-attribute

### TableFormerMode

Bases: str, Enum

Modes for the TableFormer model.

Attributes:

- ACCURATE
          –
- FAST
          –

#### ACCURATE

class-attribute
instance-attribute

#### FAST

class-attribute
instance-attribute

### TableStructureOptions

Bases: BaseModel

Options for the table structure.

Attributes:

- do\_cell\_matching
              (bool)
          –
- mode
              (TableFormerMode)
          –

#### do\_cell\_matching

class-attribute
instance-attribute

#### mode

class-attribute
instance-attribute

### TesseractCliOcrOptions

Bases: OcrOptions

Options for the TesseractCli engine.

Attributes:

- bitmap\_area\_threshold
              (float)
          –
- force\_full\_page\_ocr
              (bool)
          –
- kind
              (Literal['tesseract'])
          –
- lang
              (List[str])
          –
- model\_config
          –
- path
              (Optional[str])
          –
- tesseract\_cmd
              (str)
          –

#### bitmap\_area\_threshold

class-attribute
instance-attribute

#### force\_full\_page\_ocr

class-attribute
instance-attribute

#### kind

class-attribute
instance-attribute

#### lang

class-attribute
instance-attribute

#### model\_config

class-attribute
instance-attribute

#### path

class-attribute
instance-attribute

#### tesseract\_cmd

class-attribute
instance-attribute

### TesseractOcrOptions

Bases: OcrOptions

Options for the Tesseract engine.

Attributes:

- bitmap\_area\_threshold
              (float)
          –
- force\_full\_page\_ocr
              (bool)
          –
- kind
              (Literal['tesserocr'])
          –
- lang
              (List[str])
          –
- model\_config
          –
- path
              (Optional[str])
          –

#### bitmap\_area\_threshold

class-attribute
instance-attribute

#### force\_full\_page\_ocr

class-attribute
instance-attribute

#### kind

class-attribute
instance-attribute

#### lang

class-attribute
instance-attribute

#### model\_config

class-attribute
instance-attribute

#### path

class-attribute
instance-attribute