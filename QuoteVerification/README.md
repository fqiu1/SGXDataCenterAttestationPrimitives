Intel(R) Software Guard Extensions Data Center Attestation Primitives (Intel(R) SGX DCAP) Quote Verification Enclave Quick Start Guide
================================================

## Build QvE and dcap_quoteverify libraries, non-production only (for debug purposes). For production you must use Intel(R) signed QvE.
## Linux
Supported operating systems:
* Ubuntu* 16.04 LTS Desktop 64bits - minimal kernel 4.10
* Ubuntu* 16.04 LTS Server 64bits - minimal kernel 4.10
* Ubuntu* 18.04 LTS Desktop 64bits
* Ubuntu* 18.04 LTS Server 64bits

Requirements:
* make
* gcc
* g++
* ZIP
* bash shell

Pre-requisets:
* Intel(R) SGX SDK
* Intel(R) SgxSSL: Follow instructions in https://github.com/intel/intel-sgx-ssl (By default SgxSSL will automatically be downloaded and built). You should use latest OpenSSL to build SgxSSL.

### Build ``dcap_quoteverify.so`` and ``libsgx_qve.signed.so`` (Only for debug purposes):
````
$ cd QuoteVerification/
$ make
Generate a key and sign generated QvE enclave:
$ /opt/intel/sgxsdk/bin/x64/sgx_sign sign -key Enclave/<GENERATED_KEY>.pem -enclave qve.so -out libsgx_qve.signed.so -config Enclave/qve.config.xml
````

## Windows
Supported operating systems:
   * Windows* Server 2016 (Long-Term Servicing Channel)
   * Windows* Server 2019 (Long-Term Servicing Channel)

Requirements:
* Microsoft Visual Studio 2017 or newer.
* 7-Zip
* Perl    #for OpenSSL build
* NASM (Netwide Assembler)

Pre-requisets:
* Intel(R) SGX SDK.
* Intel(R) SgxSSL: Follow instructions in https://github.com/intel/intel-sgx-ssl (By default SgxSSL will automatically be downloaded and built). You should use latest OpenSSL to build SgxSSL.

### Build ``sgx_dcap_quoteverify.dll`` and ``qve.signed.dll`` (Only for debug purposes):
````
> Prepare SgxSSL by running script "prepare_sgxssl.cmd" in dcap_source\QuoteVerification
  > prepare_sgxssl.cmd x64 Debug
  > prepare_sgxssl.cmd x64 Release  

> In dcap_source directory, use Visual Studio to open ``SGX_DCAP.sln`` and build
````