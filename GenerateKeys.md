# Introduction #

Generating the required certificates and key stores


# Details #

  * Generate the keys pair for the server:
> > keytool -genkeypair -keystore /tmp/symbeeserver.keystore -alias symbee -storepass symbee

  * Generate the certificate for client
> > keytool -exportcert -keystore /tmp/symbeeserver.keystore -file /tmp/symbee\_client.cert -alias symbee -storepass symbee


  * Generate the trustore for client
> > keytool -importcert -keystore /tmp/symbee.truststore -file /tmp/symbee\_client.cert -alias symbee -storepass symbee
