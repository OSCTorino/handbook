---
title: What is FAIR data?
draft: false
---

In 2016, [an article](https://doi.org/10.1038/sdata.2016.18) was published outlining "The **FAIR** guiding principles for scientific data management
and stewardship".
In the paper, the many authors outline what FAIR data is, why it was invented, and why it is useful.
It's a highly recommended read: if you have the time, please stop reading this book and read the article above (if you cannot click links, copy and paste this instead: `https://doi.org/10.1038/sdata.2016.18`).
You can find a page with just the FAIR principles [here, in the GOFAIR website](https://www.go-fair.org/fair-principles/).

In the rest of the page, we go in a bit more depth about what all the FAIR principles are, and what they *actually* mean.
With FAIR data we mean data that is:

## **Findable**
> You can actually find FAIR data, and it's very hard to lose it.

This is true both for your locally-saved data (so that you can no longer say "Oh, yes, it's in a hard drive somewhere...") and for online datasets uploaded to data repositories.
These principles cover data labelling: when you get a hold of FAIR data, it should be clear what the data is all about, including:
- What it is describing, meaning the thing that was measured;
- How it was generated, meaning the instrument or technique used on the thing that was measured;
- Who generated the data and when it was generated;
- Why the data was originally gathered;

Such a large amount of [metadata](../../metadata) is usually stored in a separate file that is kept alongside the data that it is describing.

This point also covers making your metadata and data machine-readable.
Think about searching trough documentations: it's done by a machine, not a human.
If metadata was readable by a machine, you could run powerful searches managing to locate the proverbial needle (the data that you need) in the haystack (the huge amount of data available online).

## **Accessible**
> You can easily obtain, or know how to obtain, FAIR data.

This might seem trivial, but not all data is born equal.
Some data is sensitive, for example, pertaining to the health of patients or their sexual, political or otherwise opinions that should be kept secret.
Such data should still be findable, but it might require additional levels of protection regarding how it can be *accessed*.
This point is focused around *a way to access data*, not that the data is openly accessible by default: the ways of getting the data should be clearly stated (e.g. asking for permission, signing waivers, etc...), but need not be open.

This point also covers the actual method of getting the data.
For example, data might not be accessible if the only way to obtain it is to send a carrier pigeon with a USB strapped to its leg to the recipient.
The way to get the data needs to be standardized and widely available to all.
Luckily, the internet exists, so we can leverage its protocols to transport data from point A to point B.

## **Interoperable**
> You can easily understand FAIR data once you have it.

If you download a dataset only to discover that it is written in ancient cuneiform, you might not be able to understand it (unless you are an archaeologist, maybe).

Data should be in a format that is understandable by all, not behind a paywall (did you ever consider that if you don't have the money to use Excel, you might not be able to read excel datasets?), and that is explained in detail (what does the `kplm` column mean?) so that everyone might understand the data even for many years to come.

## **Reusable**
> You can easily use FAIR data for purposes other than the one it was originally made for.

This point partially overlaps with the Interoperability, but covers specifically the act of reusing the data.

If you know in detail how the data was sourced, where it was sourced from, when it was taken and how it was recorded in the file, then you are able to use the data with confidence for other purposes.

This is the ultimate goal and power of FAIR data.
FAIR data is added with confidence to the global knowledge base and can be reused many times by different people for different purposes, including laboratories and individuals that might not have had the ways to gather it in the first place but that have creative uses for it[^1].

If you haven't already, now is a good time to read [the FAIR data publication](https://doi.org/10.1038/sdata.2016.18)
and [the go-fair website](https://www.go-fair.org).

The process of making old data FAIR is known as *FAIRification*.
In practice, FAIRification is very complicated, time- and resource-consuming and probably not worth your while.
This is why this handbook will not tell you how to take an experiment that was ran a year ago and make it FAIR[^2].

Instead, this handbook tries to teach you how to make your data FAIR *by design*.
It tries to decouple the process of *interpreting* the data from the step of *creating it*.
With the method described here, your protocols will generated FAIR data by default.
In a second step, you will use these FAIR objects for data analysis, writing papers, and sharing them with the public.

[^1]: This is also why the European Union is pushing the creation of FAIR data guidelines and FAIR data object, so that companies might reuse the data to generate additional profit. This is a bleak prospect and a controversial point of view (should academia directly support capitalism? How do we economically reward the authors of the data?), but it's outside of the scope of Mimir.
[^2]: I argue that this is impossible.
