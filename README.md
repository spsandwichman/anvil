# hephaestus
Hephaestus is a single-file build tool for multi-file C projects, 
inspired by tsoding's [nobuild](https://github.com/tsoding/nobuild).

All you need to do is copy `hephaestus.c` into your project folder and configure it.

From now on, all you need to do to build your project is
```sh
$ cc ./hephaestus.c -o heph
$ ./heph
```
and viola! Feel free to try this out on the example project included!

# how it works

To use Hephaestus, you have to provide it with this information:

```c
char* project_name  = "";   // final executable name 
char* cc            = "";   // c compiler / linker to use
char* source_dirs[] = {""}; // source code folders
char* build_dir     = "";   // folder for intermediate .o files
char* output_dir    = "";   // (optional, defaults to the main folder) folder to drop the final executable in
char* flags         = "";   // (optional) c compiler flags
char* include_dir   = "";   // (optional) c include path
char* link_flags    = "";   // (optional) linker flags
int transparency_mode = 0;  // (optional) if not zero, print the executed commands instead of nice messages
```

Hephaestus searches all the folders in `source_dirs` for `.c` files, compiles them to
`build_dir`, links them all, and creates an executable in `output_dir`.
