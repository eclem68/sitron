# The goals of the SItron project #

The main goal of the project is to create a free and open-source software for managing
orienteering competitions based on the SportIdent equipment.

# Requirements #

## Requirements from the user's point of view ##

  * The application should be multiplatform. At least Linux and Windows should be supported.
  * Support for many existing data formats should be provided.
  * Support many types of competitions. Adding a new custom competition type should be as easy as possible.
  * Printing support

## Design requirements ##

  * Frontend and backend of the application is splited.
  * The main frontend is a classical desktop window frontend. Also other frontends could be supported (CLI, Web based, etc.)
  * The functionality of reading out (and also abstracting) the data from SI chips is independent from the rest of the system and has a form of an TCP server (Unix domain sockets could also be supported). The reading server could also be used in other projects.
  * competition types are provided by a kind of plugins.

## Used technology ##

  * Main language is Python.
  * Frontend is created using the PyQt library.
  * Competition files are sqlite3 files. Also support for other databases could be provided.
  * Templates for printing made in TeX/LaTeX.