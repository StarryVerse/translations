GIMP-master
===========

Cleanup of GIMP-master in GNOME. 

Expected Procedure
------------------

* Pre-Import work: check for newer translations in gimp-2.8, and merge into
  master. Apply file format suggestions (e.g. plurals) as in zh_CN_l10n.
* Import into repo.
* Do cleanup job. This mainly consists of:
  * Punctation and formatting checks as described in zh_CN_l10n.
  * Make a table for terminology differences between common sence (Inkscape &
    Adobe(R) Photoshop(R) combined)
  * Apply the table by running search-and-replace.
* Continue translation.
* Submit translations. Use the table and search-and-replace to generate a
  *old-terminology* version in case someone prefers those creepy terms.
  * For those ones marked with *no* in *replace_back*, optionally create a
    *babble* version.
* Port translations to GIMP-2.8.
* Submit 2.8, and update aosc-os-abbs archives to use our own translations.
* Archive the branch status by running `git format-patch` and making a tarball
  for others' reference.

Terminology Difference
----------------------

| Orig         | Old | Ours | Replace back later? |
|--------------|-----|------|--------------|
|brush         |画笔 |笔刷   | yes|
|indexed images|索引图像|索引颜色图像|no|
|splash screen |溅射窗口|启动画面|no|
|context|环境|上下文|yes|
|Pointer|指针|TODO||
|Spike|穗|TODO||
|Dock (noun)|停靠|TODO||
|duplicate(n.)|复本|副本|no|
|Error Log|出错记录|错误日志|yes|
|Exposure|曝光量|曝光？|yes|
|Segment (Geometry)|段|线段|manual|
|LTR|左至右|LTR|manual|
|RTL|右至左|RTL|manual|


Notes
-----

1. Please use `--previous` for all `msgmerge` operations.