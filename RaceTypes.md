# The race model #

For finding the race model used in the sitron project, the following
race types should be supported.

## Race types ##

  * classic race
  * rogaining
  * scorelauf
  * SMIK (migrating control point scorelauf)
  * butterfly race routes (one control point can be punched more than once)
  * nest checks (classic + scorelauf)
  * relay races

## Supported features ##

Determined from all possible race types the following features should be supported:

  * linear race (control points must be punched in the given order)
  * scorelauf races (control points can be punched in any order, not all control points must be punched)
  * "catch all" races (control points can be punched in any order, all control points must be punched)
  * combination of previous races
  * bounded time control points (a control point punch is valid only if punched in a given time interval)

## The race model ##

According to this feature requests a model of the race is created. See the RaceModel site.
