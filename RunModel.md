# The model of runs #

## The tree of the run ##

Every run will be modelled by a rooted tree with these properties:
  * every node has an _ordered_ list of its successors
  * every node has its type and possible other attributes depending on the type
  * all leaves have the type of logical control point, no other nodes are logical control points
  * each node of the tree can be understood as a subrun, the subrun corresponding to the root is the whole run
  * the types of other nodes are the following:
    * **linear run** - the run is compleeted if all its subruns are compleeted and compleeted in the given order
    * **scorelauf run** - the run is compleeted every time, but the score for this run is calculated from the score of its compleeted subruns
    * **catch-all run** - the run is compleeted if all its subruns are compleeted, but the order of completion of the subruns is not important
    * **logical control point** - this run is completed if the corresponding physical control point is punched

Note: The scorelauf run and catch-all run can be modeled with the same type only with different attributes set.

## The node attributes ##

Each node has some attributes. In general there are type-dependend, but some of them are common to all node types
  * **common attributes**
    * score for completing the subrun (if the race is time-based, the score may be  redundant)
    * validity period (when evaluating the run, a time of completion will be assigned - the run is seen as completed only if it is completed in the validity  period
    * bad-punch flag - determines what to do, if there is a bad punching in the run - if not set, bad punching is ignored, if set, bad punching implies the run is not compleeted. What does it mean a bad punch is type dependent
  * **scorelauf/catch-all attributes**
    * catch flag - this is a tri-state flag (states are 0, 1, 2). If set to 0, it the run is completed every time. If set to 1, it is completed if at least one subrun is completed. If set to 2, all subruns must be completed to complete the run.
    * bad-punch flag meaning - the run is bad-punched if one of its subruns is punched (a subrun is punched if at least one of its leaves is punched) more than once
  * **linear run attributes**
    * bad-punch meaning - the run is bad-punched if one of its subruns is punched more than once
  * **logical control point attributes**
    * reference to the corresponding physical control point
    * logical label (i.e. the label in the map)
    * bad-punch meaning - bad-punching has no sense for logical control points

## Models of typical runs ##
  * **classical run** - The root of the tree is a _linear run_ and all its successors are _logical control points_. Score and validity periods are not set, bad-punch flag is set on the root.
  * **rogaining** - The root of the tree is a _scorelauf_ and all its successors are _logical control points_. Score of all leaves corresponds to the score of the control points. Validity periods are not set, bad-punch flag is not set.,the catch flag is set to 0 or 1.
  * **SMIK run** - The root of the tree is a _scorelauf_ with catch flag set to 0. All successors of the root are _scorelaufs_ witch catch flag set to 1. The successors of the root's successors are leaves. The score of all leaves is 0, the score of the root's successors are the control point scores. The validity period of leaves is set according to the timetable, the validity periods of non-leaves is not set.

![http://wiki.sitron.googlecode.com/git/images/run-trees.png](http://wiki.sitron.googlecode.com/git/images/run-trees.png)