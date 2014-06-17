CenteraFileStoreProvider-XAM
============================

EMC Centera FileStore Provider for Oracle WebCenter Content (UCM), using XAM SDK
```html
<!DOCTYPE html>
<html id="home" lang="en">
<head>
<meta charset=utf-8 />
<meta name="viewport" content="width=620" />
<style type="text/css">
  /* <![CDATA[ */
	body { font-family: sans-serif;	}
	*.error { font-family: monospace; margin-left: 1em; }
	*.table-header { font-weight: bold }
	h2 { font-size: 14pt }
  /* ]]> */
</style>

<title>CenteraFileStoreProvider Component</title>
</head>

<body>
<h1>CenteraFileStoreProvider Component</h1>
<table border="0" summary="">
	<tr>
		<td class="table-header">Date:</td>
		<td>Aug, 2013</td>
	</tr>
	<tr>
		<td class="table-header">Component Version:</td>
		<td>2013_08_21(build 9)</td>
	</tr>
	<tr>
		<td class="table-header">Product and Version:</td>
		<td>
			Oracle WebCenter Content Server 11g
		</td>
	</tr>
	<tr>
		<td class="table-header">Author:</td>
		<td>
			Adao.Junior@oracle.com
		</td>
	</tr>
		<tr>
		<td class="table-header">Info:</td>
		<td class="info">
			</p><a href="http://www.ateam-oracle.com/">Oracle A-Team Chronicles</a></p><a href="http://blog.contentra.com">Content Rave Blog</a>
		</td>
	</tr>	
	<img src='data:image/png,%89PNG%0D%0A%1A%0A%00%00%00%0DIHDR%00%00%00%A8%00%00%00%21%01%03%00%00%00w%3Ar%E7%00%00%00%01sRGB%00%AE%CE%1C%E9%00%00%00%04gAMA%00%00%B1%8F%0B%FCa%05%00%00%00%06PLTE%D5%D5%D5%FF%FF%FF%B7%B5%AB%C3%00%00%00%02tRNS%FF%00%E5%B70J%00%00%00%09pHYs%00%00%0E%C3%00%00%0E%C3%01%C7o%A8d%00%00%01%10IDAT%28%CF%85%D2%B1N%C40%0C%06%E0%3F%A4j%84%40%0A%23%C3%E9%0E%DE%00%89%85%E1%A4%BE%CA%3D%02O%40-%B10%DE%C8%E3%F8%26V%1E%21%7D%83%B0%DD%80%1A%EC%14%9A%96%2B%22K%E2O%1E%EC%D8HK%07%7Fhpr%05%C0%02H%D1%26%B8%28%0F%B6%13%0D%A2%B6%E8%CD%99%A5J%D4%24%CA%1A%B2%EE%ACeG%29%1A%89%A3%99%29g5%AA%945%D8gv%21%B1%EA%BB%AA%99%AA%94%81%FD%5C%F7%8B%2A%05%FC%28T%3F%82%7Dcw%A1%1Ap%A5%8AQ%BDh%3B%E8uN%97%FA%B8%F6%E9%E5%5B%FB%A2%95O%97%A7%8A%99%B6Sm%06%7D%18%B5%F2%FDJ%F5%CE%E0s%FB%8F%D6%BE_%17mhP%A7%BA%E9%B2%02%8D%B6%ACz.%81%E8%A3%C1q%A2%AF%8B%1A%B3%92%2AcSt%A7%2A%B3%88%7D%D1pl%E1%3B%FE%A5%3CjHE%29%8A%1E%0E%A2%FC%24%ED%27%1D%23%D5%08%0D%1Cu%C1%00%5B%E8J%91%7E%3Fh-%2Bt%CB%F2Z%9D%28a%9A%5B%0Dz%CFX%DE%D4%2F%A8%18g%FD%A7%7EpN%00%00%00%00IEND%AEB%60%82' align='right' />

</table>
<h2>Component Information</h2>

<p>This sample component is AS-IS based, without any kind of support.</p>

<p>The CenteraFileStoreProvider component extends the FileStoreProvider thats extends the standard file store provider that
ships with the 10gR3 and 11g core. The standard default provider is the mechanism used
to access all the files managed by the content server and in the out-of-the-box
version, the files are stored by the usual means.</p>

<p>The CenteraFileStoreProvider uses the XAM Interface to comunicate with the Centera.</p>

<b>XAM API & Library</b>
<p>The XAM API package is intended for developers who are writing XAM code and includes headers and link libraries for 
compiling code that uses the XAM API. Support for both the C and Java APIs is included; Java support is provided through 
the use of JNI (Java Native Interface) wrappers around the C libraries.</p>

<b>EMC Centera Vendor Interface Module</b>
<p>The EMC Centera VIM package includes the runtime libraries necessary for loading the Centera support module into a compiled XAM application.</p>

<b>Public Internet EMC Centera Online Clusters connection sample included: </b>
<p>* This list do not apply if you are not using the Public Centera Cluster.</p>
<ul>
	<li>Should not be used for Proof of Concept (POC) testing for customers.</li>
	<li>Should only be used for Integration Functional Testing.</li>
	<li>Needs the port 3218 (TCP/UDP - inbound/outbound) open in your network (Oracle's network blocks this port).</li>
	<li>EMC clean the environments every 60 days deleting all archived content.</li>	
	<li>If your pea file is not working, you probably need to download a new one from: https://community.emc.com/docs/DOC-1038</li>	
</ul>
	
<h2>Installation Instructions:</h2>
<p>Warning: The recomendation was you perform all necessary backups prior to applying this component. For additional information see the
<em>Content Server Getting Started Guide</em> which contains information on System Maintenance and
Backup Strategies.
</p>

<p>If needed, upgrade your FileStoreProvider. Please see the FileStoreProvider documentation.</p>
<p/>
<p> Install the CenteraFileStoreProvider component. Preferable using Administration > Component Management </p>
<p> Add the environment variable XAM_VIM_PATH to point to /<csdir>/components/CenteraFileStoreProvider/lib/<platform> </p>
<p> <i>   * sample if using windows: set XAM_VIM_PATH=c:\oracle\wcc_domain\ucm\cs\components\CenteraFileStoreProvider\lib\windows-amd64\ </i> </p>
<p> <i>   * sample if using linux or solaris: export XAM_VIM_PATH=/oracle/wcc_domain/ucm/cs/components/CenteraFileStoreProvider/lib/linux64/ </i> </p>
<p> For Linux and Solaris: Add the environment variable LD_LIBRARY_PATH and PATH to point to /<csdir>/components/CenteraFileStoreProvider/lib/<platform> </p>
<p> <i>   ** path: export PATH=$PATH:/oracle/wcc_domain/ucm/cs/components/CenteraFileStoreProvider/lib/linux64/ </i> </p>
<p> <i>   ** ld_library_path: export LD_LIBRARY_PATH=/oracle/wcc_domain/ucm/cs/components/CenteraFileStoreProvider/lib/linux64/ </i> </p>
<p/>
<p> You can include this environment variable in the Start Script of the WebCenter Content </p>
<p/>
<p> Change the xri String to point to your .pea file and Centera Address, this could be done editing the centerafilestoreprovider_environment.cfg file on installdir\custom\CenteraFileStoreProvider </p>
<p> <i>   * sample connection string: CenteraXRI=snia-xam://centera_vim!168.159.214.20?/apps/oracle/fmw/user_projects/wcc/ucm/cs/custom/pea/c1armtesting.pea </i> </p>
<p> Enable the CenteraFileStoreProvider component </p>
<p> Restart the content server </p>
<p> Navigate to Administration>Providers </p>
<p> Click the info link on DefaultFileStore </p>
<p> Click Edit </p>
<p> In the drop down select <b>Add New Rule</b> </p>
<p> Click <b>Edit Rule</b> </p>
<p> Enter <b>Centera</b> as the storage Rule </p>
<p> Select the <b>EMC Centera Storage</b> radio button </p>
<p> Click Ok at the bottom of the page. </p>
<p> Click Update </p>
<p> Restart the content server </p>
<p> (Optional)Publish Layouts and Schema Data(everything in the actions menu) </p>
<p/>
<p> On the Checkin form should appear a storage rule option list with the Centera Option, any content with this rule will be archived on the Centera pool defined. Remenber to make visible the field Storage Rule </p>
<p/>
<h2>How to Check if this Component is Installed:</h2>
<p>To check if this version is installed, make sure that this component is enabled by looking at the
"Enabled Component Details" section under Administration:"Configuration for [Instance Name]" and that
the version of the component matches the version listed above.</p>

<h2>How to Uninstall this Component:</h2>
<p> Disable and Uninstall this component. The content references to the Centera will remain in the system for safe, you will need to clean manually the tables CenteraFileCache and CenteraFileRef for complete remove the data. Batch delete of the Centera Pool, should be done using the Centera Console.</p>

<h2>Compatibility</h2>


<p> WebCenter Content 11gR1 </p>
<p> Platforms (32 and 64): Windows, Linux and Solaris </p>
<p> JDK 1.6, 1.7 and 8</p>
<p> ATMOS 2.0.1, 2.1 requires XAM SDK 1.0 P3 (1.0.115) [Included in the Component]</p>
<p> CentraStar 4.0.2, 4.1.x, 4.2 requires XAM SDK 1.0 P3 (1.0.115) [Included in the Component]</p>
<p> Centera Virtual Archive (CVA) 1.1 requires XAM SDK 1.0 P3 (1.0.115) [Included in the Component]</p>
<p> CentraStar 4.0.1 requires XAM SDK 1.0 P2 (1.0.103)</p>
<p> CentraStar 4.0 and bellow not supported</p>

<h2>Release History:</h2>
<ul>
	<li>2013_08_21(build 9) -
		<ul>
			<li>Tested with WebCenter Content 11.1.1.8.</li>
			<li>Fixed the class path.</li>
			<li>Restored support for Java 1.6.</li>
			<li>Included the missing steps for the EMC Centera SDK.</li>	
			<li>Added support for the Cloud Storage EMC Atmos CAS 2.1.</li>					
		</ul>
	</li>
	<li>2012_12_08(build 8) -
		<ul>
			<li>Removed requirement of external sdk. Single full-featured component.</li>
			<li>Updated with the Leap Year Issue patch from EMC.</li>	
			<li>Added support for the Cloud Storage EMC Atmos CAS 2.0.1.</li>		
			<li>Updated demo Centera Online Cluster pea files. (May 17, 2012)</li>			
		</ul>
	</li>
	<li>2011_10_18(build 7) -
		<ul>
			<li>Removed support for UCM 10gR3 and Java 1.5.</li>
			<li>Classes rebuilded with Java 1.7 (Backwards compatible to Java 1.6).</li>
			<li>Rebuild to support the EMC Centera SDK for XAM 1.0 Patch 3 & VIM 1.0 Patch 3 (1.0.115 - Jul 22, 2011).</li>
			<li>Added support for CentraStar 4.2 (4.2.0-3881-0-0).</li>			
			<li>Added beta support for EMC Atmos CAS.</li>					
			<li>WebCenter Content Rebranding.</li>
		</ul>
	</li>
	<li>2011_07_18(build 6) - Removed Debug code</li>
	<li>2011_07_06(build 5) - Added support to be fully compatible to UCM 10gR3 and Java 1.5</li>
	<li>2011_06_22(build 4) - More Debug Code</li>
	<li>2011_05_27(build 3) - Debug</li>
	<li>2010_11_14(build 2) -
		<ul>
			<li>Updated to use the FileCache to index.</li>
			<li>Updated to work with CentraStar 4.1.</li>
			<li>Old Centera SDK could be found here: https://updates.oracle.com/Orion/Services/download?type=readme&aru=8303583</li>
		</ul>
	</li>
	<li>2010_11_05(build 1) - Initial release</li>
</ul>

</body>
</html>
