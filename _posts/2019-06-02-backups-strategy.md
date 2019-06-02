---
layout: post
title: Backup the Backup of the Backup
---

TLDR: Just backup your data. No excuses.

<amp-img width="713" height="273" layout="responsive" src="https://imgs.xkcd.com/comics/backups.png" alt="Image from XKCD making a joke about how he has circular backups" attribution="From https://xkcd.com/1718/"></amp-img>

### Why?

Imagine you dropped your phone and now it is a complete loss, what data would you lose? Your answer should be nothing
or almost nothing. This might be a hypothetical situation, but there is always the possibility that something goes
wrong and a device ends up broken or dead. The idea is that you could purposefully hit your phone with a sledgehammer
and the only thing you lost is lots of money. Nobody wants to go on a lovely vacation or take pictures of a loved one
only to have something happen to your phone only to lose all of your digital memories. 

### How?

There are basically an infinite number of options that are available in terms of backing up your devices. I will lay out
my strategy with two of those options. Regardless of what you choose, the way to make sure you stick to the backup strategy
is to make sure that it is an automated process, so that way even if you forget there is little risk of loss.

#### Cloud

<amp-img width="740" height="236" layout="responsive" src="https://imgs.xkcd.com/comics/the_cloud.png" alt="Image from XKCD making a joke about how the cloud is a box in a room" attribution="From https://xkcd.com/908/"></amp-img>

The easiest and cheapest option to backup your data is to store it in the cloud. While most people are often nervous about
putting their data in the cloud, odds are you already are. Do you sync your contacts with [Google](https://contacts.google.com)
or [Facebook](https://www.facebook.com/help/1041444532591371/?helpref=hc_fnav)? Congratulations, you already made a step
towards keeping things safely backed up in the cloud. If you have an apple product, Apple kindly stores your contacts in
[iCloud](https://www.icloud.com) along with a bunch of other things by default. This is the easiest step to take as your
phone does a good job of automating a few types of backup for you and is generally enabled by default.

If you want to back up your photos and do not mind [Google](https://www.google.com/photos/about/) sniffing through all your
photos, they will gladly store an unlimited amount of photos free of charge. If you do mind, there is always the option
to [increase your iCloud storage](https://support.apple.com/en-us/HT201318) or I hear [OneDrive from Microsoft](https://onedrive.live.com/about/en-us/)
and [BackBlaze](https://www.backblaze.com/cloud-backup.html) are decent products. I am sure there are plenty of other cloud
options, but those are the big consumer ones that are likely to stick around for a while. If you are on the savvy side,
there are a
few enterprise options from [AWS](https://aws.amazon.com/s3/), [Google Cloud](https://cloud.google.com/storage/), [BackBlaze](https://www.backblaze.com/b2/cloud-storage.html),
and [Azure](https://azure.microsoft.com/en-us/services/storage/) for those of you with a [Network Attached Storage](https://en.wikipedia.org/wiki/Network-attached_storage) (NAS)
setup like me that needs to be backed up.

Speaking of NAS, I back up the shared folders of my [Synology](https://www.synology.com/en-us) to Google's [Nearline](https://cloud.google.com/storage/archival/)
storage product. It is a very cost effective solution and the [Cloud Sync](https://www.synology.com/en-us/dsm/feature/cloud_sync)
app from Synology can connect to it with very little setup.

#### NAS or HDD

For those of you with a NAS at home, this is more redundant, but even if you only have an external drive the same applies.
Make a backup of your computer early and often to local storage, Apple has a built-in utility called [Time Machine](https://support.apple.com/en-us/HT201250)
that will automatically backup your entire computer to a drive. Before I got a Synology, I would bring a WD Passport with
me on vacation and every night I would empty the SD card to my laptop and then after the files were organized I would transfer
them to the Passport. The key is to make sure that the data is in at least two separate places before you delete anything.

For me, the phone is the only thing that I do not upload to my laptop because it already goes to the cloud. Although, I
recently started using [Resilio Sync](https://www.resilio.com/individuals-sync/?) (formally BitTorrent Sync) to transfer
pictures and video from my phone straight onto the Synology since Apple does not yet support either AFP or SMB from iOS natively.