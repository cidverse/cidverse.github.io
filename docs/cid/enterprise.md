# Proxy / CA Certificates

Enterprise environments often have unique requirements such as a proxy or self-signed certificates.

With `CID` you can configure these settings in a few simple steps globally for all tools used within the CI workflow.

## Certificates

You must provide `CID` with both the `ca-bundle.crt` and the `keystore.jks`.

### Format: ca-bundle.crt

> A certificate bundle that contains one or more root CA certificates, supported by most unix applications.

TODO: ...

1. Copy the `ca-bundle.crt` file into the following target directory, depending on your os.

Unix:
```bash
$HOME/.cache/cid/certs/ca-bundle.crt
```

Windows:
```powershell
%AppData%\Local\cid\certs\ca-bundle.crt
```

*If the directories are missing, create them.*

### Format: keystore.jks

> A Java KeyStore, a certificate bundle for java applications.

The following steps describe how to import the self-signed root CA into an existing java keystore, which can be found in your JDK installation:

1. Change the directory to the bin directory of your JDK installation, for example:

```bash
cd /usr/lib/jvm/coretto/bin
```

2. Run the following command to import the self-signed root CA into the keystore:

```bash
keytool -import -trustcacerts -storepass changeit -alias <companyName> -file <path/to/companyName>.crt -keystore <path/to/jdk>/lib/security/cacerts
```

3. Verify that the root CA has been successfully imported into the Java Keystore by using the following command:

```bash
keytool -list -v -keystore <path/to/jdk>/lib/security/cacerts
```

You should now see the root CA listed under the trustedCertEntry section. The Java applications that use this keystore will now trust the self-signed root CA.

4. Copy the `lib/security/cacerts` file into the following target directory, depending on your os.

Unix:
```bash
$HOME/.cache/cid/certs/keystore.jks
```

Windows:
```powershell
%AppData%\Local\cid\certs\keystore.jks
```

*If the directories are missing, create them.*

## Proxy

CID will respect the environment set in the following variables:

- HTTP_PROXY
- HTTPS_PROXY
- NO_PROXY

## Cert Access

*If you are using a prebuilt workflow you can ignore this section.*

Some environment like GitLab require you to copy the certificates into the project directory first, to mount them in other containers later.
In this case you need to set `CID_CERT_MOUNT_DIR=$CI_PROJECT_DIR/.tmp/certs`
