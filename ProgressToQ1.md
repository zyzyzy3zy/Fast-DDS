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
|3.v.c| Reference Review Process |N/A|✓|✓|✓||
|4| **Testing** |||||||
|4.i| Feature items tests |✓|✓|✓|●|●||
|4.ii| Public API tests |■|✓|||||
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