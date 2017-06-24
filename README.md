SgxCryptoFile
=============

Introduction
------------

SgxCryptoFile is an application for encrypting and decrypting HLS chunks using Intel SGX.

The encryption and decryption are implemented based on T_CRYPTO library provided by Intel SGX SDK. 

It uses AES-128-GCM algorithm and it was written in pure C language.

In addition, it generates an encryption/decryption benchmark time.

Actually, the key is hardcoded inside the enclave.


Build the SgxCryptoFile
--------------------
###Prerequisites:
- Ensure that you have the following required operating systems: 
  Ubuntu\* Desktop-14.04-LTS 64bits

- Install [Intel(R) SGX SDK for Linux* OS](https://github.com/01org/linux-sgx) and follow all the instructions;

- Use the following command to install the required tools to build SgxCryptoFile application: 
```
  $ sudo apt-get install nasm
```

###Build the SgxCryptoFile
The following steps describe how to build the SgxCryptoFile application.

-  Build the project with the prepared Makefile: 
    a. Hardware Mode, Debug build:
```
  $ make SGX_MODE=HW SGX_DEBUG=1
```
    b. Hardware Mode, Pre-release build:
```
  $ make SGX_MODE=HW SGX_PRERELEASE=1
```

    c. Hardware Mode, Release build:
```
  $ make SGX_MODE=HW
```

    d. Simulation Mode, Debug build:
```
  $ make SGX_DEBUG=1
```

    e. Simulation Mode, Pre-release build:
```
   $ make SGX_PRERELEASE=1
```

    f. Simulation Mode, Release build:
```
   $ make
``` 

- To clean the files generated by previous `make` command, enter the following command: 
```
  $ make clean
```

Run the SgxCryptoFile
--------------------
###Encrypt File
To encrypt a file, enter the following command:
```
$ ./sgxCryptoFile -e -i [INPUT_FILE] -o -i [OUTPUT_FILE]
```

To decrypt a file, enter the following command:
```
$ ./sgxCryptoFile -d -i [INPUT_FILE] -o -i [OUTPUT_FILE]
```
