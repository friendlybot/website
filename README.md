# FriendlyBot Website

Simple static site.

## Manual Deployment

```console
user@host:website$ aws s3 sync ./src/ s3://www.friendlybot.io/ \
  --delete \
  --dryrun
```

