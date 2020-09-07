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
|1.i|Version Policy available | ✓ | ✓ | ✓ | ✓ | ● ||
|1.ii|Stable version |✓| ✓ | ✓ | ✓ | | |
|1.iii|Declared public API|✓|✓|✓|●|||
|1.iv|API stability policy|✓|✓|✓|✓|||
|1.v|ABI stability policy|✓|✓|✓|✓|||
|1.vi|API/ABI stable within ROS distribution|☓|✓|✓|●|||
|2| **Change control process** |||||||
|2.i| All changes occur on change request |■|✓|✓|✓|●||
|2.ii| Contributor origin (DCO, CLA, etc) |✓|✓|✓||||
|2.iii| Peer review policy |✓|✓|||||
|2.iv| CI policy for change requests |✓|✓|✓|✓|||
|2.v| Documentation policy for change requests |☓|✓|||||
|3| **Documentation** |||||||
|3.i| Per feature documentation |✓|✓|✓||||
|3.ii| Per public API item documentation |✓|✓|||||
|3.iii| Declared License(s) |■|✓|✓|✓|✓|●|
|3.iv| Copyright in source files|■|✓|✓|✓|✓||
|3.v| Quality Declaration|✓|✓|✓|○|||
|3.v.a| Quality declaration linked to README |✓|✓|✓|✓|||
|3.v.b| Centralized declaration available for peer review |■|●|●|○|||
|3.v.c| Lists and Peer Review |N/A|✓|✓|✓||
|4| **Testing** |||||||
|4.i| Feature items tests |✓|✓|✓|●|●||
|4.ii| Public API tests |✓|✓|||||
|4.iii.a| Using coverage |☓|✓|✓||||
|4.iii.a| Coverage policy |☓|✓|||||
|4.iv.a| Performance tests (if applicable) |✓|✓|||||
|4.iv.b| Performance tests policy|☓|✓|||||
|4.v.a| Code style enforcement (linters)|■|✓|✓||||
|4.v.b| Use of static analysis tools |☓|✓|✓||||
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
 
 ### Change Requests [2.i]
 
 This point is considered to be partially met because in the change history there has been some hotfix changes made without Pull Request.
 ROS 2 developers suggest that we have a Hotfix Policy that states in which cases is valid to use this method and how it is handled.

 ### License [3.iii]

 ROS 2 developers would like that some tool ensures that the License header is included in all files.

 Personally, I am not sure if our enforced code style using uncrustify checks and enforces this issue.

 ### Copyright Statements [3.iv]

 ROS 2 developers would like that some tool ensures that the copyright statement is included in all files.

 Personally, I am not sure if our enforced code style using uncrustify checks and enforces this issue.

 ### Lists and Peer Review [3.v.c]

 This point is considered N/A as of now because it is too early to consider.

 ### Platform Support [6]

 ROS 2 developers consider partially met this point because there is no evidence that *eprosima Fast DDS* supports all [Tier1 ROS platforms](https://www.ros.org/reps/rep-2000.html).
 Specifically, *eprosima Fast DDS* does not name linux-aarch64 between its [supported platforms](README.md#supported-platforms).
 The OS supported in this particular platform for the Foxy Fitzroy Distribution is Ubuntu Focal (20.04).

 Additionally, *eprosima Fast DDS* does not run any test for that particular platform (CI, performance, feature, public API)

 ROS 2 developers would also like to know which OS *eprosima Fast DDS* supports.

 This point is REQUIRED to be considered for the Quality Level 3 category.
 Maybe this is the first issue that must be addressed to avoid any doubts about claiming to be considered Quality Level 3.

### Vulnerability Disclosure Policy [7.i]

Currently, *eprosima Fast DDS* does not have any Vulnerability Disclosure Policy.

A possible solution is to conform to the [ROS 2 Vulnerability Disclosure Policy](https://www.ros.org/reps/rep-2006.html)

This point is only recommended for Quality Level 3, but it is REQUIRED for Quality Level 2 and above.

## Progress toward Quality Level 2

Below the points that should be solved in order to qualify for the Quality Level 2 are addressed.
Those points already dealt in this document are not repeated.

### Centralized Declaration Available for Peer Review [3.v.b]

This point is recommended for Quality Level 2 (and Quality Level 1) packages.
It is only matter of time that the Quality Declaration becomes public and open to public discussion.
The Quality Declaration is going to be discussed first internally before opening the discussion to peer-reviewing.

### Using Coverage [4.iii.a]

*eprosima Fast DDS* does not have any automatic code coverage analysis tool and does not currently conforms to the guidelines in this point (as far as I know)

This point is REQUIRED to be considered for the Quality Level 2 category.

### Code style enforcement (Linters)[4.v.a]

*eprosima Fast DDS* enforces code style using uncrustify.
I am not sure if this is public knowledge because ROS 2 developers have not mentioned this in their first Quality Declaration assesment.

### Use of Static Analysis Tools [4.v.b]

*eprosima Fast DDS* does not use any static analysis tool as far as I know.
(ROS 2 developers have not found any evidence of any tool related in their first assesment).

This point is REQUIRED to be considered for the Quality Level 2 category.

### Direct Runtime non-ROS Dependency [5.iii]

This point is considered to be partially fulfilled but it is early to have a complete assesment.
First, the Quality Declaration for the dependencies must be drafted and studied.

## Progress toward Quality Level 1

Below the points that should be solved in order to qualify for the Quality Level 1 are addressed.
Those points already dealt in this document are not repeated.

### Documentation Policy [2.v]

*eprosima Fast DDS* does not have any policy that enforces that any change merge to master is documented.

ROS 2 developers state that there is no clear consistency among how to document each software change. They mention that, at least, this is better reflected in the releases summaries.

Additionally, the change history contained in the versions.md file is not automatically updated when a new release is made.

This point is REQUIRED to be considered for the Quality Level 1 category.

### Coverage Policy [4.iii.b]

*eprosima Fast DDS* does not use any coverage tool and consequently does not have any coverage policy.

This point is REQUIRED to be considered for the Quality Level 1 category.

### Performance test policy [4.iv.b]

*eprosima Fast DDS* does not have any public performance regression policy.

This point is REQUIRED to be considered for the Quality Level 1 category.

## Quality Level 3 Requirements Partially Met

* Change requests [2.i]
* Platform Support [6]

## Quality Level 2 Requirements Not Yet Met

* API and ABI stability within a released ROS distribution [1.vi]
* Using coverage [4.iii.a]
* Use of static analysis tools [4.v.b]
* Vulnerability Disclosure Policy [7.i]

## Quality Level 1 Requirements Not Yet Met

* Documentation policy for change requests [2.v]
* Coverage policy [4.iii.b]
* Performance test policy [4.iv.b]
