# Internal Flash Structure and Emulated EEPROM Example on PSOC 63 MCU

## I. Flash Structure of PSOC 63 MCU

### Overview:
- PSOC 63 MCU implement dual core architecture with both core have shared access to memory. The MCU will access to flash memory through the code region in the address map. The address range for code region is 0x0000 0000 - 0x1FFF FFFF.
- Flash memory is divided into 3 main regions which include Supervisory Flash (SFlash), Auxiliary Flash (AUXFlash), Application Flash. Each region is used for specific purpose:
    + Application Flash stores code images and constant data. Therefore, this region have the largest space compare to the rest . User have read and program/erase access to this region but due to Erase Disturb mechanism, it is recommended to store frequently-updated data on another region.
    + Auxiliary Flash provides more storing space when Application Flash's space is not enough. This region is typically used for EEPROM emulation which is benefit for storing log data updated on daily basis.
    + Supervisory Flash is reserved for system use. It contain trim parameter, system configuration parameter, protection and security settings, boot code and other Infineon proprietary information. User can read data from this region but program or erase access is limited.
- A region comprised of sectors and each sector is subdivided into rows. Row's size is 512 bytes. The distribution of rows and sectors is illustrated with the following diagram:
    + SFlash and AUXFlash have 2 sectors with each sector consist of 64 rows. The size of a sector in SFLASH and AUXFlash annotated in parentheses is 32kB.
    + Application Flash have 4 sectors with each sector consist of 512 rows. The size of a sector in Application FLash is 256kB.

![ Flash's Internal Organization.](/Flash_Structure.png)

### Application Flash and API for accessing:

### Supervisory Flash and API for accessing:

### Auxiliary Flash and API for accessing:

## II. Emulated EEPROM Example:
