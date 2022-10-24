# Remote readers for bakana

## Overview

This package provides a variety of remote readers for the [**bakana**](https://npmjs.org/package/bakana) package,
allowing us to perform scRNA-seq analyses on datasets from other sources.
Currently we support:

- Count matrices and row/column `DataFrame`s from [ExperimentHub](https://bioconductor.org/packages/ExperimentHub).

In the future, we aim to support:

- Count matrices and row/column annotations from [ArtifactDB](https://github.com/ArtifactDB).

## Quick start

Usage is as simple as:

```js
import * as ehub from "bakana-remotes/ExperimentHub";
import * as bakana from "bakana";

// Add all desired readers.
bakana.availableReaders["ExperimentHub"] = ehub;
```

For ExperimentHub-sourced datasets, we can pass the following object as an entry of `matrices` in [`bakana.runAnalysis()`](https://ltla.github.io/bakana/global.html#runAnalysis).

```js
{
    "type": "ExperimentHub",
    "id": "zeisel-brain" // or any other ID.
}
```

The supported set of IDs is listed in `ehub.availableDatasets()`... which is currently not a lot right now.

## Links

See the [**bakana**](https://github.com/LTLA/bakana) documentation for more details on how to create a custom reader.
Implementations of readers for other databases are welcome.
