Copyright 2020, Avnet, Inc. All Rights Reserved.

Table of Contents:

Section 1 - Legal Statements
Section 2 - Design Info


-- Section 1 - Legal Statements --

This material may not be reproduced, distributed, republished, 
displayed, posted, transmitted or copied in any form or by any means without 
the prior written permission of Avnet, Inc.  AVNET and the Avnet logo are 
registered trademarks of Avnet, Inc.  All trademarks and trade names are the 
properties of their respective owners and Avnet, Inc. disclaims any 
proprietary interest or right in trademarks, service marks and trade names 
other than its own.  Avnet is not responsible for typographical or other 
errors or omissions or for direct, indirect, incidental or consequential 
damages related to this material or resulting from its use.  Avnet makes no 
warranty or representation respecting this material, which is provided on an 
"AS IS" basis.  AVNET HEREBY DISCLAIMS ALL WARRANTIES OR LIABILITY OF ANY 
KIND WITH RESPECT THERETO, INCLUDING, WITHOUT LIMITATION, REPRESENTATIONS
REGARDING ACCURACY AND COMPLETENESS, ALL IMPLIED WARRANTIES AND CONDITIONS 
OF MERCHANTABILITY, SUITABILITY OR FITNESS FOR A PARTICULAR PURPOSE, TITLE 
AND/OR NON-INFRINGEMENT.  This material is not designed, intended or 
authorized for use in medical, life support, life sustaining or nuclear 
applications or applications in which the failure of the product could 
result in personal injury, death or property damage.  Any party using or 
selling products for use in any such applications do so at their sole risk 
and agree that Avnet is not liable, in whole or in part, for any claim or 
damage arising from such use, and agree to fully indemnify, defend and hold 
harmless Avnet from and against any and all claims, damages, loss, cost, 
expense or liability arising out of or in connection with the use or 
performance of products in such applications.

NOTICE:  Some of the application binaries contained within this material are 
derived from publicly available open source repositories.  Modifications to
the original source code repositories or releases, required to complete the
tutorial are documented within the tutorial documents and the required source
code changes are provided as patches to the original source code.  Avnet does 
not place any restriction upon the use or distribution of the software 
patches provided this action is performed under the same license as the 
software project from which the patch is derived.

The GNU/Linux distribution found within this material is a modular operating 
system consisting of hundreds of software components. Most of the components 
are open source packages, developed independently, and accompanied by 
separate license terms (such as GPL, LGPL, BSD, modified BSD or others). 
Your license rights with respect to individual components accompanied by 
separate license terms are defined by those terms (The license agreement for 
each component is generally located in the component's source code); nothing 
shall restrict, limit, or otherwise affect any rights or obligations you may 
have, or conditions to which you may be subject, under such license terms. 
This agreement does not limit your rights under, or grant you rights that 
supersede, the license terms of any particular component.

With the potential exception of certain firmware files, the license terms of 
components normally included in a Linux distribution normally permits you to 
copy, modify, and redistribute the component, in both source code and binary 
code forms. Some licenses require you to make the source available to those 
people you distribute a binary to. Some licenses require you to make 
available the recipe for installing their own updates.

For example:

Busybox is licensed under the GPL2.
Dropbear is licensed under the MIT lecense.
Linux is licensed under the GPL2 with exclusions for user programs.
U-Boot is licensed under the GPL2.

It is up to you and your legal team to make sure your product distribution 
complies with the licensing requirements of whatever software package that 
you include in your product.

We are not lawyers, and cannot and will not provide legal assistance, legal 
advice about any software licensing or patent issue. We will not be able to 
answer questions about the legal significance of the facts, licensing issues, 
or conduct legal research, or provide information about the legal deadlines 
that might apply to your situation. You or your legal representative needs 
to determine these issues for yourself before you distribute your product. 
A good place to start might be to see how not to do things, at the 
gpl-violations.org project.


-- Section 2 - Design Info --

TOOL/SOFTWARE VERSIONS:

	- Xilinx Vivado 2019.2 and SDK
	- Xilinx_Zynq_2019_2_Release - Linux kernel created with PetaLinux
	  (http://avnet.me/xilinx_zynq_2019_2_release)

DESCRIPTIONS:

	- Linux kernel, ramdisk, boot.elf, devicetree are from the ZedBoard 
	  files found in the Xilinx_Zynq_2019_2_Release archive (created with 
	  PetaLinux)

	- ZedBoard devicetree is modified as follows:
		- updated memory entry for 1GB DDR3
		- adds reg-init string to Ethernet PHY entry
	
	- Boot image BOOT.bin targeted to MZ7010 and MZ7020
		- system_wrapper.bit contains an empty/placeholder Zynq PL design
		- FSBL loads the .bit file contained in BOOT.bin
		- SSBL/U-boot is contained in BOOT.bin

FILES:

	Each mz70x0_basic.zip archive contains the following:
	
	- Vivado and SDK project files
	
	- Bootable SD card image
	
		> sd_image (copy the contents of this folder to your 4GB SD card root)
			- BOOT.bin
			- devicetree.dtb
			- uImage
			- uramdisk.image.gz
			> sources
				- devicetree_microzed_2014_4.dts
				- u-boot.elf
