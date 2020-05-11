# DeterministicFileStoage
A proposed method of file compression and storage that relies on an standard set of incremental files

File paths are an effecient way to compress information and every file can be reconstructed with a collection of hexcode, therefore a program can utilise this in order to have highly space effecient file storage at the cost of much time and file space somewhere else. This is ideal for usage in a server because then multiple parties can point to the same hex chunks and simply back up their list of pointers/file_paths/keys onto something like paper or a relatively small USB drive, which can then reconstruct their desired files given access to the large sequential hexcode. This is ideal for integration with a secure scuttlebutt style gossip network so that bluetooth transfers can be done very quickly with strangers on the street but can still represent comparitively large meaningful payloads but offloading the processing into a time when someone goes home or to the city, wherever the sequential hexcode is stored. I'm sure there are other examples where the transition cost of incredibly high so that this is a good deal to make. 

Ideally, the filepath structure would be standardised so that not only could data be "uploaded" offline, but smaller scale versions can be done without something crazy like petabytes of home storage, albiet at less effecient levels. This would mean that some compressed files would only ever be uncompressable when compared to enterprise level servers, however, it will be done in such a way that the compression process can choose how big the chunk sizes will be so they can be bypassed completely if so desired.

The compressed file would be a bin file, though for now txt, that has the chunk size ( number of digits that it got divided into ) the file paths in those digits ( this can be shortened via yvfuencoder ) and the remainder, which will usually be a different chunk size than the rest.

Filepaths are not going to be more effecient than just writing out something like 4 digits of hexadecimal, therefore the remainder ( the portion of the hexdump at the end which does not fit perfectly into a given chunk size, when % != 0 ) will just be sent as plain text.

