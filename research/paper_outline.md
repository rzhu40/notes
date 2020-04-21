# Paper Outline

-----

## Centrality

* Introduce current flow centrality model (closeness/ betweenness).
* Initial voltage/ current distributions based on centrality.
* Voltage/ current/ filament state dynamcis based on centrality.

-----

## TE (and AIS) vs centrality

* Introduce the idea of TE and AIS.
* The plot of TE vs node centrality (and AIS vs junction centrality).
* Talk about the linear trend in TE vs centrality plot. (Under controled protocol) - difficult for multiple electrodes.

-----

## TE time series analysis

* Show how TE line up with conductance (or $\Delta G$) vs time.
* Meanwhile, show how modularity line up with these two values as well.
* (Maybe) show the Gamiro (module z-score vs participation coefficient) plot at different time points.

-----

## (Maybe) TE behavior in tasks

* Non-linear wave transformation.
* Mackey-Glass forecast.
* (Have to think about this) MNIST.

And talk about the special case - when multiple source/drains are applied, the linear trend vanishes. Mainly because most wires/junctions are involved in the dynamics.

------

## Dual task

* Link modularity with learning in the second task.
* Preactivate the network with Mackey-Glass signal. Feed in with the forecast layout so that most junctions can be involved.
* Move onto the next task (non-linear wave transformation, MNIST, etc). See how the results change.
* No reset MNIST
* Learning rate

