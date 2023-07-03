# TFLint Ruleset with formatter
[![Build Status](https://github.com/thaim/tflint-ruleset-formatter/workflows/build/badge.svg?branch=main)](https://github.com/thaim/tflint-ruleset-formatter/actions)

TFLint ruleset plugin for Terraform Language with more format check.
This ruleset achieves more syntax checking that cannot be detected in 'terraform fmt'.

## Requirements

- TFLint v0.40+
- Go v1.20

## Installation

TODO: This template repository does not contain release binaries, so this installation will not work. Please rewrite for your repository. See the "Building the plugin" section to get this template ruleset working.

You can install the plugin with `tflint --init`. Declare a config in `.tflint.hcl` as follows:

```hcl
plugin "formatter" {
  enabled = true

  version = "0.1.0"
  source  = "github.com/thaim/tflint-ruleset-formatter"
}
```

## Rules

|Rule|Description|Severity|Enabled by default|
| --- | --- | --- | --- |
|[formatter_blank_line](docs/rules/formatter_blank_line.md)|ensures that there are no extra blank lines|WARNING|✔
|[formatter_eof](docs/rules/formatter_eof.md)|ensures that file end with new line|WARNING|✔
|[formatter_max_len](docs/rules/formatter_max_len.md)|ensures the limitation of code line length|WARNING|✔
|[formatter_trailing_comma](docs/rules/formatter_trailing_comma.md)|ensures that tuple element always end with comma|WARNING|✔

## Building the plugin

Clone the repository locally and run the following command:

```
$ make
```

You can easily install the built plugin with the following:

```
$ make install
```

You can run the built plugin like the following:

```
$ cat << EOS > .tflint.hcl
plugin "formatter" {
  enabled = true
}
EOS
$ tflint
```
