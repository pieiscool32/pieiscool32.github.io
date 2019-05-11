---
layout: post
title: Meta Blog
---

I think by this point the overall pipeline and site code are pretty solid, so I wanted to go over those in detail.

### Site

The site itself looks rather basic and modern as you may have noticed.
This is mostly because I wanted a site that was easy on the eyes and focused on content,unlike the
[new trend](https://www.reddit.com/r/badwebdesign/) of [flooding a site](https://www.reddit.com/r/funny/comments/9q22c2/every_website_in_2018/)
with ads, banners, and pop-ups.

#### Foundation

When I was on the hunt for a CMS there were plenty of options, [WordPress](https://wordpress.org) in particular has a
large presence in the blogging community. However, I am a developer and I want to get my hands dirty and look at some code. 
After a little bit of digging around, I found [Jekyll](https://jekyllrb.com) and the seemingly hidden community around it.

The primary upside of Jekyll is the sheer amount of customization that is available. Even though I started off with the
[Amplify](https://github.com/ageitgey/amplify) template, I was able to make some adjustments to the page and make it my own. 
Even though I picked this template, there is nothing stopping me from getting some other template and swapping everything 
out with little effort.

The other nice part about Jekyll is that I am not stuck to using a particular editor or website to do my writing, in fact
I have been using [WebStorm](https://www.jetbrains.com/webstorm/) to write my posts to far, because I like the interface.
Plus, there is no way to undersell the benefits of using git to track changes and manage my workflow.

#### AMP

Something that is probably not apparent to most readers is the sheer speed at which the pages load, because everyone expects
that pages be fast and responsive. I chose [Accelerated Mobile Page](https://amp.dev) (AMP) because the sole purpose is
being fast and lightweight. There are a few [controversies](https://ferdychristant.com/amp-the-missing-controversy-3b424031047)
surrounding AMP, but the general reasoning given is not enough to dissuade me from using it.

#### Disqus

Yet another service I use with some [issues](https://www.isaumya.com/7-reasons-to-avoid-disqus-commenting-system/) from the
community and other bloggers. Although, a lot of the concerns are avoidable if you know a little about how [iframes](https://www.w3schools.com/tags/tag_iframe.asp)
work and like to dig deep into settings to disable creepy stuff. By default the Disqus ads are turned off because this site
is small enough to be ads-optional for free. I did have to disable their referral link injection and tracking features, which
were hidden in the site settings, but at least they can be turned off. Considering that the service is offered free of charge,
I decided it is the best option for me at this point. I might switch to [Utterances](https://utteranc.es) at some point.

#### RSS

If the previous two items are a cause of concern, there is a handy-dandy [RSS feed](https://blog.munte.me/feed.xml) for
you to use and just read the articles. I use [Feedly](https://feedly.com) to read some news articles at the recommendation
of a friend. The feed is not going to go anywhere, so feel free to use it exclusively if you are concerned about me or
the services I use on the site are doing something shady.

#### Hosting

For the hosting, I use [Github Pages](https://pages.github.com/) and [Cloudflare](https://www.cloudflare.com) together.
While I do not strictly need to use Cloudflare, they have been doing a good job recently and will have [AMP Real URL](https://blog.cloudflare.com/announcing-amp-real-url/)
to package up the site according to the [AMP Signed Exchanges](https://amp.dev/documentation/guides-and-tutorials/optimize-and-measure/signed-exchange).
Github Pages is necessary as they kindly go ahead and compile the site to be served and host it free of charge.
