# hephaestus
Hephaestus is a single-file build tool for multi-file C projects, 
inspired by tsoding's [nobuild](https://github.com/tsoding/nobuild).

All you need to do is copy `hephaestus.c` into your project and quickly configure it.

From now on, all you need to do to build your project is
```sh
$ cc ./hephaestus.c -o heph
$ ./heph
```
and viola! Feel free to try this out on the example project included!

# how it works

Hephaestus offers these configuration options:

```c
char* project_name  = "";   //final executable name 
char* cc            = "";   // c compiler / linker to use
char* flags         = "";   // c compiler flags
char* source_dirs[] = {""}; // source code folders
char* include_dir   = "";   // optional c include folder
char* build_dir     = "";   // folder for intermediate .o files
char* output_dir    = "";   // folder to drop the final executable in
char* link_flags    = "";   // extra linker flags
int transparency_mode = 0;  // if not zero, print the commands instead of nice messages
```

Hephaestus searches all the folders in `source_dirs` for `.c` files, compiles them to
`build_dir`, links them all, and creates an executable in `output_dir`.
