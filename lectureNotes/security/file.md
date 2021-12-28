2021-12-24
林晓东 溯源取证

## file carving
### header-footer carving
footer and header
stored contiguously on disk
header-footer carving
tools: foremost scalpel

### bifragmented files
file validation check
* CRC, checksum, on zip and micro-office 
bifragment gap carving (BGC)
gap size and $e_1$
### metadata carving
search for some specific data, such as timestamp, and so on
### deduplicated file system forensic analysis
inline deduplication and post-processing deduplication
rehydrating the file system volume, change the disk content! bad!
### Challenges
data security and confidentiality 
encrypted data recovery
recover damaged files or deleted partially overwritten files
