# s2t
A pool of words in sed compatible form transform text file from Simplified Chinese (SC) to Traditional Chinese (TC)

## Usage
Use sed. (more to come....)

Good resource: http://www.grymoire.com/Unix/Sed.html

## How the wordings are ordered
The concept of sed is search and replace. But it is a top down search as well as some of the letter like (只) could transform to the same (只) or the (隻) depends on context. The order of the wording will then basically have the contextful words go first and clear 1-to-1 mapping pairs will go to the lower position. This way, some common pitfall of direct transform can be avoided (although not fully).

## Wording principal
Basically the pool is constructed in conservative way. Using (只) and (隻) example. There is a no direct (只)->(隻) entry because this will introduce unnecessary confusion on top of the already confusing incomplete translate.

This basically lead the the caveat described in the Caveat section.

## Caveat
As the the pool is constructed in a conservative way. Some of the obvious transformable words are not transformed. It is especially obvious when it comes to end of a sentence. This is so far a problem unsolvable. We can only minimise the un-transformable by introducing more sophisticated search terms.

## Future Plan
This has been start off as a personal project as some of the subtitle files in animes are only provided in Simplified Chinese and not Traditional Chinese. It is still now a personal project, but I do hope people would at least remotely benefit slightly from my personal work.

When I come across more animes in similar situation I will put more wording and phrase to this pool. Currently it is still in early stage. A lot of the obvious are still not yet covered.

Another plan is to create some gui or at least some tool around the pool so it can be used easier. Since it start of as my personal project it was really really primitive.

## Approach
The way to find the wording to put in is basically the following steps:

1. Lock in to a file contains, ideally, only the Simplified Chinese (SC) that you want to transform
1. Run the existing pool over the SC to generate the Traditional Chinese (TC) version
1. Diff the SC text and the TC text
1. We don't look at the difference, we look at the 'same' and spot the parts that require transformation
1. Insert the new entities found in the check (and make sure not in conflict with with the 'How the wordings are ordered' section)
1. Save the list
1. Repeat the whole process with another files (or the same SC files if needed)

## License
It seems that CC-BY-4.0 suit the need of the repo. This may subject to change if later on I find a better license.
