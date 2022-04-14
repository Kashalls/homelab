---
template: main.html
---

# Synology DiskStation DS412+

## A Child's Dream

Released sometime in 2012, I bought the DS412+ with my parent's money. Originally as a christmas present to hold some of the projects and photos I took during my photography ambition, this nas has served me well into 2022 (10 years later!). Sometime in 2017, I upgraded this bad boy to use 4 gigabytes of DDR3 ram and eventually configured LACP on both of it's gigabit ports.

## Configuration

I'm running DSM Version `6.2.4-25556 Update 5` with a single `BTRFS` Storage Pool. In this configuration, I expect to have `5.23 TB` available running in a `RAID 5 (with data protection)`.

|  Number  |   Drive Size   |  Type  |  Model             |
|:--------:|:--------------:|:------:|:------------------:|
| Drive 1  | 1.82 TB        | HDD    | ST2000DM008-2FR102 |
| Drive 2  | 1.82 TB        | HDD    | ST2000DM008-2FR102 |
| Drive 3  | 1.82 TB        | HDD    | ST2000DM008-2FR102 |
| Drive 4  | 1.82 TB        | HDD    | ST2000DM008-2FR102 |

## 3-2-1 Backup

### AWS Glacier

Using Synology's `Glacier Backup` application, I backup family documents and photos almost daily to [AWS Glacier](https://aws.amazon.com/s3/storage-classes/glacier/). I store around 1 TB of files and it costs `$3.50` ($0.0036 per GB / Month) +/- related bandwidth fees. I don't expect to ever pull from the backup more than 1 or 2 times a year for testing.

### Google Storage

Anything `AWS Glacier` doesn't pickup, gets shoved into my personal google storage. I currently simp for Google with my `Pixel 6 Pro` as my daily phone. I already previously paid for their `Standard 200GB` advertised on [Google One](https://one.google.com), I simply upgraded to their `Premium 2TB` plan for $100/year. Every 3 days, using Synology's `Cloud Sync`, we push compressed zip's into my google drive only if the file's hash is modified.

### Local Storage

This one is just incase I need to take the nas offline or need to take a copy of the nas with me to a family member's house. I use one of these [Seagate 8TB Expansion EXT Drives](https://www.bhphotovideo.com/c/product/1268951-REG/seagate_steb8000100_8tb_expansion_desktop.html) which makes it really nice to take it anywhere.

## Problems For Future Me

### Recent Problems

I have found `Drive 2` to be constantly reporting bad sector counts quite too often, so I am currently researching to see if it is just an isolated case or just really bad QA on these model of drives. **These drives are by no means meant to be running in this setup.**

### Future Plans

Following `Level1Techs` recent video, even though this uses software raid, I have decided that I am going to retire my Synology NAS to my grandparents as a off-site backup.

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/l55GfAwa8RI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
