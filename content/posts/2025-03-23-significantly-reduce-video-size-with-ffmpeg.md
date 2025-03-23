---
title: "Significantly reduce video file size with ffmpeg"
date: 2025-03-23T10:42:48Z
tags: ['linux','video']
---

I was recently asked to record someones short performance at a gig on my phone. I obliged of course but I've got to admit dealing with video footage on phones is not all that fun to me. Mostly because of the huge file sizes. Then we've got to work out how we're going to transfer it to a computer for some post processing and send it on. The piece of video in question was around 5 gigs in size. You take this on an Android phone with Google Photos or something and that's a pretty nasty chunk out of your free storage allowance.

Anyways, I got it across to computer and ran some noise reduction processes on it in Kdenlive. The final output was still a massive file and I needed to send it via wetransfer where it was still way, way over the file size limitation of 2 gigs.

Thankfully I have this nice little piece of code bookmarked for such situations and I thought I should share it here for your use and easy reference. Make sure you have ffmpeg installed and run this command on your file in the terminal. Replace input and output.mp4 with the name of your file. Be warned this process needs to be allowed to run in the terminal without being disturbed and can take quite some time. I can't explain the technicals of it but it goes through frame and frame and runs some compression on it. It  may take a quite a long time even on a short video depending on the power of your machine. 

I managed to get a 5 gig file down to under 500 mb! with absolutely no noticeable difference in resolution or sound quality. For me that's worth the waiting time. Try it out and be patient -  It just works.

```sh
ffmpeg -i input.mp4  -vcodec libx265 -crf 28 output.mp4
```

## Related

[Getting Started with Doom Emacs](/posts/2023-01-27-getting-started-with-doom-emacs/)

[What the hell is Org-Mode?](/posts/2023-12-01-what-the-hell-is-org-mode/)
