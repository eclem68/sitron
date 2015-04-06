# The race model #

## Physical and logical control points ##

The term control point can have two different meanings:

  * **the physical control point** - is the physically existing control point hardware. It will have two attributes:
    * the internal code
    * optional label (can be equal to the internal code, but in general it can by _any_ string
  * **the logical control point** - it is the obligatory to punch a given physical control point somewhere in the race. So every logical control point has associated exactly one physical control point. But in general one physical control point can be associated with more logical control points.


## Races and runs ##

Every race has one ore more runs. Every run corresponds to one run of a competitor/team/team member. So every run has a separate map. For the
structure of runs see the RunModel.

## Evaluating of races ##

The evaluation of a race follows the structure of the race, which is not yet ready. But as a substep, every run of the race must be evaluated. This process is described in RunEvaluation.