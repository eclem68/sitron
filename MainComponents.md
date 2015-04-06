# The SItron components #

SItron consists of three components:
  * SItron application
  * SItron server
  * SItron print server

# SItron application #

SItron application is the main part of the system. It is interacting with the user. Any users interaction is done through SItron application. SItron application is
controlling the other components.

# SItron server #

SItron server is controlling the SI reading units. The server is communicating
with the application by a TCP based protocol (unix domain sockets may be also optionally supported).

Supported features:
  * the protocol is text-based
  * the protocol supports following operations:
    * sending the chip readouts in an abstract form
    * setting the readout mode (now two modes: read all data, read only chip id)
    * enabling/disabling the local ports
    * attaching/detaching an another SItron server
    * configuration of SI units (planed to be supported later)
  * autodetecting ports, but also manual port setting

# SItron print server #

There are two components needed for printing to work:
  * template processor
  * printing driver

The template processor takes the template and data and using TeX/LaTeX creates a portable document (i.e. pdf document). The template processor will be more or less
platform independent, but an installation of TeX/LaTeX must be provided. The templates and also data are provided by the SItron application.

The portable document will be sent to the printing driver, which will do all the
needed stuff to get the printed page from the printer. The driver is strongly platform dependent.

It is also necessary to look on the Internet if an another already existing project could be used as the print server.