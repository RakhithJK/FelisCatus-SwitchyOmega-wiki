This project starts with the following phrases.

## Logic prototype
FelisCatus will write the first implementation of the new [[profile]] and [[condition]] design.
Code **won't** be pushed to the git repo until [[PAC generating]] is done.

### Status
Done.

## The first push
FelisCatus will push some code to master. Developers can generate PAC scripts with constructed profiles and conditions.
However, there won't be any UI at this phrase, so most users won't be able to use it.

Developers should focus on validating the PAC scripts and improving its efficiency.

### Status
Done. (pushed: 2012-07-14)

## Logic testing and fixing
FelisCatus will write tests and fix bugs on the profile switching logic. Issues should be reported at the issue tracker.

### Status
The logic is somewhat tested and it works fine. Could not find any more bugs at the moment.

Unit tests are not written yet.

## UI design
The HTML and CSS should be done by FelisCatus in this phrase. FelisCatus will start pushing to git master when the UI looks nice and complete. Users can review the UI design and report issues.

### Status
Due to FelisCatus's being fully occupied of other things (and the fact that FelisCatus is **very lazy**), the finish date was put off for 3 times.

**Finally (almost) finished** by 2012-08-13. Minor tweaks could happen later.

## Interaction code
Users should be able to change the settings via the UI. Things like switching among profiles and saving settings should be implemented by FelisCatus.

### Status
FelisCatus is now working on the background page.

Estimated finish date: 2012-08-25

## Overall testing
[[SwitchySharp]] could not be updated any more after Late September 2012 because [manifest version 1 starts to be phased out][manifestVersion]. So this project should enter [[stable]] as soon as possible. Branches should be set up for [[beta]] and [[stable]] releases.

[manifestVersion]: https://code.google.com/chrome/extensions/manifestVersion.html

## Status
Estimated date of entering beta: 2012-08-31

Estimated date of entering stable: N/A 
(Beta will be uploaded to [[Chrome Web Store]] if stable is not ready.)