---
share: true
dg-publish: true
---
# Drafts Things Action
Updated `07232022-142511`

- [**Drafts Directory**](https://directory.getdrafts.com/a/2BJ)
- [GitHub Issue](https://github.com/extratone/drafts/issues/79)
- [**Gist**](https://gist.github.com/8e70d1c53bbf9daa5eb36e697bafa6ac)
- [Repo File](https://github.com/extratone/drafts/blob/main/actions/ActionsTemplate.md)
- [Things](things:///show?id=EaRLKrL8Yh99pMAmuw7dBj)
- [Things](things:///show?id=9uNT3LG88AwEVhR7hrXDyq)
- [Simplenote Local](simplenote://note/70f69966c6994b4f9464950d34a8fdb9)
- [Simplenote Publish](http://simp.ly/publish/FcZg5S)
- [WTF](https://davidblue.wtf/drafts/4BE7BE82-1E9B-400C-B913-AD6FFAD4F5DE.html)

<script src="https://gist.github.com/extratone/8e70d1c53bbf9daa5eb36e697bafa6ac.js"></script>

### Dev

`⌥ ⌘ T`

```
things:///add?title=Drafts Things Action&notes=[](thing)&tags=[](thingstags)&list-id=LMLw5mRdV3y7BWkuZUJKu6&heading=Arrival&creation-date=[](creation_date)
```

## Description

Creates an item in Things with the following parameters:

- `title` = [display_title]
- `notes` = (The Draft body with a prepended DavodTime timestamp.)
- `tags` = Drafts, [tags]
- `list-id` = LMLw5mRdV3y7BWkuZUJKu6
- `heading` = Arrival
- `creation-date` = [creation_date]

Upon returning to Drafts, `x-things-id` is inserted at the cursor in the following format:
`[Things]([callback_x-things-id])`


## Directory Description

See this [GitHub Issue](https://github.com/extratone/drafts/issues/79) in my Drafts-specific Repository.

Creates an item in Things with the following parameters:

- `title` = [display_title]
- `notes` = (The Draft body with a prepended DavodTime timestamp.)
- `tags` = Drafts, [tags]
- `list-id` = LMLw5mRdV3y7BWkuZUJKu6
- `heading` = Arrival
- `creation-date` = [creation_date]

Upon returning to Drafts, `x-things-id` is inserted at the cursor in the following format:
`[Things]([callback_x-things-id])`

---

## JS

```js
```

---

## Install

```
drafts://action?data=%7B%22uuid%22:%2236905936-5936-464A-835A-18B633EC60E4%22,%22steps%22:%5B%7B%22platforms%22:3,%22data%22:%7B%22name%22:%22thing%22,%22template%22:%22%5B**%5B%5Bdisplay_title%5D%5D**%5D(%5B%5Bdraft_open_url%5D%5D)%5Cn---%5Cn%5B%5Bbody%5D%5D%22,%22templateType%22:%22legacy%22%7D,%22type%22:%22defineTemplateTag%22,%22isEnabled%22:true,%22uuid%22:%2291E885DA-3AAB-4419-8C29-75B48291CEE5%22%7D,%7B%22platforms%22:3,%22data%22:%7B%22template%22:%22Drafts,%20%5B%5Btags%5D%5D%22,%22name%22:%22thingstags%22,%22templateType%22:%22legacy%22%7D,%22type%22:%22defineTemplateTag%22,%22isEnabled%22:true,%22uuid%22:%229EE5B4A2-6BBE-4A99-9DF3-DF2434A42666%22%7D,%7B%22platforms%22:3,%22data%22:%7B%22template%22:%22things:%5C/%5C/%5C/add?title%3D%5B%5Bdisplay_title%5D%5D%26notes%3D%5B%5Bthing%5D%5D%26tags%3D%5B%5Bthingstags%5D%5D%26list-id%3DLMLw5mRdV3y7BWkuZUJKu6%26heading%3DArrival%26creation-date%3D%5B%5Bcreation_date%5D%5D%22,%22encodeTags%22:%22true%22,%22waitForResponse%22:%22true%22%7D,%22type%22:%22callbackUrl%22,%22isEnabled%22:true,%22uuid%22:%22A48F176F-E676-4825-8D0C-A5659DDA853D%22%7D,%7B%22platforms%22:3,%22data%22:%7B%22template%22:%22%5BThings%5D(things:%5C/%5C/%5C/show?id%3D%5B%5Bcallback_x-things-id%5D%5D)%22,%22templateType%22:%22legacy%22%7D,%22type%22:%22insertText%22,%22isEnabled%22:true,%22uuid%22:%227E0C5BF0-2EE7-4F96-A9E7-0C45DAB443C1%22%7D%5D,%22backingPlatforms%22:3,%22shortName%22:%22%22,%22shouldConfirm%22:false,%22disposition%22:0,%22keyCommand%22:%7B%22optionKey%22:true,%22input%22:%22T%22,%22controlKey%22:false,%22commandKey%22:true,%22type%22:%22action%22,%22discoverabilityTitle%22:%22Drafts%20Things%22,%22shiftKey%22:false%7D,%22logLevel%22:2,%22groupDisposition%22:0,%22notificationType%22:2,%22tintColor%22:%22blue%22,%22actionDescription%22:%22Creates%20an%20item%20in%20Things%20with%20the%20following%20parameters:%5Cn%5Cn-%20%60title%60%20%3D%20%5Bdisplay_title%5D%5Cn-%20%60notes%60%20%3D%20(The%20Draft%20body%20with%20a%20prepended%20DavodTime%20timestamp.)%5Cn-%20%60tags%60%20%3D%20Drafts,%20%5Btags%5D%5Cn-%20%60list-id%60%20%3D%20LMLw5mRdV3y7BWkuZUJKu6%5Cn-%20%60heading%60%20%3D%20Arrival%5Cn-%20%60creation-date%60%20%3D%20%5Bcreation_date%5D%5Cn%5CnUpon%20returning%20to%20Drafts,%20%60x-things-id%60%20is%20inserted%20at%20the%20cursor%20in%20the%20following%20format:%5Cn%60%5BThings%5D(%5Bcallback_x-things-id%5D)%60%22,%22keyUseIcon%22:false,%22icon%22:%22checkbox-active%22,%22visibility%22:480,%22backingIsSeparator%22:false,%22groupUUID%22:%22C6035177-21BF-4B32-AEAB-4739D6B46D63%22,%22assignTags%22:%5B%5D,%22name%22:%22Drafts%20Things%22%7D
```