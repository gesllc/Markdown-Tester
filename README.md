
# Master Control Board Documentation

## Table of Contents
1. [Introduction](#introduction)

2. [Build Environment](#build_environment)
	1. [Environment Variables](#be_1)
	2. [Applications](#be_2)

2. [Database Documentation](#db_documentation)
	1. [Subsection 1](#subsection_sp_1)
	2. [Subsection 2](#subsection_sp_2)

2. [Update Procedure](#update_procedure)
	1. [Subsection 1](#subsection_sp_1)
	2. [Subsection 2](#subsection_sp_2)

2. [Probe Flash Instructions](#probe_flash_instructions)
	1. [Subsection 1](#subsection_sp_1)
	2. [Subsection 2](#subsection_sp_2)

2. [Telnet Ports](#telnet_ports)
	1. [Subsection 1](#subsection_sp_1)
	2. [Subsection 2](#subsection_sp_2)

2. [User Interface](#user_interface)
	1. [Subsection 1](#subsection_sp_1)
	2. [Subsection 2](#subsection_sp_2)

---
<a name="introduction"></a>
### Introduction
The Master Control Board (MCB) is the primary control board for the Virtuo instrument.  It is based 
on a ColdFire 68332 CPU.

---
<a name="build_environment"></a>
### Build Environment
This section provides instructions for installing the necessary software tools for building the Virtuo MCB firmware.   

<a name="be_1"></a>
#### Environment Variables
Prior to installing software packages, add the following Environment Variables to the "System Variables" section.   

| Variable | Value |
| :------- | :---- |
| GHS_INT  | C:/ghs/int1002 \(Consider different path\) | 
| MULTI_61 | C:/ghs/comp_20121 \(Consider different path\) |
| PTOOLS   | C:/PT             |
| PATH     | ;C:/Users/Public/opus |

<a name="be_2"></a>
#### Required Applications

| Application | Location |
| :------- | :---- |
| Subversion Client                | URL: http://usstlweb02:/Applications/Subversion/CollabNetSubversion-client-1.8.9-3-x64.exe                |
| Source Tree \(or Git\)           | URL: http://usstlweb02:/Applications/Git/SourceTreeSetup-3.0.17.exe                                       |
| Git Client                       | URL: http://usstlweb02:/Applications/Git/Git-2.28.0-64-bit.exe                                            |
| Python 2.7                       | URL: http://usstlweb02:/Applications/Python/2.7.2/python-2.7.2.msi                                        |
| Python 2.7 Setup Tools           | URL: http://usstlweb02:/Applications/Python/2.7.2/setuptools-0.6c11.win32-py2.7.exe                       |
| Python Mako Templates            | URL: http://usstlweb02:/Applications/Python/2.7.2/Libraries/Mako-0.7.3/                                   |
| Python Image Library             | URL: http://usstlweb02:/Applications/Python/2.7.2/Libraries/Pillow-2.4.0.win32-py2.7.exe                  |
| Python 3.X                       | URL: http://usstlweb02:/Applications/Python/3.8.2/python-3.8.2-amd64.exe                                  |
| State Machine Compiler           | URL: https://usstlsvn02:18080/svn/toos/tools/smc_6_0_0                                                    |
| Multi 6-1                        | URL: http://usstlweb02:/Applications/GreenHills/Multi/multi_6-1_install.iso                               |

#### Apply NOR flash patches
The original NOR Flash driver provided from Green Hills Software had performance issues.  An optimized driver is installed using:   
* cd %GHS_INT%/lib/intcf_float
* rename libflash.a originalGHS_libflash.a
* rename libflash.dba originalGHS_libflash.dba
* wget http://usstlweb02/Applications/GreenHills/ColdFire-NorFlashDriver/libflash.a
* wget http://usstlweb02/Applications/GreenHills/ColdFire-NorFlashDriver/libflash.dba


#### Check out and build Integrity kernel
From base of GHS installation directory:
* svn checkout https://usstlsvn02:18080/svn/vendor/GreenHills/integrity/coldfire_mcb/int1002
* cd int1002/bmx_MCB
* %MULTI_61%/gbuild

#### Check out and build MCB Application
From your repository working directory
* svn checkout https://usstlsvn02:18080/svn/Virtuo/mcb/trunk 
* OR \(Coming soon....\)
* git clone http://usstlgit03:7990/scm/vir/mcbTBD.git
* %MULTI_61%/gbuild




---
<a name="db_documentation"></a>
### Database Documentation

---
<a name="update_procedure"></a>
### Update Procedure

---
<a name="probe_flash_instructions"></a>
### Probe Flash Instructions

---
<a name="telnet_ports"></a>
### Telnet Ports

---
<a name="user_interface"></a>
### User Interface

