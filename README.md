# ![LibPacSet Logo](./assets/title/title_4x.png)

## Overview

*LibPacSet* is a shared library that contains tools for managing ROM files in *Pac-Man*. These tools include creating virtual ROM sets, as well as virtual ROMs. Additionally, it can save and load data by reading and writing the ROM files from your copy of *Pac-Man*, making it the go-to tool for ROM-hacking the game. It also contains debugging tools, like printing information about the virtual ROMs and the ROM sets onto the terminal.

## Functions

### PacSet

* `void pac_set_init(pac_set_t* set, const char* path)`
* `pac_set_t* pac_set_create(const char* path)`
* `void pac_set_clear(pac_set_t* set)`
* `void pac_set_destroy(pac_set_t* set)`
* `void pac_set_copy(const pac_set_t* set_source, pac_set_t* set_destination)`
* `pac_set_t* pac_set_duplicate(const pac_set_t* set_source)`
* `const char* pac_set_get_path(const pac_set_t* set)`
* `size_t pac_set_get_size(const pac_set_t* set)`
* `pac_rom_t* const* pac_set_get_roms(const pac_set_t* set)`
* `const pac_rom_t* pac_set_get_rom(const pac_set_t* set, const size_t index)`
* `int pac_set_append_rom(pac_set_t* set, pac_rom_t* rom)`

### PacRom

* `void pac_rom_init(pac_rom_t* rom, const char* name)`
* `pac_rom_t* pac_rom_create(const char* name)`
* `void pac_rom_clear(pac_rom_t* rom)`
* `void pac_rom_destroy(pac_rom_t* rom)`
* `void pac_rom_copy(const pac_rom_t* rom_source, pac_rom_t* rom_destination)`
* `pac_rom_t* pac_rom_duplicate(const pac_rom_t* rom_source)`
* `const char* pac_rom_get_name(const pac_rom_t* rom)`
* `size_t pac_rom_get_size(const pac_rom_t* rom)`
* `const uint8_t* pac_rom_get_data(const pac_rom_t* rom)`

### PacIO

* `uint8_t pac_rom_read(pac_rom_t* rom, const off_t offset)`
* `void pac_rom_readn(pac_rom_t* rom, const off_t offset, const size_t amount, uint8_t* destination)`
* `int pac_rom_load(pac_rom_t* rom)`
* `int pac_rom_unload(pac_rom_t* rom)`
* `int pac_rom_save(const pac_rom_t* rom)`
* `int pac_set_scan_directory(pac_set_t* set)`
* `char* pac_path_generate(const char* path)`
* `void pac_path_clear(char* path)`

### PacSort

* `int pac_set_sort(pac_set_t* set)`
* `void pac_rom_swap(pac_rom_t** rom_a, pac_rom_t** rom_b)`
* `int pac_rom_compare(pac_rom_t* rom_a, pac_rom_t* rom_b)`
* `int pac_set_find_lowest_rom(const pac_set_t* set, const off_t offset)`

### PacPrint

* `void pac_set_print(const pac_set_t* set)`
* `void pac_set_printp(const pac_set_t* set)`
* `void pac_rom_print(const pac_rom_t* rom)`
* `void pac_rom_printd(const pac_rom_t* rom)`

### PacLimits

* `const uint8_t get_pac_name_max(void)`
* `const uint8_t get_pac_path_max(void)`
* `const uint8_t get_pac_roms_max(void)`

### PacError

* `void pac_info(const char* function_name, const char* message)`
* `void pac_warn(const char* function_name, const char* message)`
* `void pac_error(const char* function_name, const char* message)`

## Copyright Disclaimer

This is not an official product by Bandai Namco. *Pac-Man* is owned by Bandai Namco, and *LibPacSet* is created by GarlicDude. Moreover, *LibPacSet* does not distribute any ROMs, code, or assets related to *Pac-Man*.

The logo and title for *LibPacSet* uses the Press Start 2P text font. Press Start 2P is owned by CodeMan38.
