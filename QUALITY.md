Quality policy declaration
=============================

This **Quality Declaration** is based on the guidelines provided in [REP-2004](https://www.ros.org/reps/rep-2004.html). `Fast DDS` having been chosen as the default middleware implementation for the [Robot Operating System 2 (ROS 2)](https://index.ros.org/doc/ros2/) requires the best Quality Level possible, aspiring to be included in the Quality 1 category.

The criteria listed in the [Quality Level 1 Package Requirements](https://www.ros.org/reps/rep-2004.html#package-requirements) are presented below:

## 1. Version Policy

The **`Fast DDS` Version Policy**  can be consulted in [VERSIONING](https://github.com/eProsima/Fast-DDS/blob/master/VERSIONING.md). This policy adheres to the [Semantic Versioning](https://semver.org/) policies.

### 1.i Version stability

The `Fast DDS` version is stable and follows the [Semantic Versioning](https://semver.org/#spec-item-2) criteria. The latest release can be found [here](https://github.com/eProsima/Fast-DDS/releases). Additionally, the change history is kept in the [versions](https://github.com/eProsima/Fast-DDS/blob/master/versions.md) file.

### 1.ii Public API declaration

The `Fast DDS` library is an implementation of the [DDS (Data Distribution Service) Specification](https://www.omg.org/spec/DDS/1.4/PDF) which already defines the main characteristics of the DDS API. `Fast DDS` API implementation is well documented and provides a wide set of use case examples to start easily using the library to develop specific applications. The latest documentation release can be found [here](https://fast-dds.docs.eprosima.com/en/latest/).

### 1.iii API stability policy

Following the [Semantic Versioning](https://semver.org/#spec-item-8) policy, API stability is ensured always in MINOR and PATCH releases. MAJOR releases are reserved to changes in the public API that are not backward compatible.

### 1.iv ABI stability

As stated in the [Versioning policy declaration](https://github.com/eProsima/Fast-DDS/blob/master/VERSIONING.md), ABI breaks are done between MINOR releases and they should be clearly stated on the release notes. PATCH releases ensure ABI stability.

### 1.v API and ABI stability within a released ROS distribution

