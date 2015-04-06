# Evaluation of runs #

This page describes how runs are evaluated. The result of run evaluation
is the triple of:
  * score
  * time
  * completion (or disqualification) flag

When comparing these triplets, an _fixed_ lexikographical ordering is used. First the completion (or disqualification) flag is compared, then the score, and finally the time.
Competitions without score have all scores set to 0.

## Inputs ##

The inputs of the evaluation process are:
  * the logical running path (see LogicalRunningPath)
  * the tree of the run (see RunModel)

The logical running path is an ordered list of pairs (logical control point, punch time).

## The process ##

The evaluation is done according to the tree of the run recursively from the root to the leaves. Therefore the evaluation of the whole tree is equivalent to the evaluation of its root node.

This is the algorithm for evaluating a non-leaf node of the tree:
  * associate to each point of the running path the direct successor of the evaluated node, in which subtree the logical control point is contained
  * split the running path in parts in such a way that all continuous subpaths have the same associated direct successor
  * evaluate recursively the continuous subpath on the associated subnode.
  * calculate the resulting completion flag according to the node type and the reculsively calculated completion flags of the successors.
  * calculate the resulting score according to the node type and according to the recursively calculated subscores/completion flags.
  * calculate the time of the run (need not be calculated recursively) and return the three values

The algorithm for evaluating a leaf node:
  * if the corresponding logical control point was punched, return the completion flag set to 1 and the score
  * otherwise return completion flag set to 0 and score 0.