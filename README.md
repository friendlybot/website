# FriendlyBot Website

Simple static site.

## Manual Deployment

```console
user@host:website$ aws s3 sync ./src/ s3://www.friendlybot.io/ \
  --delete \
  --dryrun
user@host:website$ aws cloudfront create-invalidation \
  --distribution-id=$(aws cloudfront list-distributions | jq -r '.DistributionList.Items[] | select(.Aliases.Items[0]=="www.friendlybot.io") | .Id') \
  --paths=/*
```

