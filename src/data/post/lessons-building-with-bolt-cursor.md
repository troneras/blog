---
title: I Didn’t Plan to Join the World’s Largest Hackathon—Here’s How I Ended Up Building an AI Receptionist Solo
description: After months of ignoring hackathon emails, I stumbled into the world’s largest hackathon almost by accident—just as I was finally ready to build my vision for a truly useful AI business assistant. Here’s how I used Bolt, Cursor, and a squad of AI copilots to ship a real project solo, what worked (and didn’t), and why you shouldn’t sleep on building with AI.
publishDate: 2025-06-30
author: Antonio Blázquez
image: ~/assets/images/cutcall-hackathon.png
tags:
  - hackathon
  - ai
  - solo founder
  - bolt
  - cursor
  - square
  - entrepreneurship
  - programming
  - story
---

# **I Didn’t Plan to Join the World’s Largest Hackathon—Here’s How I Ended Up Building an AI Receptionist Solo**

**I never intended to join a hackathon.** I totally ignored promotional emails for ages. I knew [bolt.new](https://bolt.new) existed, but I wasn’t really interested.

I’d used [v0.dev](https://v0.dev) a few times for creating components, and even tried generating more complex apps, so I knew these tools—and their limitations.

But one day, I opened up Bolt, ready to finally make my refined vision real—and there it was: a huge banner for the world’s largest hackathon. I thought to myself, _“why not?”_ Having a bit of pressure to actually finish a project for once didn’t sound bad at all.

My _honest_ take was that Bolt.new was mostly for “vive coders,” not “real coders.”  
But after this experience, I think the opposite: vive coders should use Cursor, and software engineers should use Bolt.

The reason? If you check [Bolt’s code](https://github.com/stackblitz/bolt.new), you’ll see that on every message, _the full context_ (chat messages, code produced, responses) is sent back and forth. This makes it super expensive if you want to iterate a lot—especially like a “vive coder” (even with caching).

If you’re going to iterate, it’s much better to use Cursor. You can open as many threads as you want and work incrementally, without sending insane amounts of context to LLMs.  
And Cursor does a lot of internal optimization magic. (If you’re curious about that, check out [this interview](https://www.youtube.com/watch?v=oFfVt3S51T4) from Lex Fridman with the Cursor team—they share more details about how it works than they probably intended.)

However, if you _have a plan_, a clear system vision, and you can solve your problem with Supabase or Stripe alone, Bolt’s direct integration with Supabase is awesome for quickly building a first version with a beautiful UI.

You could probably get similar results with Cursor if you set up different MCP servers, but it’s slower. What makes Bolt special is how fast it creates interfaces—it parses the responses and updates files as it goes, keeping the full context in memory. For the first iterations (before you hit context limits), Bolt knows every little detail about your project because it doesn’t optimize anything on the context side.  
Cursor, by contrast, sends just the parts its internal model thinks are relevant for your query. Sometimes, Cursor has to go back and forth a few times before it finds the solution.

The main limitation of these tools is _context_. If you don’t have a very clear vision from the start, iterating gets more and more token-hungry and slow.

You should absolutely follow [Guillermo Rauch (CEO of Vercel)](https://x.com/rauchg) for some amazing one-shot interfaces and tips for tools like v0 or Bolt.

So: if you have a clear solution in mind, give these tools a shot—and let me know your impression.

---

In my case, I’d been iterating on an app idea for a few months—one of those projects where you start, realize your idea isn’t so great, set it aside, then one day look at it from another perspective, and bit by bit it takes shape.

I’d already done a couple “start from scratch” attempts for this project.  
That’s normal: at first you don’t really know the domain, and the more you dig in, the better you understand the problems, competitors, and where your product might fit.  
That’s why so many projects get abandoned—because once you truly understand the space, you see that nobody really needs your solution, or the main problems are totally different, or there are already great solutions out there.  
Honestly, sometimes it’s better to become a referral partner instead. (Referrals are a great business, by the way.)

For me, I wanted to build a smart appointment system. But to be honest, I didn’t really know what businesses use, or what competitors are out there.  
Turns out, it’s a _huge_ market—multimillion dollar companies like Square offer complete digitalization suites: bookings, payments, online stores, invoicing, customer management, and more. Trying to compete with that isn’t realistic, and I don’t want to sell anyone something that’s suboptimal for their business.

So I took a more humble route: if you can’t beat them, join them.  
Out of all the business digital tools I found, the best in my opinion (and the one I’d recommend to any small business) is Square. They let external apps integrate and read/write business info, so it was the perfect platform to build my AI agent on.

Once I had a clear scope—integrate with OAuth, implement an API client for Square data, and create a real value proposition that Square itself was missing—I decided to give Bolt a try.

And it was awesome. My vision came alive in hours right before my eyes.  
Of course, working on backend code in Bolt is a bit weird, so after I had the main screens I pushed to GitHub and continued working locally with Cursor.

---

**If you’ve tried Bolt, Cursor, or v0.dev, I’d love to hear about your experiences (or horror stories!). Let’s trade notes.**

_Up next: how I shipped a real AI phone receptionist—solo—for the world’s largest hackathon, and what I learned along the way…_
