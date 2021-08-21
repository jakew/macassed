---
---
## Mac-Assed Mac Apps

With the rise of cross platform frameworks (Electron being the biggest culprit),
large companies are, more than ever, porting the same experience across all
platforms. This website lists apps that think different.

## What is "Mac-Assed"

Brent Simmons described Mac-assed this way:
>>>A few people have asked me, “What’s a Mac-assed Mac app?”

>>>Answer: it’s a phrase I stole from my friend Collin Donnell to describe Mac
>>>apps that are unapologetically Mac apps. They’re platform-specific and
>>>they’re not trying to wow us with all their custom not-Mac-like UI (which
>>>often isn’t very accessible).

A Mac-assed Mac app is an app that doesn't just run on macOS, but fits in. It
uses the same design language the macOS expects. It uses the same components
you're already familiar with. It works as you would expect anything on macOS to
work.

### The Apps

{% assign apps_by_type = site.apps | group_by: "type" %}

{% for type in apps_by_type %}

## {{ type.name | capitalize }}
                                
{% for app in type.items %}
<div>

{% if app.image != nil and app.image != '' %}
<img src="{{ app.image | prepend: '/assets/images/' | prepend: site.baseurl }}"
     style="width: 100%; max-width: 50pt; max-height: 50pt; float: left; margin-right: 5pt;"
     alt="{{ app.name }}"
     title="{{ app.name }}"
/>
{% endif %}
<h3>{{ app.name }}</h3>

</div>

- [Homepage]({{ app.site_url }}) — [{{ app.price }}]({{ app.buy_url }})

{{ app.content | markdownify }}

{% endfor %}

{% endfor %}

### Qualifications

Clarifying the exact requirements is difficult as most people are not design
experts. A good first step is to check if the application exists on other
platforms. If it does, and it looks the same on each platform, it is **not** a
Mac-assed Mac app.

To be a true Mac-assed Mac app, the app has to be built using the provided Apple
UI frameworks such as Carbon, Cocoa, or SwiftUI, and all of the features those
UI frameworks provide in a macOS specific way, complying with Apple's
own [Human Interface Guidelines for macOS](https://developer.apple.com/design/human-interface-guidelines/macos/overview/).

A side benefit is, if macOS has a UI framework feature added, the app will often
get the new feature without an update.

### Contributing

If you run a Mac-assed Mac app (or just know of one), please [make a pull
request](). If you don't know how to do that, just make an
[issue](https://github.com/jakew/macassed/issues/new/choose).


