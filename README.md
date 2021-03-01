# fcd-kicad-lib

Flying Camp Design KiCad Library

## Usage

Unfortunately, KiCad 5 doesn't allow PCB footprint definitions to specify relative paths to 3D models.[^1]  To avoid hard coding any absolute paths to 3D models within the PCB footprint definitions, all paths to 3D models in this library are prefixed with a `Flying_Camp_Design:` alias.  However, KiCad 5 also doesn't support project specific library management for 3D models, so it's necessary to configure a global alias when using this library.[^2]

Open the "Configure Paths" preference window and add the following alias to the "3D Search Paths" section:

| Alias                | Path                                                         | Description                      |
| -------------------- | ------------------------------------------------------------ | -------------------------------- |
| `Flying_Camp_Design` | `${KIPRJMOD}/lib/github.com/FlyingCampDesign/fcd-kicad-lib/Flying_Camp_Design.3dshapes` | Flying Camp Design KiCad Library |

**IMPORTANT:** To ensure that the global alias above works across multiple projects and users, it is required that this library is located at `<your-kicad-project>/lib/github.com/FlyingCampDesign/fcd-kicad-lib`.

```
└── your-kicad-project
    ├── your-kicad-project.kicad_pcb
    ├── your-kicad-project.kicad_pro
    ├── your-kicad-project.kicad_prl
    ├── your-kicad-project.kicad_sch
    ├── fp-lib-table
    ├── lib
    │   └── github.com
    │       └── FlyingCampDesign
    │           └── fcd-kicad-lib
    └── sym-lib-table
```

[^1]: https://gitlab.com/kicad/code/kicad/issues/2073
[^2]: https://gitlab.com/kicad/code/kicad/issues/3792

