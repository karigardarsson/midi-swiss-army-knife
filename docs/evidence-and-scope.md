# Evidence and scope

## Evidence policy

Claims in this repository are intentionally limited by their evidence:

- **HARDWARE-PROVEN:** observed on the relevant physical configuration.
- **IMPLEMENTED / SOURCE-LEVEL:** present in source; not a claim of physical runtime behavior.
- **TESTED:** demonstrated by a test or fixture; not hardware proof.
- **EXPERIMENTAL:** an active technical or musical experiment awaiting fuller validation.
- **RESEARCH / NOT YET PRODUCTIZED:** informs future work but is not a released feature.

This distinction is especially important in USB-host, MIDI/SysEx, display, and embedded-routing work, where a build can be healthy while a physical device behavior remains unproven.

## Included

- High-level engineering descriptions.
- Original high-level diagrams.
- One early CAD enclosure image, labelled as such.
- Public-facing discussion of transaction safety, state separation, and musical exploration.

## Excluded

- Complete firmware source and private history.
- Binaries and firmware images.
- Raw SysEx, MIDI captures, payloads, decoded object layouts, byte maps, and ownership tables.
- Device backups and serial/device/account identifiers.
- Private research notes, full experimental corpus, and book-derived source material.
- Local filesystem paths, secrets, tokens, and unrelated projects.

## Syntakt boundary

Syntakt is referenced only as adjacent research and a source of architectural lessons. It is not claimed as a peer of the Digitakt II integration, and the showcase does not imply firmware modification, universal control coverage, or full protocol support.

## License

**NO SOFTWARE LICENSE ADDED.**

The repository is a public showcase and does not distribute the complete firmware source. Any future decision about documentation, image, or code licensing should be made deliberately with the intended reuse rights in mind.
