<div align="center">

# Learn Scenic

A guide to getting up and running with Scenic.

</div>

## What?

Scenic is a functional UI library for Elixir with which you can
build applications for many supported operating systems;
including macOS, Windows and Nerves/Linux.

It's also reasonably lightweight, with a Scenic+Nerves firmware image
clocking in at ~30MB.

## Why?

Scenic is a great way to add a simple UI to your Nerves application 
(or any Elixir app) without having to include a web browser to render
HTML and JavaScript. This reduces complexity and keeps deployment simple.

For complex, rich UIs, i'd still recommend using web technologies and 
deploying using [`nerves-web-kiosk`](https://github.com/nerves-web-kiosk/kiosk_system_rpi3).
Even SpaceX used [JavaScript for rendering the GUI in their new
Dragon capsule](https://www.reddit.com/r/spacex/comments/gxb7j1/we_are_the_spacex_software_team_ask_us_anything/ft0aip8?utm_source=share&utm_medium=web2x)!

We're using Scenic to render simple user feedback for `smart-home-security-system`,
where its small size and simplicity makes it a perfect fit!

## How?

We'll build a simple "Hello world!" Scenic application that will help us to
understand how Scenic works!

### 0. Prerequisites

This guide presumes that you've got Elixir installed, 
and you have a good understanding of how it works.
If not, go visit [dwyl/learn-elixir](https://github.com/dwyl/learn-elixir)
and learn some more!

### 1. Install dependencies

Scenic goes to great lengths to minimize its dependencies, 
but we still need to install a few so Elixir can talk to your OS' 
graphics stack.

##### GLFW
*Graphics Library FrameWork*. This is a library that allows Scenic to
manage application windows, as well as handle keyboard and mouse input.

##### GLEW
*openGL Extension Wrangler*. This helps Scenic load and query extensions
to the OpenGL framework.

#### Installing

On macOS, you can easily install these through Homebrew:
```
brew install glfw3 glew pkg-config
```
*pkg-config* is probaly already installed, its used to configure packages 
and load libraries

For other systems, check the official documentation:
https://hexdocs.pm/scenic/install_dependencies.html#content

#### Install the generator

Scenic, like Phoenix and Nerves, comes with a Generator to spin your 
project up quickly, so lets install that now.

```
mix archive.install hex scenic_new
```

