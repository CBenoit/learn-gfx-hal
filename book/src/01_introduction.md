# Introduction

## What Is `gfx-hal`

The [gfx-hal](https://docs.rs/gfx-hal) crate is a cross platform graphics API
that attempts to be a minimal wrapping of the "modern, low level" graphics APIs
(DX12, Vulkan, and Metal).

To quote Icefox (lead of the GGEZ project):

> I think of Vulkan as basically being GPU assembly language, at least in terms
> of level of abstraction. Which is to say, there is very little abstraction: it
> gives you the parts that you have to work with, it has nothing stopping you
> from doing whatever you feel like with those parts, now go write stuff with
> it. No, there's no memory allocator. I just told you to go write stuff, didn't
> I? Write it. Comparatively, OpenGL is like GPU Javascript: It starts out
> convenient, but it's old, wacky, clunky, weird, has a million evolutionary
> versions and odd edge cases, and it’s not really a convenient model for
> computation these days. Sure you can make it fast if you try, but you have to
> jump through lots of hoops to do so.

So this will be a _very long_ style of tutorial, because we'll have to be doing
oh-so-many little steps and configurations by hand as we learn to do each new
thing. If that's not your scene then sorry I guess, this tutorial might not be
for you.

## Requirements

I assume that you have basic familiarity with Rust. So go read [The Rust
Book](https://doc.rust-lang.org/book/) if you haven't ever done that.

We will also be touching upon elements of `unsafe` Rust, and so you should also
read [The Rustonomicon](https://doc.rust-lang.org/nomicon/) if you have not.
Actually, that's a mild lie, most of `gfx-hal-0.1.0` doesn't define any of its
safety limits anyway (not beyond "whatever Vulkan say is okay"), so it's all a
shot in the dark no matter what you do. Even if you're using a backend that
isn't Vulkan.

I don't assume you have any prior graphics programming skills. I sure don't have
much myself. I drew a quad once in OpenGL, but that's it. We'll be learning and
reviewing all that stuff together.

The code all assumes that you're using **Rust 2018**.

I set rustfmt to have 2 space indents and a line limit of 130. I hope you're
fine with that.
