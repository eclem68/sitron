# Use cases #

  * competition setup
  * registration of competitors
  * chip readout + correction
  * export of results & statistics

## competition setup ##

In the competition setup the following must be done:

  * set the competition type and set the parameters of a competition (number of team members, time of race, etc.) Each competition type provides different competition parameters.
  * set the general competition parameters (start time, etc.)
  * control point setup:
    * enter all control point codes
    * setup the relations between control points (i.e. the order of control points, but in general the relations could be more complex, for example when first 5 control points can be punched in any order, but other control points have to be punched in the exactly given order)
    * setup of the SI control point units **(not present in the first version of SItron)**

## registration of competitors ##

At the registration office all these operations must be supported:

  * Import data from another source (typically done before the registration office starts)
  * setings race
  * Creating a new competitor and enter all its needed data.
  * Correcting data of an already registered competitor
  * import competitor (ČSOS)
  * import categorys
  * import race (OCAD)
  * lottery start lists

When registering or correcting a competitor, the SI chip number can be also entered through the SI chip reader.

## chip readout + correction ##

This is the main use case. This case must be well-designed, since many competitors must be processed in a short time period. For every competitor these tasks must happen:

  * reading out the SI chip
  * Printing time (es) of one competitor (press leaves) (tisk lístečků)
  * Possibly correct values from the chips. There are three kinds of values:
    * chip related values
    * person related values (if the competition type allows more chips assigned to one person)
    * team related values (if one team contains more than one person)
  * Print the team/personal statistics

## export of results & statistics ##

At the end, the possibility of preparing a scorecard and optionally other statistical data must be available.