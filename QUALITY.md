This document is a declaration of software quality for the *eprosima Fast DDS* library based on the guidelines provided in the [ROS 2 REP-2004 document](https://www.ros.org/reps/rep-2004.html).

Quality Declaration
=============================

*eprosima Fast DDS* (formerly Fast RTPS) is a C++ implementation of the DDS (Data Distribution Service) standard of the OMG (Object Management Group).
eProsima Fast DDS implements the RTPS (Real Time Publish Subscribe) protocol, which provides publisher-subscriber communications over unreliable transports such as UDP,
as defined and maintained by the Object Management Group (OMG) consortium.

*eprosima Fast DDS* claims to be in the **Quality Level 3** category.

Below are the rationales, notes and caveats for this claim, organized by each requirement listed in the [Package Requirements for Quality Level 1 in REP-2004](https://www.ros.org/reps/rep-2004.html#package-requirements).

## Version Policy [1]

### Version Scheme [1.i]

The **Versioning Policy Declaration** for *eprosima Fast DDS* can be found [here](VERSIONING.md).
It adheres to `semver`, which is also used by ROS 2 Core packages as stated in the [ROS 2 Developer Guide](https://index.ros.org/doc/ros2/Contributing/Developer-Guide/#versioning).
However, *eprosima Fast DDS* version policy differs with some of the ROS-specific rules, specifically, the ABI is not considered part of the public interface and any ABI break should be released in minor versions.

### Version Stability [1.ii]

*eprosima Fast DDS* is at a stable version, i.e. `>=1.0.0`
The current version can be found [here](https://github.com/eProsima/Fast-DDS/releases) and its change history can be found [here](versions.md).

### Public API Declaration [1.iii]

*eprosima Fast DDS* documentation is hosted on [Read the Docs](https://fast-dds.docs.eprosima.com). The documentation includes the [API Reference](https://fast-dds.docs.eprosima.com/en/latest/fastdds/api_reference/api_reference.html).

### API Stability Policy [1.iv]

*eprosima Fast DDS* will only break public API between major releases.

### ABI Stability Policy [1.v]

Any ABI break in *eprosima Fast DDS* will be done between minor versions and it should be clearly stated on the release notes.

### API and ABI Stability Within a Released ROS Distribution [1.vi]

[//]: # (TODO JLBuenoLopez-eProsima This specific point is so ROS related that maybe it does not make sense to keep in this Declaration. The external declaration for ROS will consider if we meet his specifications)

## Change Control Process [2]

The stability of *eprosima Fast DDS* is ensured through review, CI and tests.
All commits must be signed by the author as stated in [CONTRIBUTING](CONTRIBUTING.md).

All changes to *eprosima Fast DDS* occur through pull requests that are required to pass all CI test (unless there is enough evidence that the failure is unrelated to the change).

[//]: # (TODO JLBuenoLopez-eProsima I am not sure about the following statement)

Only the Commiters can merge a pull request.

### Change Requests [2.i]

All changes will occur through a pull request.

[//]: # (TODO JLBuenoLopez-eProsima ROS 2 developers have suggested to include a hotfix policy because there has been done over the *eprosima Fast DDS* history)

### Contributor Origin [2.ii]

*eprosima Fast DDS* uses the [Developer Certificate of Origin (DCO)](https://developercertificate.org/) as its confirmation of contributor origin policy. More information can be found in [CONTRIBUTING](Contributing.md)

### Peer Review Policy [2.iii]

All pull request will be peer-reviewed by at least one other contributor who did not author the pull request. Approval is required before merging.

### Continuous Integration [2.iv]

All pull request must pass CI to be considered for merging (unless the Committers consider that there is enough evidence that the failure is unrelated to the changes).
CI testing is automatically triggered by incoming pull requests .
Current nightly results can be seen here for all supported platforms:

* Linux [![Linux ci](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_linux/badge/icon?subject=%20%20%20Linux%20CI%20)](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_linux)
* Windows [![Windows ci](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_windows/label=windows-secure,platform=x64,toolset=v141/badge/icon?subject=%20%20%20%20Windows%20CI%20)](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_windows/label=windows-secure,platform=x64,toolset=v141)
* Mac [![Mac ci](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_mac/badge/icon?subject=%20%20%20%20%20%20%20Mac%20CI%20)](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_mac)

[//]: # (TODO JLBuenoLopez-eProsima ROS 2 is requiring to support all tier 1 platforms. Currently we are not supporting linux-aarch64_release)

[//]: # (TODO JLBuenoLopez-eProsima ROS 2 developers would want to know the specific OS information)

### Documentation Policy [2.v]

[//]: # (TODO JLBuenoLopez-eProsima Currently there is no Documentation Policy enforced in *eprosima Fast DDS* repository)

## Documentation [3]

### Feature Documentation [3.i]

*eprosima Fast DDS* has a documented feature list hosted in [Read the Docs](https://fast-dds.docs.eprosima.com/en/latest/fastdds/dds_layer/dds_layer.html#dds-layer).

### Public API Documentation [3.ii]

*eprosima Fast DDS* includes a complete API Reference which is hosted in [Read the Docs](https://fast-dds.docs.eprosima.com/en/latest/fastdds/api_reference/api_reference.html).

### License [3.iii]

The license for *eprosima Fast DDS* is Apache 2.0, and a summary can be found in each source file.
A full copy of the license can be found [here](LICENSE).

[//]: # (TODO JLBuenoLopez-eProsima As far as I know there is no linter automated test that ensures that each file has the license statement)

There is some third-party content included with *eprosima Fast DDS* which is distributed under the [Boost Software License version 1.0](http://www.boost.org/LICENSE_1_0.txt) and [Zlib license](https://github.com/leethomason/tinyxml2/blob/8c8293ba8969a46947606a93ff0cb5a083aab47a/readme.md#license).

### Copyright Statements [3.iv]

*eprosima Fast DDS* copyright holder provide a statement of copyright in each source file.

[//]: # (TODO JLBuenoLopez-eProsima As far as I know there is no linter automated test that ensures that each file has the copyright included)

## Testing [4]

### Feature Testing [4.i]

Each feature in *eprosima Fas DDS* has corresponding tests which simulate typical usage, and they are located in the `test` directory.
New features are required to have tests before being added.
Current nightly results can be found here:

* Linux [![Linux ci](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_linux/badge/icon?subject=%20%20%20Linux%20CI%20)](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_linux)
* Windows [![Windows ci](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_windows/label=windows-secure,platform=x64,toolset=v141/badge/icon?subject=%20%20%20%20Windows%20CI%20)](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_windows/label=windows-secure,platform=x64,toolset=v141)
* Mac [![Mac ci](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_mac/badge/icon?subject=%20%20%20%20%20%20%20Mac%20CI%20)](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_mac)

[//]: # (TODO JLBuenoLopez-eProsima ROS 2 is requiring to support all tier 1 platforms. Currently we are not supporting linux-aarch64_release)

[//]: # (TODO JLBuenoLopez-eProsima ROS 2 developers would want to know the specific OS information)

### Public API Testing [4.ii]

Each part of the public API has tests, and new additions or changes to the public API require tests before being added.
The tests aim to cover typical usage.

[//]: # (TODO JLBuenoLopez-eProsima I am unsure if the tests also cover corner cases.)

[//]: # (TODO JLBuenoLopez-eProsima As far as I know there is no coverage done to ensure a complete testing.)

### Coverage [4.iii]

[//]: # (TODO JLBuenoLopez-eProsima There seems to be no automatic code coverage analysis being made or anything related)

[//]: # (TODO JLBuenoLopez-eProsima There are 2 requirements concerning this point:
a. Must have code coverage tracking for the package.
b. Must have and enforce a code coverage policy for new changes)

### Performance [4.iv]

*eprosima Fast DDS* provides a test directory specifically dedicated to performance that can be found [here](test/performance).

[//]: # (TODO JLBuenoLopez-eProsima There is a second issue:
b. Must have a performance regression policy)

### Linters and Static Analysis [4.v]

*eprosima Fast DDS* has a code style that it is enforced using uncrustify.

[//]: # (TODO JLBuenoLopez-eProsima There is no linters nor automatic static analysis being done on the code developed.)

## Dependencies [5]

### Direct Runtime ROS Dependencies [5.i]

[//]: # (TODO JLBuenoLopez-eProsima This specific point is so ROS related that maybe it does not make sense to keep in this Declaration. The external declaration for ROS will consider if we meet his specifications)

### Optional Direct Runtime ROS Dependencies [5.ii]

[//]: # (TODO JLBuenoLopez-eProsima This specific point is so ROS related that maybe it does not make sense to keep in this Declaration. The external declaration for ROS will consider if we meet his specifications)

### Direct Runtime non-ROS Dependency [5.iii]

[//]: # (TODO JLBuenoLopez-eProsima I suggest renaming this part leaving non-ROS out of the title)

*eprosima Fast DDS* depends on the following packages:

- `libasio-dev`
- `libtinyxml2-dev`
- `fast-cdr`
- `foonathan_memory`

The first two dependencies are suggested to be installed for Linux using apt package manager, which would pull them from the Debian upstream.
Therefore, these dependencies can be considered Quality Level 1 following the [advantages of being packaged for Debian](https://wiki.debian.org/AdvantagesForUpstream).

The other two dependencies are installed from the eProsima repositories and their current Quality Declarations can be found

[//]: # (TODO JLBuenoLopez-eProsima Complete when the Quality Declarations are available)

## Platform Support [6]

*eprosima Fast DDS* supports the following platforms and tests each change against all of them as can be seen in the current nightly results:

* Linux [![Linux ci](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_linux/badge/icon?subject=%20%20%20Linux%20CI%20)](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_linux)
* Windows [![Windows ci](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_windows/label=windows-secure,platform=x64,toolset=v141/badge/icon?subject=%20%20%20%20Windows%20CI%20)](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_windows/label=windows-secure,platform=x64,toolset=v141)
* Mac [![Mac ci](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_mac/badge/icon?subject=%20%20%20%20%20%20%20Mac%20CI%20)](http://jenkins.eprosima.com:8080/job/nightly_fastdds_sec_master_mac)

[//]: # (TODO JLBuenoLopez-eProsima ROS 2 is requiring to support all tier 1 platforms. Currently we are not supporting linux-aarch64_release)

[//]: # (TODO JLBuenoLopez-eProsima ROS 2 developers would want to know the specific OS information)

## Vulnerability Disclosure Policy [7.i]

[//]: # (TODO JLBuenoLopez-eProsima Currently we do not have any Vulnerability Disclosure Policy. A possible solution is to conform to the ROS 2 one.)

# Current Status Summary

The chart below compares the requirements in the [REP-2004](https://www.ros.org/reps/rep-2004.html#quality-level-comparison-chart) with the current state of *eprosima Fast DDS*
|Number| Requirement| Current State |
|--|--|--|
|1| **Version policy** |---|
|1.i|Version Policy available | ✓ |
|1.ii|Stable version |✓|
|1.iii|Declared public API|✓|
|1.iv|API stability policy|✓|
|1.v|ABI stability policy|✓|
|1.vi|API/ABI stable within ROS distribution|N/A|
|2| **Change control process** |---|
|2.i| All changes occur on change request | ○|
|2.ii| Contributor origin (DCO, CLA, etc) | ✓|
|2.iii| Peer review policy | ✓ |
|2.iv| CI policy for change requests | ✓ |
|2.v| Documentation policy for change requests | |
|3| **Documentation** | --- |
|3.i| Per feature documentation | ✓ |
|3.ii| Per public API item documentation | ✓ |
|3.iii| Declared License(s) | ○ |
|3.iv| Copyright in source files| ○ |
|3.v.a| Quality declaration linked to README | ✓ |
|3.v.b| Centralized declaration available for peer review |✓|
|4| Testing | --- |
|4.i| Feature items tests | ✓ |
|4.ii| Public API tests | ○ |
|4.iii.a| Using coverage | ☓ |
|4.iii.a| Coverage policy | ☓ |
|4.iv.a| Performance tests (if applicable) | ✓ |
|4.iv.b| Performance tests policy| ☓ |
|4.v.a| Code style enforcement (linters)| ○ |
|4.v.b| Use of static analysis tools | ☓ |
|5| Dependencies | --- |
|5.i| Must not have ROS lower level dependencies | N/A |
|5.ii| Optional ROS lower level dependencies| N/A |
|5.iii| Justifies quality use of non-ROS dependencies |○|
|6| Platform support | --- |
|6.i| Support targets Tier1 ROS platforms| ○ |
|7| Security | --- |
|7.i| Vulnerability Disclosure Policy | ☓ |

[//]: # (TODO JLBuenoLopez-eProsima I suggest removing from the chart those points exclusively related to ROS)