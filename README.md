# Dart Code Coverage Generator
[![Build Status](https://travis-ci.org/ekweible/dart_codecov_generator.svg?branch=master)](https://travis-ci.org/ekweible/dart_codecov_generator) [![codecov.io](http://codecov.io/github/ekweible/dart_codecov_generator/coverage.svg?branch=master)](http://codecov.io/github/ekweible/dart_codecov_generator?branch=master)

> Generate code coverage for Dart projects. Output can be [lcov](http://ltp.sourceforge.net/coverage/lcov.php) format or an HTML report.

This project includes a `dart_codecov_generator` executable that runs one or many test files and uses the `coverage` package to collect coverage for each file and format the coverage into the desired output format.


## Prerequisites
Depends on the following utilities:

- genhtml (`brew install lcov` on a mac)
- lsof (standard unix utility)


## Installation

Add this to your package's pubspec.yaml file:
```yaml
dependencies:
  coverage:
    git:
      url: git@github.com:johnpryan/coverage.git
      ref: master
  dart_codecov_generator:
    git:
      url: git@github.com:johnpryan/dart_codecov_generator.git
      ref: 0.1.0
```

Install:
```
pub get
```


## Usage
```
pub run dart_codecov_generator
```


## Configuration
By default, this tool runs every test file in the `test/` directory. You can explicitly specify the directories or files like so:
```
generate_coverage test/my_test.dart
```

### Options
- `--report-on`: Which directories or files to report coverage on. For example, `--report-on=lib/`.

### Flags
- `--html`: Whether or not to generate the HTML report. Defaults to true.
- `--lcov`: Whether or not to generate the .lcov file. Defaults to true.
- `--verbose`: Toggle verbose output to stdout.
