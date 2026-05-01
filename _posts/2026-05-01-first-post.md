---
layout: post
title: "Choosing a toolbox — switching from Windows to Fedora"
date: 2026-05-01
usemathjax: true
categories: [devlog]
tags: [dev-environment, fedora]
description: "How and why I switched from Windows back to Linux (for the 4th time)"
---

## The build-up

For the last 3-4 years I have been back on Windows after using various distros with KDE as my primary desktop environment. I went back mostly because I started using my desktop less for personal projects in infrastructure/software and because I spent more time playing video games...    

Every year I would do a fresh install of Windows, after some times file explorer would become sluggish, the login screen wouldn't show me the password window, the browser would freeze (even after re-installs/cache clearing). None of these things made me conciously think about switching, I was a casual user basically using the OS as a bootloader for Steam and Chrome.

Fast forward to about two weeks ago, when I started spending considerable time in VSCode while taking a course in Embedded Programming in C/C++ at the higher vocational education I attend.  
During the previous courses we would use AVR Microchip Studio while writing firmware for ATmega microprocessors, which runs just fine on windows and works as a nicely set up "out of the box" IDE.  Now in the embedded c++ course we are using VSCode, writing our own Makefiles from scratch and compiling with g++. All was great at the start, writing code, compiling, seeing prints in our terminals, then we started working using ESP-IDF while developing drivers for the ESP32. Enter a split brain situation where half our dev environment was meant to live in WSL and the other half lives as a python venv, which is what esp-idf is under the hood.  

Most of the time spent on the driver project so far has been spent troubleshooting error messages from vscode trying to configure intellisense and setting up the make files. Solving this was not a clear journey where I felt in control of my development environment, I felt like any tiny change would break everything and I would have to spend another 30 minutes troubleshooting instead of actually writing code.  

This made me start thinking, what makes a good development environment? What aligns with my philosophy and mindset in life? I like things to be easy to explain and understand, no hidden complexity but everything should be transparent. I also value ergonomics, both physically and mentally. Needing to switch between the keyboard and mouse, switch focus from different windows and side bars, and things cluttering the screen all tax my energy. If I'm going to spend a couple of thousands of hours in front of a keyboard and monitor either writing software or papers during my career (which I hopefully have many years left of), I want to do it in a way where I can feel like I have chosen the right tools for the job.  

I have always been fascinated by the Unix philosophy since I first heard about it, especially the part about small focused tools made to work together, each with their own clear purpose. I think modern software and mostly Windows is guilty of trying to do way too many things at once. The goal is of course simplicity and that things should "just work", which is something that I also value! But does it have to be a choice between "just working" + simplicity, to having performant software that is open to extension/modification?

So the journey to build my own toolbox that I will try to carry with me during my whole career started!  

## The toolbox

What will the toolbox consist of then?  

Choosing a distro was quite easy, out of earlier experience I picked fedora. From my earlier experiences I remember it being easy to set-up and stable while also having up to date packages. I made the choice to go with a minimal install without desktop environment first, to even further make the environment fully custom and to have full control and track of package/dependency installed. The natural choice for desktop environment was KDE, even if I was tempted to install a tiling wm like i3. Having the base of the OS in place, the next step was of course picking out the necessary tools to put in the toolbox.  

For the shell I chose zsh and started writing a custom .zshrc along with installing zoxide and fzf to make navigation fast. The color scheme and font had to be easy on the eyes so I chose Gruvbox Light and ComicShanns Mono. This lead me to choose alacritty as my terminal emulator, since it seemed to be stable, lightweight and customizable. I spent a great deal of time configuring Neovim, choosing to do it manually instead of using lazyvim to avoid getting stuck in the same situation as with vscode. Neovim and its configuration warrants its own post, I am only in the beginning of my journey configuring it and getting comfortable with a purely keyboard based workflow.  

Since my focus currently is C/C++, the toolchain I chose is nothing surprising probably, gcc/g++ and clang as compilers, cmake + ninja as build system and clangd as LSP for integration with neovim.

For version control git and github cli client (gh) was the obvious choice. Though having heard about people leaving github behind for Codeberg I realize that relying on one centralized remote git server might not be the move. Trying to always think one step further is good when choosing your tools, especially when choosing services or software that other people maintain and develop. I always try to have in mind what their philosophy and motivations are and how my choice could play out long term.

That is how far I've gotten so far! Nothing revolutionary, probably very similar tooling to what many other people have chosen for themselves. The key and most important fact though, is that all these people _chose_ this collection of tools themselves, and so did I!. Choose the tools you like, build your own environment and take control of your own time and wellbeing. For me this is the most important takeaway, choose tools that you enjoy using and that you could see yourself using for the foreseeable future, that will save you time and headaches.  
Choose with care. 
