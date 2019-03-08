# TexStep

A way to run steps from a text file or web page directly in a terminal.

## Installation with TexStep

Use texstep itself to install the tool by pointing at this very readme file!

```sh
bin/txs README.md install
```

It will automatically find and run the snippet from the *Manual Installation* section.

## Manual Installation

The following are commands for copying `txs`, the TexStep executable, and its supporting libraries, to an installed location.

```sh
#TXS:install require-root
#!/usr/bin/env bash

cp bin/txs /usr/local/bin/txs
cp -r lib/txs /usr/local/lib/txs

#TXS/install
```

## What does TexStep do ?

`txs` detects `#TXS:<STEPNAME>` and `#TXS/<STEPNAME>` as boundaries for a name to execute with `txs <FILE> <STEPNAME> ...`

In this way, snippets from within documentation can be run directly.

You can also run steps from webpages themselves:

```sh
txs http://example.com/install.html step1
```

### Data extraction

With the `-e` option, rather than executing the found step, it is output to the console:

```sh
txs -e README.md data-example
```

Which will simply print the section here:

```json
#TXS:data-example
{
    "data" : "example embedded json data"
}
#TXS/data-example
```
