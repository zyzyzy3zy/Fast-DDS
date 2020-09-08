This document is temporal and its only aim is to compare the current Quality Level with the requirements to be considered Quality Level 1 following the guidelines provided in the [ROS 2 REP-2004 document](https://www.ros.org/reps/rep-2004.html).
This document also presents different solutions and options to conform to the guidelines and progress toward Quality Level 1.

Progress toward Quality Level 1
=============================

# Current Status Summary Comparison

The chart below compares *eprosima Fast DDS* current Quality Level with Quality Levels 1 through 5 relative to the 'Level 1' requirements' 

✓ = required

● = recommended

○ = optional

☓ = requirement currently unmet

■ = requirement partially fulfilled 

|Number| Requirement| Current State | Level 1 | Level 2 | Level 3 | Level 4 | Level 5 |
|--|--|--|--|--|--|--|--|
|1| **Version policy** |||||||
|1.i|Version Policy available |✓|✓|✓|✓|●||
|1.ii|Stable version |✓|✓|✓|✓|||
|1.iii|Declared public API|✓|✓|✓|●|||
|1.iv|API stability policy|✓|✓|✓|✓|||
|1.v|ABI stability policy|✓|✓|✓|✓|||
|1.vi|API/ABI stable within ROS distribution|☓|✓|✓|●|||
|2| **Change control process** |||||||
|2.i| All changes occur on change request |■|✓|✓|✓|●||
|2.ii| Contributor origin (DCO, CLA, etc) |✓|✓|✓||||
|2.iii| Peer review policy |■|✓|||||
|2.iv| CI policy for change requests |■|✓|✓|✓|||
|2.v| Documentation policy for change requests |☓|✓|||||
|3| **Documentation** |||||||
|3.i| Per feature documentation |✓|✓|✓||||
|3.ii| Per public API item documentation |✓|✓|||||
|3.iii| Declared License(s) |✓|✓|✓|✓|✓|●|
|3.iv| Copyright in source files|✓|✓|✓|✓|✓||
|3.v| Quality Declaration|✓|✓|✓|○|||
|3.v.a| Quality declaration linked to README |✓|✓|✓|✓|||
|3.v.b| Centralized declaration available for peer review |■|●|●|○|||
|3.v.c| Lists and Peer Review |N/A|✓|✓|✓||
|4| **Testing** |||||||
|4.i| Feature items tests |■|✓|✓|●|●||
|4.ii| Public API tests |✓|✓|||||
|4.iii.a| Using coverage |■|✓|✓||||
|4.iii.a| Coverage policy |☓|✓|||||
|4.iv.a| Performance tests (if applicable) |✓|✓|||||
|4.iv.b| Performance tests policy|■|✓|||||
|4.v.a| Code style enforcement (linters)|✓|✓|✓||||
|4.v.b| Use of static analysis tools |■|✓|✓||||
|5| **Dependencies** |||||||
|5.i| Must not have ROS lower level dependencies |N/A|✓|✓||||
|5.ii| Optional ROS lower level dependencies|N/A|○|○|○|||
|5.iii| Justifies quality use of non-ROS dependencies |■|✓|✓||||
|6| **Platform support** |||||||
|6.i| Support targets Tier1 ROS platforms|■|✓|✓|✓|●||
|7| **Security** |||||||
|7.i| Vulnerability Disclosure Policy |☓|✓|✓|●|||

## Current Status Claim

Currently *eprosima Fast DDS* claims to be in the **Quality Level 3** category.
However, there are some suggestions that have been made from ROS 2 developers to conform better to the [ROS 2 REP-2004 guidelines](https://www.ros.org/reps/rep-2004.html).

Below you can find those suggestions related to each specific point:

 ### API and ABI Stability Within a Released ROS Distribution [1.vi]
 
 This point is recommended for Quality Level 3 packages.
 *eprosima Fast DDS* Version Policy does not conform to the ROS 2 Version Policy.
 *eprosima Fast DDS* does not consider ABI breaks to be breaks in the public API and consequently, those changes are released between minor versions.
 
 Therefore, if there is not a specific version pinned to each ROS Distribution, this point is not met.
 Having a specific version pinned to each ROS Distribution has the main disadvantage that each pinned version has to be supported the same time that its ROS Distribution (up to five years for some distributions).

 **[Task #9265](https://eprosima.easyredmine.com/issues/9265): Analyze which API is ROS using to establish which ABI cannot be broken.**
 
 ### Change Requests [2.i]
 
 This point is considered to be partially met because in the change history there has been some hotfix changes made without Pull Request.
 ROS 2 developers suggest that we have a Hotfix Policy that states in which cases is valid to use this method and how it is handled.

 **[Task #9262](https://eprosima.easyredmine.com/issues/9262): Update CONTRIBUTING adding information about the Change Control Process taking as example the one hosted in [all-docs](https://github.com/eProsima/all-docs/blob/master/CONTRIBUTING.md)**

 This task should also deal and clarify the following points:

 * All changes occur on change request [2.i]
 * Contributor origin (DCO) [2.ii] (Already introduced)
 * Peer review policy [2.iii]
 * CI policy for change requests [2.iv]
 * [Documentation policy for change requests [2.v]](ProgressToQ1.md#documentation-policy-2v)

 Additionally, it should be linked or deal also with the following points:

 * Coverage policy for new changes [4.iii.b]
 * [Performance regression policy [4.iv.b]](ProgressToQ1.md#performance-test-policy-4ivb)
 * Use of static analysis tools for code style enforcement [4.v.b]

 **Task: Currently the coverage report is done only over the nightly CI tests. Therefore, there is no coverage policy for new changes that can be enforced right now. This should be discussed in the next Sprint meeting.**

 ### Lists and Peer Review [3.v.c]

 This point is considered N/A as of now because it is too early to consider.

 ### Platform Support [6]

 ROS 2 developers consider partially met this point because there is no evidence that *eprosima Fast DDS* supports all [Tier1 ROS platforms](https://www.ros.org/reps/rep-2000.html).
 Specifically, *eprosima Fast DDS* does not name linux-aarch64 between its [supported platforms](README.md#supported-platforms).
 The OS supported in this particular platform for the Foxy Fitzroy Distribution is Ubuntu Focal (20.04).

 Additionally, *eprosima Fast DDS* does not run any test for that particular platform (CI, performance, feature, public API)

 ROS 2 developers would also like to know which OS *eprosima Fast DDS* supports.

 This point is REQUIRED to be considered for the Quality Level 3 category.

**[Task #9263](https://eprosima.easyredmine.com/issues/9263): Define Tier platforms and OS for *eprosima Fast DDS* adding the corresponding file to the repository and linking to the README and QUALITY DECLARATION**

**[Task #9264](https://eprosima.easyredmine.com/issues/9264): Add CI support for aarch64 with Ubuntu Focal in Jenkins (nightly and manual linked to pull requests). Include also coverage report.**

### Vulnerability Disclosure Policy [7.i]

Currently, *eprosima Fast DDS* does not have any Vulnerability Disclosure Policy.

A possible solution is to conform to the [ROS 2 Vulnerability Disclosure Policy](https://www.ros.org/reps/rep-2006.html)

This point is only recommended for Quality Level 3, but it is REQUIRED for Quality Level 2 and above.

**[Task #9267](https://eprosima.easyredmine.com/issues/9267): Prepare the Vulnerability Disclosure Policy based on the [ROS 2 one](https://www.ros.org/reps/rep-2006.html)**

## Progress toward Quality Level 2

Below the points that should be solved in order to qualify for the Quality Level 2 are addressed.
Those points already dealt in this document are not repeated.

### Centralized Declaration Available for Peer Review [3.v.b]

This point is recommended for Quality Level 2 (and Quality Level 1) packages.
It is only matter of time that the Quality Declaration becomes public and open to public discussion.
The Quality Declaration is going to be discussed first internally before opening the discussion to peer-reviewing.

### Use of Static Analysis Tools [4.v.b]

*eprosima Fast DDS* enforces the code style by running Uncrustify tests on each pull request. The code style is only enforced in the new changes being submitted. Therefore, the tendency will be to homogenize the older source files to the code style.

This point is REQUIRED to be considered for the Quality Level 2 category.

**[Task #9266](https://eprosima.easyredmine.com/issues/9266): Update and translate [README](https://github.com/eProsima/cpp-style/blob/master/README.es.md) in cpp-style repository**

### Direct Runtime non-ROS Dependency [5.iii]

This point is considered to be partially fulfilled but it is early to have a complete assesment.
First, the Quality Declaration for the dependencies must be drafted and studied.

**Task: Prepare Quality Declaration and Roadmap for FastCDR**

**Task: Prepare Quality Declaration and Roadmap for foonathan_memory**

## Progress toward Quality Level 1

Below the points that should be solved in order to qualify for the Quality Level 1 are addressed.
Those points already dealt in this document are not repeated.

### Documentation Policy [2.v]

*eprosima Fast DDS* does not have any policy that enforces that any change merge to master is documented.

ROS 2 developers state that there is no clear consistency among how to document each software change. They mention that, at least, this is better reflected in the releases summaries.

Additionally, the change history contained in the versions.md file is not automatically updated when a new release is made.

This point is REQUIRED to be considered for the Quality Level 1 category.

### Coverage Policy [4.iii.b]

**Task: prepare a Coverage Policy. Analyze the results of the current coverage report and propose achievable goals to improve.**

**[Task #9268](https://eprosima.easyredmine.com/issues/9268): add coverage report to Windows in Jenkins**

This point is REQUIRED to be considered for the Quality Level 1 category.

### Performance test policy [4.iv.b]

*eprosima Fast DDS* does not have any public performance regression policy.

This point is REQUIRED to be considered for the Quality Level 1 category.

## Quality Level 3 Requirements Partially Met

* [Change requests [2.i]](ProgressToQ1.md#change-requests-2i)
* [Platform Support [6]](ProgressToQ1.md#platform-support-6)

## Quality Level 2 Requirements Not Yet Met

* [API and ABI stability within a released ROS distribution [1.vi]](ProgressToQ1.md#api-and-abi-stability-within-a-released-ros-distribution-1vi)
* [Use of static analysis tools [4.v.b]](ProgressToQ1.md#use-of-static-analysis-tools-4vb)
* [Vulnerability Disclosure Policy [7.i]](ProgressToQ1.md#vulnerability-disclosure-policy-7i)

## Quality Level 1 Requirements Not Yet Met

* [Coverage policy [4.iii.b]](ProgressToQ1.md#coverage-policy-4iiib)
