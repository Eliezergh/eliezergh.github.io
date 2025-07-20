+++
draft = false
date = 2025-07-20T14:30:49Z
title = "Work with Hugo on your iPad"
+++
## Introduction

As you might’ve noticed, this blog runs on [Hugo](https://gohugo.io), a static site generator that I use as the base platform.

The site is hosted on GitHub Pages, which works great for a simple blog like this one. It’s easy to manage content with Markdown and push updates using just a few Git commands.

## The Problem

Since Hugo is written in Go, getting the binary to run on *iPadOS* isn’t exactly straightforward.

You might be thinking: _why even bother using an iPad for this?_ — but I actually find it super convenient for writing and editing documents. So I started looking for a way to make it work.

Modern iPads are surprisingly capable, and there are now a few decent apps that can help power users do more than just browse and type.

## The Solution

### Running the Hugo Binary

Hugo works through the command line, and iPadOS doesn’t ship with one — so we have to rely on third-party apps.

I first tried the well-known [iSH Shell](https://apps.apple.com/es/app/ish-shell/id1436902243), which is great in general, but Go support is lacking. After wasting quite a bit of time trying to get Hugo to work inside iSH, I gave up.

Then I came across [UTM SE: Retro PC Emulator](https://apps.apple.com/es/app/utm-se-retro-pc-emulator/id1564628856), and this one was a game-changer. UTM lets you run full virtual machines on an iPad — including Linux.

I grabbed a free Arch Linux VM from the [UTM public gallery](https://mac.getutm.app/gallery/), and after updating and installing a few packages, I finally had Hugo up and running in a proper Linux shell — right on my iPad.

### Writing Content

For editing and Git integration, I use [Working Copy](https://apps.apple.com/es/app/working-copy-git-client/id896694807), which lets me clone my GitHub repo, edit Markdown files, and push changes.

I set up a *shared folder* between the Arch VM and the iPad filesystem, which means I can use the Hugo CLI inside the VM to create new posts and build the site.

**This post was created entirely on my iPad.**

## My Setup Summary

If you’re curious about the exact setup I’m using to make this work, here’s a quick breakdown of the apps and hardware:

### Apps & Tools

- **[Hugo](https://gohugo.io/)** — Static site generator used for building the blog.
- **[UTM SE: Retro PC Emulator](https://apps.apple.com/es/app/utm-se-retro-pc-emulator/id1564628856)** — Used to run a full Linux virtual machine on the iPad.
- **[Arch Linux VM](https://mac.getutm.app/gallery/)** — Downloaded from the UTM public gallery; gives me a proper shell environment.
- **[Working Copy – Git Client](https://apps.apple.com/es/app/working-copy-git-client/id896694807)** — Used to clone, edit, and push changes to my GitHub Pages repo.
- **[iSH Shell](https://apps.apple.com/es/app/ish-shell/id1436902243)** — Mentioned as an alternative shell emulator, but lacks proper Go support.

### Hardware

- **iPad Air 11-inch (M3, 2024)** — Main device I’m working on.
- **Logitech Combo Touch for iPad** — Keyboard case with trackpad, makes typing and navigation way more comfortable.