# Internal Flash Structure and Emulated EEPROM Example

## Flash Structure
- Flash is divided into 3 main regions which include Supervisory Flash (SFlash), Auxiliary Flash (AUXFlash), Application Flash. Each region is used for specific purpose.
- Application Flash stores code images and constant data. Therefor, this region have the largest space compare to the rest . User have read and write access to this region but due to Erase Disturb mechanism, it is recommended to store frequently-updated data on another region.
- Auxiliary Flash provides more storing space when Application Flash's space is not enough. This region is typically used for EEPROM emulation which is benefit for storing log data updated on daily basis.
- Supervisory Flash is reserved for system use. It contain trim parameter, system configuration parameter, protection and security settings, boot code and other Infineon proprietary information. User can read data from this region but program or erase access is limited.
- Each region comprised of sectors and each sector is subdivided into rows. Row size is 512 bytes. The distribution of rows and sectors is illustrated with the following table:


  
