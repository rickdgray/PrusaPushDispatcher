# Prusa Push Notif Dispatcher
Push status updates from your Prusa 3D printer right to your phone!

## Pushover
You will need an account at [Pushover](https://pushover.net/) to be able to run this. Be sure to also create an application and get the associated `API Token/Key` as well.

## Settings
Once you create an account and have both a `User Key` and an `API Token/Key`, you need to pass them in at runtime. The optional settings are:

* PushoverUserKey
* PushoverAppKey
* PollRateInMinutes (optional, defaults to 60)

## Deploying
Simply run with the necessary environment variables set and the image specified.
```bash
docker run -itd --restart unless-stopped --env Settings__PushoverUserKey='abcd1234' --env Settings__PushoverAppKey='abcd1234' ghcr.io/rickdgray/prusapushdispatcher:main
```

## Building
Projects in .NET have an unusual folder structure, so when building we must both specify the context to be at the root of the solution, but also specify the location of the `dockerfile`.
```bash
docker build -f .\PrusaPushDispatcher\Dockerfile .
```
