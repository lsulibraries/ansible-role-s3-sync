This role pip-installs aws cli, creates a dedicated user account, `backup_agent_username`, and configures a cron task to sync files from `backup_location` to `s3_path`. AWS credentials need to allow access to `s3_path`.

~~~
# defaults/main.yml
aws_access_key_id: secret_id
aws_secret_access_key: secret_key
aws_region: us-west-2

backup_agent_username: s3backup
backup_agent_homedir: "/home/{{ backup_agent_username }}"

s3_path: s3://path/to/my/bucket/backup/folder
backup_location: /backup

s3_sync_cron:
  minute: 5
  hour: '0'
  day: '*'
  month: '*'
  weekday: '*'
~~~
