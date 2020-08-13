# Intl Locale Info API


## Stage 
Stage 0

## Champion
* Frank Tang @FrankYFTang

## Scope

A proposal to expose Locale information, such as week data (first day in a week, weekend start day, weekend end  day, minimun day in the first week), hour cycle used in the locale, measurement system used in the locale.

* Week Data: (User request: https://github.com/tc39/ecma402/issues/6 )
  * Prior Art: [mozIntl.getCalendarInfo(locale)](https://firefox-source-docs.mozilla.org/intl/dataintl.html#mozintl-getcalendarinfo-locale)
* Hour Cycle
* Direction (User request: https://github.com/tc39/ecma402/issues/205 )
  * Prior Art: [mozIntl.getLocaleInfo(locales, options)](https://firefox-source-docs.mozilla.org/intl/dataintl.html#mozintl-getlocaleinfo-locales-options)

## High Level Design
### Week Data
```
let weekInfo = Intl.getWeekInfo(["en-US"])
// { 
//  locale: "en-US", 
//  firstDayOfWeek: 7,
//  minimalDaysInFirstWeek: 4, 
//  weekendStart:  6,
//  weekendEnd: 7,
// }
```
Monday is 1 and Sunday is 7, as defined by ISO-8861 and followed by [Temporal proposal](https://tc39.es/proposal-temporal/#sec-temporal-todayofweek)

# TO BE DELETED- FROM TEMPLATE
## Before creating a proposal

Please ensure the following:
  1. You have read the [process document](https://tc39.github.io/process-document/)
  1. You have reviewed the [existing proposals](https://github.com/tc39/proposals/)
  1. You are aware that your proposal requires being a member of TC39, or locating a TC39 delegate to "champion" your proposal

## Create your proposal repo

Follow these steps:
  1.  Click the green ["use this template"](https://github.com/tc39/template-for-proposals/generate) button in the repo header. (Note: Do not fork this repo in GitHub's web interface, as that will later prevent transfer into the TC39 organization)
  1.  Go to your repo settings “Options” page, under “GitHub Pages”, and set the source to the **main branch** under the root (and click Save, if it does not autosave this setting)
      1. check "Enforce HTTPS"
      1. On "Options", under "Features", Ensure "Issues" is checked, and disable "Wiki", and "Projects" (unless you intend to use Projects)
      1. Under "Merge button", check "automatically delete head branches"
<!--
  1.  Avoid merge conflicts with build process output files by running:
      ```sh
      git config --local --add merge.output.driver true
      git config --local --add merge.output.driver true
      ```
  1.  Add a post-rewrite git hook to auto-rebuild the output on every commit:
      ```sh
      cp hooks/post-rewrite .git/hooks/post-rewrite
      chmod +x .git/hooks/post-rewrite
      ```
-->
  1.  ["How to write a good explainer"][explainer] explains how to make a good first impression.

      > Each TC39 proposal should have a `README.md` file which explains the purpose
      > of the proposal and its shape at a high level.
      >
      > ...
      >
      > The rest of this page can be used as a template ...

      Your explainer can point readers to the `index.html` generated from `spec.emu`
      via markdown like

      ```markdown
      You can browse the [ecmarkup output](https://ACCOUNT.github.io/PROJECT/)
      or browse the [source](https://github.com/ACCOUNT/PROJECT/blob/HEAD/spec.emu).
      ```

      where *ACCOUNT* and *PROJECT* are the first two path elements in your project's Github URL.
      For example, for github.com/**tc39**/**template-for-proposals**, *ACCOUNT* is "tc39"
      and *PROJECT* is "template-for-proposals".


## Maintain your proposal repo

  1. Make your changes to `spec.emu` (ecmarkup uses HTML syntax, but is not HTML, so I strongly suggest not naming it ".html")
  1. Any commit that makes meaningful changes to the spec, should run `npm run build` and commit the resulting output.
  1. Whenever you update `ecmarkup`, run `npm run build` and commit any changes that come from that dependency.

  [explainer]: https://github.com/tc39/how-we-work/blob/HEAD/explainer.md
