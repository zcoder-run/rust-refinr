# Content Map Types

This module defines the in-memory content map and the serialized document used to store generated file and directory guidance.

## Map entries

[`ContentMap`] groups file and folder entries. Its `file_map` keys are source-relative file paths, and its `folder_map` keys are source-relative directory paths.

[`FileMapEntry`] stores a file summary, usage guidance, public type and function names, and searchable topics. It also carries engine-owned provenance: `hash` identifies the source content the entry was generated from, and `mtime` records the source modification time in Unix microseconds when available. [`FolderMapEntry`] stores a directory summary, usage guidance, and searchable topics.

## Serialized documents

[`ContentMapDocument`] carries the file and folder maps together with generation provenance: the schema version, model name, prompt version, and generation timestamp. [`ContentMapDocument::new`] sets the schema version to `2`. [`ContentMapDocument::from_content_map`] transfers both maps from an in-memory [`ContentMap`].
