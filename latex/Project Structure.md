---
example: 
command: table-floats/
---

Writing everything in one file reduces readability, increases compile time, and makes debugging more difficult. Therefore a logical project structure is highly recommended.

- **`main.tex`** for project structure which inputs all files
- **`setup/`** for the preamble, configuration, layout and formatting
    - **`packages.tex`** for used packages
    - **`layout.tex`** for formatting styles, package configuration
    - **`definitions.tex`** for new commands, environments, etc.
- **`chapters/`** for text chapters
- **`resources/`** for images, table values, sourcecode files, attachments
- **`bibliographies/`** for sources and external references
- **`table-floats/`** for floating object definitions of tables
- **`figure-floats/`** for the floating object definitions of images and graphics
- **`listing-floats/`** for the floating object definitions of listings
- **`sty/`** for self-written packages