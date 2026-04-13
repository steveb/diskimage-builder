==============
no-final-image
==============

This element indicates to diskimage-builder that no final image file should be
produced from the generated filesystem.  It is useful when an element handles
its own output format, such as ``ironic-python-agent-ramdisk`` (which produces
a cpio ramdisk) or Docker images.

When this element is present, diskimage-builder skips all block device
operations entirely: no loopback devices are created, no partition tables are
written, and no filesystem formatting is performed.  This makes it suitable for
use in unprivileged container environments where access to loop devices or
device-mapper is unavailable.

Elements that wish to behave this way should include this element in their
``element-deps`` file.
