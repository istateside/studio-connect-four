# Studio Connect Four

This is Movable Ink Cartridge that goes with the Studio Connect Four app.

## Updating in dev

First, you need to have the `push-dev-cartridge` script. You can get it like so:

```
curl 'https://movableink-chef.s3.amazonaws.com/local-tools/push-dev-cartridge' > /usr/local/bin/push-dev-cartridge
chmod +x /usr/local/bin/push-dev-cartridge
```

(don't blindly download scripts, take a glance through it)

Then, you can push locally by running `push-dev-cartridge` from this directory. This will do two things:

* Uploads the directory to `movableink-cartridge-development` s3 bucket.
* Posts to your local rails server to register the updated cartridge.

## Deploying to production

You need to run a one-time setup to add gitolite as a remote:

```
bin/setup-deploy
```

Then you can deploy:

```
git deploy-production
```

This deploys your `master` branch to git.movableink.com and is the recommended deploy method.
