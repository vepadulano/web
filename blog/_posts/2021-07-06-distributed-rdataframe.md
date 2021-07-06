---
title: "RDataFrame is going distributed!"
layout: archive
author: Vincenzo Eduardo Padulano
---

[RDataFrame](https://root.cern/doc/master/classROOT_1_1RDataFrame.html) is ROOT's declarative interface for data
analysis and since its release in 6.14 has seen tons of usages in real world analysis use cases and other examples in
the wild. Parallelism has always been a staple of its design with the support of executing the event loop on all cores
of a machine thanks to implicit multi-threading. Since ROOT 6.24, this aspect of RDataFrame has been enhanced further
with distributed computing capabilities, allowing users to run their analysis on multi-node computing clusters through
widely used frameworks such as [Apache Spark](https://spark.apache.org/), [Dask](https://dask.org/) or
[AWS Lambda](https://aws.amazon.com/lambda/). The feature is currently in an experimental phase, try it out with this
simple example (requires the python `pyspark` package):

```python
import ROOT
 
# Point RDataFrame calls to the Spark specific RDataFrame
RDataFrame = ROOT.RDF.Experimental.Distributed.Spark.RDataFrame
 
# It still accepts the same constructor arguments as traditional RDataFrame
df = RDataFrame("mytree", "myfile.root")
 
# Continue the application with the traditional RDataFrame API
sum = df.Filter("x > 10").Sum("y")
h = df.Histo1D("x")
 
print(sum.GetValue())
h.Draw()
```

## Goals and implementation

The main goal is to support distributed execution of any RDataFrame application. This has lead to the creation of a 
**Python** package that acts as a glue between the RDataFrame API (available in Python through PyROOT) and the APIs of
distributed computing frameworks, which are offered in Python in the vast majority of cases. Another key goal is to be
able to support as many backends as possible, in order to avoid being tied to any particular infrastructure. This is
reached through a modular implementation, that defines a generic task (representing the RDataFrame computation graph) to
be executed on data. The input dataset is logically split into many ranges of entries, which will be sent to the
distributed nodes for processing. Each range will then be paired to the generic task and submitted to the computing
framework thanks to the particular backend implementation. An added benefit of using RDataFrame is that the distributed
tasks run C++ computations. This is made available thanks to PyROOT and cling.The current status of the package offers
support for running the application on a Spark cluster. Other backends have already been implemented and demonstrated at
different conferences and will be available in future ROOT releases:

* Dask backend: shown at [PyHEP 2021](https://indico.cern.ch/event/1019958/contributions/4419751/)
* AWS Lambda backend: developed thanks to an external contribution from AGH University and shown at [HPDC 2021](https://highperformanceserverless.github.io/program.html)

It will be possible to implement many more backends in the future thanks to this modular design.

As shown by the example snippet above, all it takes to steer an existing RDataFrame application to distributed
resources is to use the correct RDataFrame instance and provide it with the arguments needed to connect to the remote
cluster. Let's see an example of connection to a Dask cluster:

```python
from dask.distributed import Client
import ROOT

# Point RDataFrame calls to the Dask specific RDataFrame
RDataFrame = ROOT.RDF.Experimental.Distributed.Dask.RDataFrame

# Create the Client object to connect to the Dask cluster
# See the Dask documentation for all the options available
client = Client("DASK_SCHEDULER_ADDRESS")

# It still accepts the same constructor arguments as traditional RDataFrame
# And supports some extra keyword arguments
df = RDataFrame("mytree", "myfile.root", npartitions = 8, daskclient = client)
```

In this example the `npartitions` parameter tells the RDataFrame in how many ranges of entries the input dataset should
be split. Each range will then correspond to a task on a node of the cluster. The `daskclient` parameter receives the
object needed to connect to the Dask scheduler. All the options are available in the
[Dask documentation](https://distributed.dask.org/en/latest/client.html). The equivalent object for the Spark framework
is called [SparkContext](https://spark.apache.org/docs/latest/api/python/reference/api/pyspark.SparkContext.html) and in
general every backend will have its own way to connect to a cluster of nodes.

Once the correct `RDataFrame` object has been created, there is no need to modify any other part of the program.

## Conclusions

Distributed RDataFrame enables large-scale interactive data analysis with ROOT. This Python layer on top of RDataFrame
allows to steer C++ computations on a set of computing nodes and returning the final result directly to the user, so
that the entire analysis can be run within the same application. It is available as an experimental feature since ROOT
6.24 with the support for running on a Spark cluster, with more backends coming in future ROOT releases. Try it with our
[tutorial](https://root.cern/doc/master/distrdf001__spark__connection_8py.html) and learn more about it in the
respective RDataFrame documentation [section](https://root.cern/doc/master/classROOT_1_1RDataFrame.html#distrdf).