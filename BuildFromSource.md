# Introduction #

This page lists the steps to build from the source.

# Details #
  * Generate the required SSL keys and certificates. Refer to GenerateKeys for to generate a test one using keytool

  * Checkout the source code from subversion
> > svn checkout http://symbee.googlecode.com/svn/trunk/ symbee-read-only

  * Edit the build properties in  trunk/src/build/build.properties

  * Run the ant build for build.xml located in trunk/src/build

  * The ant build will create the following files:
    1. The jar file needed for the server - trunk/dist/symbee\_server.jar
    1. The trunc/dist/jnlp directory that contains all the jars needed to host the java web start applet. Every jar in this directory is signed with the certificate specified in ${KEY\_STORE}
    1. The vd.jnlp file that can be used to launch the java webstart client. Please edit the jnlp file to suite your needs.