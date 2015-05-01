# Introduction #

This document describes the steps to deploy and run your own symbee server and client.


# Details #

  * Checkout the source code from subversion
> > svn checkout http://symbee.googlecode.com/svn/trunk/ symbee-read-only
  * Edit the VDProperties.properties file to appropriate values
> > MAIN\_SERVER\_PORT=<The Server Port that you want your symbee server to run>\n
> > MAIN\_SERVER\_HOST=<The hostname of the server that you will be running your symbee server on>
  * Build the deployable jar files. Refer to BuildFromSource for details
  * Edit the vd.jnlp as per your deployment details
  * Start the server. You can refer to src/scripts/startserver.sh for details.
> > nohup java  -Djavax.net.ssl.keyStore=$KEY\_STORE -Djavax.net.ssl.keyStorePassword=$KEY\_STORE\_PASS com.vayoodoot.server.MainServer <PORT NUMBER> &