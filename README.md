This role pip-installs aws cli, creates a dedicated user account, `s3_sync_agent_linux_username`, and configures a cron task to sync files from `s3_sync_source_location` to `s3_sync_path`. AWS credentials need to allow access to `s3_sync_bucket`/`s3_sync_folder`.

~~~
# defaults/main.yml
s3_sync_agent_homedir: "/home/{{ s3_sync_agent_linux_username }}"
s3_sync_agent_linux_username: s3backup
s3_sync_aws_access_key_id: secret_id
s3_sync_aws_cli_bin_location: /usr/local/bin/aws
s3_sync_aws_region: us-west-2
s3_sync_aws_secret_access_key: secret_key
s3_sync_bucket: mybucket
s3_sync_folder: path/to/my/bucket/backup/folder/
s3_sync_source_location: /backup

s3_sync_cron:
  minute: '7'
  hour: '0'
  day: '*'
  month: '*'
  weekday: '*'

~~~
