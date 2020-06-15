# enry ![Test](https://github.com/go-enry/enry/workflows/Test/badge.svg)

Programming language detector based on `go-enry/go-enry/v2` library. 
*go-enry*, started as a port to _Go_ of the original [linguist](https://github.com/github/linguist) _Ruby_ library, that has an improved *2x performance*.

*enry* CLI accepts similar flags (`--breakdown/--json`) and produce an output, similar to *linguist*:

```bash
$ enry
97.71%	Go
1.60%	C
0.31%	Shell
0.22%	Java
0.07%	Ruby
0.05%	Makefile
0.04%	Scala
0.01%	Gnuplot
```

Note that enry's CLI **_does not need an actual git repository to work_**, which is an intentional difference from linguist.

## Usage

By default, only the languages from Markdown and Programming groups are reported.

One can choose to report all the languages (including plain text, markup, templates, configuration scripts, etc) using
```
enry -all
```

For cases when subsequent lexing/parsing of the files is desired, one can keep only the programming languages by
```
enry -prog
```

Well-known vendoring, configuration, documentation paths as well as paths starting with dot are alwasy excluded from the final report.

## Install

The recommended way to install the `enry` command-line tool is to either
[download a release](https://github.com/go-enry/enry/releases) or run:

```
(cd "$(mktemp -d)" && go mod download && go get github.com/go-enry/enry)
```

## License

Apache License, Version 2.0. See [LICENSE](LICENSE)
