---
id: 341
title: V4 Beta Release
date: 2019-02-06T05:22:16+00:00
author: arshaw
layout: post
guid: https://fullcalendar.io/blog/?p=341
excerpt_separator: <!--more-->
dsq_thread_id:
  - "7213172625"
---
The FullCalendar v4 **beta** has just been released. It contains almost exactly the same API as the previous alpha version except for one big thing: all functionality is broken up into **plugins**. There is a **core** package, but it won&#8217;t do anything on its own. You must load plugins for everything, including each type of view.<!--more-->

[View the list of plugins »](https://fullcalendar.io/docs/v4/plugin-index)

Each plugin has its own NPM package. Many of the views have been renamed to be more consistent with the package names they come from:

  * **agenda** view has been renamed to **timeGrid** (timeGridWeek, timeGridDay)
  * **basic** view has been renamed to **dayGrid** (dayGridWeek, dayGridDay)
  * **month** view has been renamed to **dayGridMonth**
  * **timeline** view has been renamed to **resourceTimeline** (resourceTimelineWeek, etc)

Also, it&#8217;s important to note that date clicking, date selecting, event drag-n-drop, and event resizing require the **interaction** plugin.

In addition, Bootstrap 3 theme support and jQuery UI theme support have both been dropped. And there are some minor setting renames. Also, **superagent** has been dropped as a dependency for JSON feed requests, which was introduced in a previous alpha.

For more info, see the [changelog](https://github.com/fullcalendar/fullcalendar/releases/tag/v4.0.0-beta.2), the updated [upgrade guide](https://fullcalendar.io/docs/v4/release-notes), or the [updated docs](https://fullcalendar.io/docs/v4).

Because FullCalendar has been broken up into plugins, it&#8217;s possible to bundle only the functionality you need, saving space. This, combined with the shedding of jQuery and Moment as dependencies, has drastically reduced the total filesize of a simplest-case app. For example, if all you want to do is display a read-only month-view calendar, you would bundle the following packages:

<p style="margin-left: 2em;">
  <strong>@fullcalendar/core</strong> + <strong>@fullcalendar/daygrid</strong><br /> = <strong>43k</strong> (minified and gzipped)
</p>

Whereas before you needed to bundle much more:

<p style="margin-left: 2em;">
  <strong>fullcalendar</strong> + <strong>jquery</strong> + <strong>moment</strong><br /> = <strong>101k</strong> (minified and gzipped)
</p>

The size of the required JS is less than half!

For getting your hands on this beta release, it is recommended you follow the guide for [using an ES6 build system](https://fullcalendar.io/docs/v4/initialize-es6). If you would prefer to download a ZIP file and use [script tags and browser globals](https://fullcalendar.io/docs/v4/initialize-globals), download these:

  * [fullcalendar-4.0.0-beta.2.zip](https://github.com/fullcalendar/fullcalendar/releases/download/v4.0.0-beta.2/fullcalendar-4.0.0-beta.2.zip)
  * [fullcalendar-scheduler-4.0.0-beta.2.zip](https://github.com/fullcalendar/fullcalendar-scheduler/releases/download/v4.0.0-beta.2/fullcalendar-scheduler-4.0.0-beta.2.zip)

While pluginifying FullCalendar, one aspect that has not yet been quite nailed down is **how to deliver the CSS/SCSS**. If you have experience with this matter, <a href="https://github.com/fullcalendar/fullcalendar/issues/4490" target="_blank">please chime in on the GitHub Issue »</a>

Please give this beta release a try! [Report any bugs you find »](https://fullcalendar.io/reporting-bugs)

If this beta release goes as smoothly as the previous alpha releases, the final release of 4.0.0 should be March 15th.