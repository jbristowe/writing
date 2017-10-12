# Telerik R3 2017 Release Webinar Wrap-Up

## Questions and Answers

### Telerik UI for ASP.NET MVC

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">We have some drag and drop functionality. Is there something specific you&#39;re looking for? <a href="https://t.co/esNIIPOssz">https://t.co/esNIIPOssz</a></p>&mdash; Ed Charbeneau (@EdCharbeneau) <a href="https://twitter.com/EdCharbeneau/status/918140485474103297?ref_src=twsrc%5Etfw">October 11, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/hashtag/heytelerik?src=hash&amp;ref_src=twsrc%5Etfw">#heytelerik</a> Does the Scheduler support CRON inputs?</p>&mdash; Sage Aucoin (@AucoinSage) <a href="https://twitter.com/AucoinSage/status/918156670353707008?ref_src=twsrc%5Etfw">October 11, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

No. The recurrence rule string for events in the **Scheduler** follows the RRULE format as outlined in the iCalendar specification ([RFC 5545](https://tools.ietf.org/html/rfc5545)). You'd need a cron parser and converter in order to get this working with the **Scheduler**.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/hashtag/heyTelerik?src=hash&amp;ref_src=twsrc%5Etfw">#heyTelerik</a> With Virtual Scrolling and Endless Scrolling, how does the Excel Export work?</p>&mdash; Darron Scott Michael (@Darr0nMichae1) <a href="https://twitter.com/Darr0nMichae1/status/918133204023885825?ref_src=twsrc%5Etfw">October 11, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

Great question. Virtual scrolling and endless scrolling operate in similar ways in that they load data on-demand. This means that the **Grid** will typically have only a subset of the entire underlying data source loaded in its view. When the user exports this data to Excel, only the data contained in the current view will be exported.

### Telerik UI for UWP

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/hashtag/HeyTelerik?src=hash&amp;ref_src=twsrc%5Etfw">#HeyTelerik</a> With the recent news about Windows Mobile, is it worth writing UWP apps that target mobile?</p>&mdash; Pete Geiter (@PGeiter) <a href="https://twitter.com/PGeiter/status/918131380722077696?ref_src=twsrc%5Etfw">October 11, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

I would suggest using Xamarin and Telerik UI for Xamarin if you're looking to build mobile applications. That stated, UWP and Telerik UI for UWP helps you to build applications that run on all types of Windows-based devices. This includes the Xbox, HoloLens, IoT, and more.