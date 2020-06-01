# Kernel Hacking

Learning about Linux Kernel development

## Linux Foundation Course

- [Class Forum](https://forum.linuxfoundation.org/categories/lfd103-class-forum)

### Linux Kernel Development Process

While the kernel development is a continuous process, at certain points during the development, when a set of features and bug fixes are ready, a new version of the kernel is released. These new versions are called kernel releases. Linus Torvalds releases a new kernel and opens a 2-week merge window. During this merge window, he pulls code for the next release from subsystem maintainers. Subsystem maintainers send signed git pull requests to Linus either during the merge window or before. All major new development is added to the kernel during the merge window.10,000+ change sets (patches) get pulled into Linus's tree during these 2 weeks, at the end of which he releases the first release candidate, known as rc1.

At this point, the release cycle moves into a bug fixes-only mode, with a series of release candidate (rc) releases from Linus. One week after rc1 is released, rc2 comes out; rc3 comes out a week after, and so on, until all major bug fixes and regressions (if any) are resolved.

A new cycle begins with 3 weeks of quiet period, which starts a week before the release, and continues through the 2-week merge window. Maintainers and key contributors are busy getting their trees ready to send pull requests to Linus. Please note that the quiet period isn't formalized, and each sub-system might handle it differently. This period isn't well advertised, and new developers might see a slow response from the community.

![Linux Development Cycle](LinuxDevelopmentCycle.jpg)

### Active Kernel Releases

[Active Kernel Releases](https://www.kernel.org/category/releases.html)

**Release Candidate (RC)**

Release Candidate or RC releases are mainline kernel pre-releases that are used for testing new features in the mainline (we will talk about mainline tree shortly). These releases must be compiled from source. Kernel developers test these releases for bugs and regressions.

**Stable**

Stable releases are bug fix-only releases. After Linus releases a mainline kernel, it moves into stable mode. Any bug fixes for a stable kernel are backported from the mainline kernel and applied to stable git by a designated stable kernel release maintainer. Stable kernel updates are released on average, once a week, or on an as needed basis.

**Long-term**

Long-term releases are stable releases selected for long-term maintenance to provide critical bug fixes for older kernel trees.

Stable releases are normally only maintained for a few mainline release cycles, unless they are marked as long-term releases (LTR). A long-term release, as the name suggests, is maintained for a longer period to allow multiple vendors collaborate on a specific kernel release that they plan on maintaining for an extended period of time.

### Kernel Trees

**The Mainline kernel tree**

This tree is maintained by Linus Torvalds. This is where Linus releases mainline kernels and RC releases.

**Close The Stable tree**

This tree is maintained by Greg Kroah-Hartman. This tree consists of stable release branches. Stable releases are based on this tree.

**Close The linux-next tree**

This is the integration tree maintained by Stephen Rothwell. Code from a large number of subsystem trees gets pulled into this tree periodically and then released for integration testing. The process of pulling changes from various trees catches merge conflicts (if any) between trees

One of my first actions as a maintainer was to request my tree to be added to linux-next. After I commit patches to my tree, I wait 3 to 7 days before sending a pull request to Linus, giving enough time to find problems and regressions, if any. Patches applied to a tree that will be added to linux-next are only for the next merge window, including during the merge window. Patches for the next release may be added to linux-next after the merge window has closed, and the rc1 candidate has been released by Linus.

### Subsystem Maintainers

- [Subsystem Maintainers](https://www.kernel.org/doc/linux/MAINTAINERS)
- [Linux kernel mailing lists](http://vger.kernel.org/vger-lists.html)
- [List of mailing lists and their archives](https://lore.kernel.org/lists.html)
- [kernel.org Git Repositories](https://git.kernel.org/)

## Resources

- https://www.kernel.org/doc/html/v4.13/process/development-process.html
- https://www.opengroup.org/membership/forums/platform/unix
- https://kernelnewbies.org/
- https://blog.usejournal.com/how-to-become-a-linux-kernel-developer-20774c72ab07
- https://linuxhint.com/linux-kernel-tutorial-beginners/
- https://training.linuxfoundation.org/training/a-beginners-guide-to-linux-kernel-development-lfd103/
- https://developer.ibm.com/technologies/linux/articles/l-linux-kernel/
- https://www.kernel.org/doc/html/v4.13/process/howto.html
- https://en.wikipedia.org/wiki/Linux_kernel
- https://lkw.readthedocs.io/en/latest/
