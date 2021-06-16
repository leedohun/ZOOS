ZConverter OCI Object-Storage (ZOOS)
============
> Before You Begin

> Prepare

> How to Use ZOOS Command Line

## Before You Begin

Before using ZOOS, oci-cli must be installed.

> Linux
```script
bash -c "$(curl -L https://raw.githubusercontent.com/oracle/oci-cli/master/scripts/install/install.sh)"
```

>Windows (PowerShell)
```script
powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/oracle/oci-cli/master/scripts/install/install.ps1'))"
```
### You only need to enter Enter or Y when installing.

## Prepare

To use ZOOS, you need to prepare the environment to run and download ZOOS.

### OCI SETTING

##### You should prepare user-ocid, tenancy-ocid and region in the Oracle console window.
```script
oci setup config
```
![config](https://objectstorage.ap-seoul-1.oraclecloud.com/p/F_2ujJOp0frEQ_GOeqkaWxov08LQTfSE3RQP7D3vHzDtam_s0pEWrz6ROvM9ZmHp/n/cnfyb6dq82p9/b/OCI_Terraform_reference/o/config.png)

### Registering an api-key

You register the api-key-public-pem created when you create the config with the user account you used.
1. **Enter the User menu.**
![Account User](https://objectstorage.ap-seoul-1.oraclecloud.com/p/ZOKRkEnpLI3IHFs80_aW3Ciy6HTd-skSGzNuZ2fzSywbU6MSdWf2U5dOxN9ID_1X/n/cnfyb6dq82p9/b/test_bucket/o/Select%20Users.png)

2. **Choice User Account Name to use.**

      ![Account Users](https://objectstorage.ap-seoul-1.oraclecloud.com/p/Mj3mBoNkl6NWjDLhtxfe63J-4Lq2r6VyKoZIxFOYEus_uUxy4KO4yL8-1O-EXKAX/n/cnfyb6dq82p9/b/test_bucket/o/Account%20Users.png)

3. **Click api-key in the lower left resource**

      ![Api-Key](https://objectstorage.ap-seoul-1.oraclecloud.com/p/mZP_d9myS9aL_V3lTFWWtr4qU9puC_l3rkUGxclnR-aTUGedd4YEn4faWMU3jww8/n/cnfyb6dq82p9/b/test_bucket/o/Select%20API.png)

4. **Click add api key**

      ![Api-Key](https://objectstorage.ap-seoul-1.oraclecloud.com/p/wTwhMhRpk_lhRDXu-4RnSznJrNTFkIEI53rONT3YTeCh-QFG-t-NSEeYzvQ2MSQ9/n/cnfyb6dq82p9/b/test_bucket/o/Add%20API%20Key.png)

5. **upload your public key**  

![upload](https://objectstorage.ap-seoul-1.oraclecloud.com/p/i8CUXQXBwBJAHFE9V76rM50j2lGoQqzAIKy6zk3M3ACeSB5-x2UO0tci5ysMhCCE/n/cnfyb6dq82p9/b/OCI_Terraform_reference/o/add_api_key.png)

6. **Select the public_key created in the config step.**

![choice_public_file](https://objectstorage.ap-seoul-1.oraclecloud.com/p/OlopftyGkfi0o1ceLdXEAYl80aLlrLFN-RC9MLwCCeesfz2FcU931I1J-qkPc5dp/n/cnfyb6dq82p9/b/OCI_Terraform_reference/o/choice_public_key.png)

**Result**
![result_upload_api_key](https://objectstorage.ap-seoul-1.oraclecloud.com/p/q66rxKKJHqZtb_CXELkstFoidD0MQWC9YuTwZZgCoo1LHDRz_WAQOoYFs7tuXc96/n/cnfyb6dq82p9/b/OCI_Terraform_reference/o/finish_add_api_key.png)

## How to Use ZOOS Command Line

### Download ZOOS
>Linux
여기 링크
>Windows
여기 링크

1. **Create Bucket**
* Linux
```script
python3 ZOS.py bucket_create {tenancy-ocid} {bucket-name} {Archive or Standard}
```
* Windows
```script
ZOS.exe file_upload {bucket-name} {file-path} {Archive or Standard}
```

2. **file upload**
* Linux
```script
python3 ZOS.py file_upload {bucket-name} {file-path} {Archive or Standard}
```
* Windows
```script
ZOS.exe file_upload {bucket-name} {file-path} {Archive or Standard}
```
3. **folder upload**
* Linux
```script
python3 ZOS.py folder_upload {bucket-name} {dir-path} {Archive or Standard}
```
* Windows
```script
ZOS.exe folder_upload {bucket-name} {dir-path} {Archive or Standard}
```
4. **file copy**
* Linux
```script
python3 ZOS.py file_copy {bucket-name} {file-name} {target-bucket-name} {target-storage-tier : Archive or Standard}
```
* Windows
```script
ZOS.exe file_copy {bucket-name} {file-name} {target-bucket-name} {target-storage-tier : Archive or Standard}
```
6. **file copy**
* Linux
```script
python3 ZOS.py file_download {bucket-name} {file-name} {download-file-path}
```
* Windows
```script
ZOS.exe file_download {bucket-name} {file-name} {download-file-path}
```
7. **folder download**
* Linux
```script
python3 ZOS.py folder_download {bucket-name} {download-dir-path}
```
* Windows
```script
ZOS.exe file_download {bucket-name} {file-name} {download-file-path}
```

8. **file download using url**
* Linux
```script
python3 ZOS.py file_url {bucket-name} {file-name} {url-object-name} {access-type} {time-expires}
```
* Windows
```script
ZOS.exe file_url {bucket-name} {file-name} {url-object-name} {access-type} {time-expires}
```
