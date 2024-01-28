# Anvil
Anvil is a single-file build tool for C, inspired by tsoding's [nobuild](https://github.com/tsoding/nobuild).

Anvil is a build tool that's small enough to be **included in your project as source code**.
Just modify Anvil's settings to suit your project, then compile and run it:
```sh
$ cc ./anvil.c -o anvil
$ ./anvil
```
and viola! You can try this out on the example project included!

# Usage
Anvil needs this information about your project.

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

Anvil searches all the folders in `source_dirs` for `.c` files, compiles them to
`build_dir`, links them all, and creates an executable in `output_dir`.

# What's the catch?
As of right now, Anvil is still in its pretty early stages, and it's limited in what it can do. For projects with more complex build steps or other languages, 
I'd recommend using more flexible build tools.

As always, pull requests are welcome! I'd love to improve this as much as I can while sticking to the original goal of a small, single-file tool.
