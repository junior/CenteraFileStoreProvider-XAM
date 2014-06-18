CenteraFileStoreProvider Component
==================================

|                      	|                                                          	|
|----------------------	|----------------------------------------------------------	|
| Date:                	| Aug, 2013                                                	|
| Component Version:   	| 2013\_08\_21(build 9)                                 	|
| Product and Version: 	| Oracle WebCenter Content Server 11g                      	|
| Author:              	| Adao.Junior                                              	|
| Info:                	| [Oracle A-Team Chronicles](http://www.ateam-oracle.com/) 	|
|                      	| [Content Rave Blog](http://blog.contentra.com)            |


Component Information
---------------------

This sample component is AS-IS based, without any kind of support.

The CenteraFileStoreProvider component extends the FileStoreProvider
thats extends the standard file store provider that ships with the 10gR3
and 11g core. The standard default provider is the mechanism used to
access all the files managed by the content server and in the
out-of-the-box version, the files are stored by the usual means.

The CenteraFileStoreProvider uses the XAM Interface to comunicate with
the Centera.

**XAM API & Library**

The XAM API package is intended for developers who are writing XAM code
and includes headers and link libraries for compiling code that uses the
XAM API. Support for both the C and Java APIs is included; Java support
is provided through the use of JNI (Java Native Interface) wrappers
around the C libraries.

**EMC Centera Vendor Interface Module**

The EMC Centera VIM package includes the runtime libraries necessary for
loading the Centera support module into a compiled XAM application.

**Public Internet EMC Centera Online Clusters connection sample
included:**

\* This list do not apply if you are not using the Public Centera
Cluster.

-   Should not be used for Proof of Concept (POC) testing for customers.
-   Should only be used for Integration Functional Testing.
-   Needs the port 3218 (TCP/UDP - inbound/outbound) open in your
    network (Oracle's network blocks this port).
-   EMC clean the environments every 60 days deleting all archived
    content.
-   If your pea file is not working, you probably need to download a new
    one from: https://community.emc.com/docs/DOC-1038

Installation Instructions:
--------------------------

Warning: The recomendation was you perform all necessary backups prior
to applying this component. For additional information see the *Content
Server Getting Started Guide* which contains information on System
Maintenance and Backup Strategies.

If needed, upgrade your FileStoreProvider. Please see the
FileStoreProvider documentation.

Install the CenteraFileStoreProvider component. Preferable using
Administration \> Component Management

Add the environment variable `XAM_VIM_PATH` to point to `/components/CenteraFileStoreProvider/lib/`

\* sample if using windows:
```sh
set XAM_VIM_PATH=c:\\oracle\\wcc\_domain\\ucm\\cs\\components\\CenteraFileStoreProvider\\lib\\windows-amd64\\*
```

\* sample if using linux:
```sh
export XAM_VIM_PATH=/oracle/wcc_domain/ucm/cs/components/CenteraFileStoreProvider/lib/linux64/*
```

\* sample if using solaris:
```sh
export XAM_VIM_PATH=/oracle/wcc_domain/ucm/cs/components/CenteraFileStoreProvider/lib/solaris64/*
```

For Linux and Solaris: Add the environment variable `LD_LIBRARY_PATH`
and PATH to point to `/components/CenteraFileStoreProvider/lib/`

\*\* path:
```sh
export PATH=$PATH:/oracle/wcc_domain/ucm/cs/components/CenteraFileStoreProvider/lib/linux64/*
```

\*\* ld\_library\_path:
```sh
export LD_LIBRARY_PATH=/oracle/wcc_domain/ucm/cs/components/CenteraFileStoreProvider/lib/linux64/*
```

You can include this environment variable in the Start Script of the
WebCenter Content

Change the xri String to point to your .pea file and Centera Address,
this could be done editing the `centerafilestoreprovider_environment.cfg`
file on installdir\\custom\\CenteraFileStoreProvider

\* sample connection string:
```sh
CenteraXRI=snia-xam://centera_vim!168.159.214.20?/apps/oracle/fmw/user_projects/wcc/ucm/cs/custom/CenteraFileStoreProvider/pea/c1armtesting.pea*
```

Enable the CenteraFileStoreProvider component

Restart the content server

Navigate to Administration\>Providers

Click the info link on DefaultFileStore

Click Edit

In the drop down select **Add New Rule**

Click **Edit Rule**

Enter **Centera** as the storage Rule

Select the **EMC Centera Storage** radio button

Click Ok at the bottom of the page.

Click Update

Restart the content server

(Optional)Publish Layouts and Schema Data(everything in the actions
menu)

On the Checkin form should appear a storage rule option list with the
Centera Option, any content with this rule will be archived on the
Centera pool defined. Remenber to make visible the field Storage Rule

How to Check if this Component is Installed:
--------------------------------------------

To check if this version is installed, make sure that this component is
enabled by looking at the "Enabled Component Details" section under
Administration:"Configuration for [Instance Name]" and that the version
of the component matches the version listed above.

How to Uninstall this Component:
--------------------------------

Disable and Uninstall this component. The content references to the
Centera will remain in the system for safe, you will need to clean
manually the tables CenteraFileCache and CenteraFileRef for complete
remove the data. Batch delete of the Centera Pool, should be done using
the Centera Console.

Compatibility
-------------

WebCenter Content 11gR1

Platforms (32 and 64): Windows, Linux and Solaris

JDK 1.6, 1.7 and 8

ATMOS 2.0.1, 2.1 requires XAM SDK 1.0 P3 (1.0.115) [Included in the
Component]

CentraStar 4.0.2, 4.1.x, 4.2 requires XAM SDK 1.0 P3 (1.0.115) [Included
in the Component]

Centera Virtual Archive (CVA) 1.1 requires XAM SDK 1.0 P3 (1.0.115)
[Included in the Component]

CentraStar 4.0.1 requires XAM SDK 1.0 P2 (1.0.103)

CentraStar 4.0 and bellow not supported

Release History:
----------------

-   2013\_08\_21(build 9) -
    -   Tested with WebCenter Content 11.1.1.8.
    -   Fixed the class path.
    -   Restored support for Java 1.6.
    -   Included the missing steps for the EMC Centera SDK.
    -   Added support for the Cloud Storage EMC Atmos CAS 2.1.
-   2012\_12\_08(build 8) -
    -   Removed requirement of external sdk. Single full-featured
        component.
    -   Updated with the Leap Year Issue patch from EMC.
    -   Added support for the Cloud Storage EMC Atmos CAS 2.0.1.
    -   Updated demo Centera Online Cluster pea files. (May 17, 2012)
-   2011\_10\_18(build 7) -
    -   Removed support for UCM 10gR3 and Java 1.5.
    -   Classes rebuilded with Java 1.7 (Backwards compatible to Java
        1.6).
    -   Rebuild to support the EMC Centera SDK for XAM 1.0 Patch 3 & VIM
        1.0 Patch 3 (1.0.115 - Jul 22, 2011).
    -   Added support for CentraStar 4.2 (4.2.0-3881-0-0).
    -   Added beta support for EMC Atmos CAS.
    -   WebCenter Content Rebranding.
-   2011\_07\_18(build 6) - Removed Debug code
-   2011\_07\_06(build 5) - Added support to be fully compatible to UCM
    10gR3 and Java 1.5
-   2011\_06\_22(build 4) - More Debug Code
-   2011\_05\_27(build 3) - Debug
-   2010\_11\_14(build 2) -
    -   Updated to use the FileCache to index.
    -   Updated to work with CentraStar 4.1.
    -   Old Centera SDK could be found here:
        https://updates.oracle.com/Orion/Services/download?type=readme&aru=8303583
-   2010\_11\_05(build 1) - Initial release

