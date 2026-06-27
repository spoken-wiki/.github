# Spoken Wiki

## Goal
This project aims to generate easy to consume videos created from english Wikipedia articles.

This project is currently online at [https://spoken.wiki/](https://spoken.wiki/)

## Repositories

List of repostitories used by Spoken Wiki.

### 🚀 apollo :: [repo](https://github.com/spoken-wiki/apollo)
The Apollo project is a backend service written in Deno that orchestrates the collection and generation of spoken wiki videos. It acts as a central controller, coordinating data flow between other services in the Spoken Wiki system.

### 🌐 athena :: [repo](https://github.com/spoken-wiki/athena)
The Athena project is a web application built with the Laravel PHP framework. It serves as the main user-facing portal for the Spoken Wiki system, providing features such as browsing, searching, and accessing generated spoken wiki videos.

### 🛠️ hephaestus :: [repo](https://github.com/spoken-wiki/hephaestus)
The Hephaestus project is a modular pipeline for generating spoken wiki videos from Wikipedia articles. It consists of several stages, each in its own subfolder, handling a specific part of the process.

### 😴 hypnos :: [repo](https://github.com/spoken-wiki/hypnos)
The Hypnos project is a backend service for managing and tracking the processing of Wikipedia articles and their associated video generation tasks.

### 🏗️ infra :: [repo](https://github.com/spoken-wiki/infra)
The Infra project provides infrastructure management and deployment scripts for the Spoken Wiki system. It organizes environment configuration, container orchestration, and provisioning for both development (dev) and production (prd) setups.

## Architecture

athena:
- Web interface
- Uses hypnos to get articles and videos

apollo:
- REST API interface
- Handles two types of work:
- - collect: get new articles from wikipedia
- - generate: triggers video generation process for articles without video (can run in the background)

hypnos:
- REST API interface
- Persistence layer interface, connects to postgresql database

hephaestus:
- REST API interface
- Pipeline to generate videos from articles


## Roadmap

### 🟢 Phase 1
Goals for the first phase:
- Development of an infrastructe the allows the automatic generation of videos based on Wikipedia articles
- Make the project available online

Phase finished on December, 2022.

### 🟡 Phase 2
Goals for the second phase:
- ✅ RSS Feed
- ✅ Remove chronos repo
- Change DB password
- Add hephaestus prefix to docker images
- Merge/reduce hephaestus services
- Make all repos public
- Setup a blog
- Improve audio generation (use other models)
- Test of multiple articles (check bellow)

### 🔴 Phase 3
Goals for the third phase:
- Setup of an Youtube account
- Automatic distruibuiton of videos via Youtube

### 🔴 Phase 4
Goals for the fourth phase:
- Integration with Instagram
- Integration with Twitter
- Integration with Facebook

## Test Articles

| Article Name | Words | Tested | Pass |
| :----------- | :---: | :----: | :--: |
| [Sakhsabay](https://en.wikipedia.org/wiki/Sakhsabay)                          | 510       | ✅ | ✅ |
| [Honda_CBR1000RR](https://en.wikipedia.org/wiki/Honda_CBR1000RR)              | 3 057     | ✅ | ❌ |
| [Perseverance_(rover)](https://en.wikipedia.org/wiki/Perseverance_(rover))    | 6 936     | ❌ | ❌ |
| [PlayStation_5](https://en.wikipedia.org/wiki/PlayStation_5)                  | 7 213     | ❌ | ❌ |
| [Horizon_Zero_Dawn](https://en.wikipedia.org/wiki/Horizon_Zero_Dawn)          | 8 029     | ❌ | ❌ |
| [Mona_Lisa](https://en.wikipedia.org/wiki/Mona_Lisa)                          | 11 191    | ❌ | ❌ |
| [Ian_Fleming](https://en.wikipedia.org/wiki/Ian_Fleming)                      | 11 271    | ❌ | ❌ |
| [Tesla_Model_3](https://en.wikipedia.org/wiki/Tesla_Model_3)                  | 13 910    | ❌ | ❌ |
| [Google](https://en.wikipedia.org/wiki/Google)                                | 17 382    | ❌ | ❌ |
| [Apollo](https://en.wikipedia.org/wiki/Apollo)                                | 28 886    | ❌ | ❌ |
| [Portugal](https://en.wikipedia.org/wiki/Portugal)                            | 31 202    | ❌ | ❌ |
| [The_Castle_(novel)](https://en.wikipedia.org/wiki/The_Castle_(novel))        |  5 654    | ❌ | ❌ |



