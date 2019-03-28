# Setup AWS Config

```
$ cat ~/.aws/credentials 
[default]
aws_secret_access_key = SECRET_ACCESS_KEY
aws_access_key_id = ACCESS_KEY_ID

```

# Steps To Update BerryNet Repository 

1. Create `<git-to-s3>/git_to_s3_temp/` (indicated in `settings.py`)
1. Put new files into temp dir
  1. Update local repository

      ```
      $ dput berrynet
      ```

  1. Copy updated files from repository to temp dir.
  1. Example result:

      ```
      $ tree git_to_s3_temp/
      git_to_s3_temp/
      └── stretch
          ├── berrynet_3.4.0-1_all.deb
          ├── berrynet_3.4.0-1_amd64.changes
          ├── berrynet-dashboard_3.4.0-1_all.deb
          ├── InRelease
          ├── Packages
          ├── Packages.bz2
          ├── Packages.gz
          ├── Packages.xz
          ├── python3-berrynet_3.4.0-1_all.deb
          ├── Release
          ├── Release.gpg
          └── Sources.gz
    
      1 directory, 12 files
      ```
      
1. Run uploader (`git_to_s3.py`)
  * Uploader will upload dirs and files onto S3 indicated bucket.
1. Go to S3 bucket and re-make it public
  * Click stretch
  * Click Actions
  * Click Make public
