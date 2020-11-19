# SF100Linux
Linux software for Dediprog SF100 and SF600 SPI flash programmers.

## Building
To compile the project, first install required dependencies:
  - libusb 0.1 (libusb-compat)

Change to the directory where the sources are located and build using make:
```bash
$ cd SF100Linux
$ make
```

The resulting binary `dpcmd` is located in the root of the source tree.

## Usage
The most basic usage is writing a whole image file to a flash chip:
```bash
$ dpcmd --auto image.bin --verify
```

The `--auto` flag ensures that the current chip contents are read out, compared
to the data being written and only the regions that differ are written to the
chip. In combination with `--verify` verifies written data integrity.

For more advanced usage see `dpcmd --help`.
