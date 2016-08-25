-# Introduction

The individual performance tests in PerfCake are created in so called _scenarios_. The scenarios describe the configuration and behaviour of tests.
The PerfCake Users' Guide can help you with basic usage of PerfCake and with creation of many scenarios. In this book we go a little bit deeper and
reveal some advanced scenario configurations that might not be immediately obvious but can help with complex performance testing. For example we will
demonstrate how to monitor utilization of individual client threads to be sure there is no stalled connection and the test reports correct performance 
data.

For now there is no special order of the scenarios. They are all standalone recipes that can be applied without any dependencies between them. 

Each scenario also has a short video with the walk-through of its implementation.

Some scenarios might link to source codes located on GitHub. Please always checkout the lates commits in the _devel_ branch. This book is still
a work in progress and the scenarios might not made it to the release yet.

-# Scenarios