# 8cc C Compiler
8cc is a compiler for the C programming language. It's designed to support all C11 language features while keeping the code as small and simple as possible.

The compiler is capable of compiling itself, making its source code both an implementation of the C language and an example of what this compiler can compile.

8cc's source code is carefully written to be concise and easy to read, making it excellent study material for learning various compiler techniques. You may find the lexer, the preprocessor, and the parser useful for understanding how C source code is processed at each stage.

It's not an optimizing compiler. Generated code is typically 2x or more slower than GCC. I plan to implement a reasonable level of optimization in the future.

8cc currently supports x86-64 Linux only. I have no plans to make it portable until I fix all known miscompilations and implement an optimization pass. As of 2015, I'm using Ubuntu 14 as my development platform, but it should work on other x86-64 Linux distributions.

**Note:** Do not have high expectations for this compiler. If you attempt to compile a program other than the compiler itself, there's a good chance of encountering compile errors or miscompilations. This is essentially a one-man project, and I have spent only a few months of my spare time on it.

## Build

To build 8cc, simply run:

```sh
make
```

8cc comes with unit tests. You can run the tests by using:

```sh
make test
```

The following target builds 8cc three times to verify that the stage1 compiler can build stage2, and stage2 can build stage3. It then compares stage2 and stage3 binaries byte by byte to verify that we reach a fixed point:

```sh
make fulltest
```

## Author

**Rui Ueyama**
Email: rui314@gmail.com

## Links for C Compiler Development

In addition to popular books about compilers like the Dragon Book, I found the following books/documents very useful for developing a C compiler. Note that the standard draft versions are very close to the ratified versions and can be practically used as standard documents:

- [LCC: A Retargetable C Compiler: Design and Implementation](http://www.amazon.com/dp/0805316701), [GitHub Repository](https://github.com/drh/lcc)

- [TCC: Tiny C Compiler](http://bellard.org/tcc/), [Git Repository](http://repo.or.cz/w/tinycc.git/tree)

- [C99 standard final draft](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n1124.pdf)

- [C11 standard final draft](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n1570.pdf)

- [Dave Prosser's C Preprocessing Algorithm](http://www.spinellis.gr/blog/20060626/)

- [The x86-64 ABI](http://www.x86-64.org/documentation/abi.pdf)
