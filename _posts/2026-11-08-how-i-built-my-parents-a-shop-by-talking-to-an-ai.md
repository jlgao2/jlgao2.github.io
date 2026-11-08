---
layout: post
author: George
title: How I built my parents an online shop by talking to an AI
description: A step-by-step guide for people who have never used AI, from switching on the computer to a first working version of an ordering website.
---
<style>
.g-fig { margin: 2rem 0; }
.g-fig img { display: block; width: 100%; height: auto; border: 1px solid var(--rule); border-radius: 10px; }
.g-fig figcaption { font-size: 0.85rem; color: var(--muted); margin-top: 0.5rem; line-height: 1.5; }
.g-pair { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin: 2rem 0; }
.g-pair .g-fig { margin: 0; }
.g-trio { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0.8rem; margin: 2rem 0; }
.g-trio .g-fig { margin: 0; }
@media (max-width: 600px) { .g-trio { grid-template-columns: 1fr 1fr; } }
.g-chat { margin: 1.6rem 0; display: flex; flex-direction: column; gap: 0.7rem; font-family: -apple-system, 'Segoe UI', Roboto, sans-serif; font-size: 0.92rem; line-height: 1.5; }
.g-msg { max-width: 85%; padding: 0.65rem 0.9rem; border-radius: 14px; }
.g-me { align-self: flex-end; background: var(--warm); color: #fff; border-bottom-right-radius: 4px; }
.g-ai { align-self: flex-start; background: var(--quote-bg); border: 1px solid var(--rule); border-bottom-left-radius: 4px; }
.g-who { display: block; font-size: 0.72rem; opacity: 0.75; margin-bottom: 0.15rem; letter-spacing: 0.04em; text-transform: uppercase; }
.g-loop { display: grid; grid-template-columns: 1fr 1fr; gap: 0.8rem; margin: 2rem 0 0.5rem; counter-reset: loop; }
@media (max-width: 600px) { .g-loop { grid-template-columns: 1fr; } }
.g-loop div { border: 1px solid var(--rule); background: var(--quote-bg); border-radius: 12px; padding: 0.9rem 1rem; font-size: 0.95rem; line-height: 1.45; }
.g-loop div::before { counter-increment: loop; content: counter(loop); display: inline-flex; align-items: center; justify-content: center; width: 1.6rem; height: 1.6rem; border-radius: 50%; background: var(--warm); color: #fff; font-size: 0.85rem; font-weight: 600; margin-right: 0.5rem; }
.g-loop-note { text-align: center; font-size: 0.85rem; color: var(--muted); margin: 0 0 2rem; }
.g-window { margin: 2rem 0 0.5rem; border: 1px solid var(--rule); border-radius: 12px; overflow: hidden; font-family: -apple-system, 'Segoe UI', Roboto, sans-serif; font-size: 0.85rem; background: var(--bg); }
.g-bar { display: flex; gap: 6px; padding: 0.55rem 0.7rem; border-bottom: 1px solid var(--rule); background: var(--quote-bg); }
.g-bar i { width: 10px; height: 10px; border-radius: 50%; background: var(--rule); display: block; }
.g-body { display: grid; grid-template-columns: 7.5rem 1fr; min-height: 13rem; }
.g-side { border-right: 1px solid var(--rule); padding: 0.7rem 0.5rem; display: flex; flex-direction: column; gap: 0.35rem; color: var(--muted); }
.g-side span { padding: 0.3rem 0.5rem; border-radius: 6px; }
.g-side .on { background: var(--warm); color: #fff; font-weight: 600; }
.g-main { padding: 0.9rem; display: flex; flex-direction: column; justify-content: flex-end; gap: 0.5rem; }
.g-box { border: 1px solid var(--rule); border-radius: 10px; padding: 0.7rem; color: var(--muted); }
.g-row { display: flex; flex-wrap: wrap; gap: 0.4rem; }
.g-row span { border: 1px solid var(--rule); border-radius: 999px; padding: 0.15rem 0.6rem; }
.g-row .tag { border-color: var(--warm); color: var(--warm); font-weight: 600; }
.g-note { font-size: 0.85rem; color: var(--muted); margin: 0 0 2rem; }
.g-tip h3, .g-tip p { margin: 0 0 0.5rem; }
.g-tip ul { margin: 0.3rem 0 0; }
.g-tip { border-left: 3px solid var(--warm); background: var(--quote-bg); padding: 0.8rem 1rem; margin: 1.5rem 0; border-radius: 0 8px 8px 0; }
</style>

My parents run a small wholesale business that supplies local shops. For years, every order arrived as a text message. My mum would read it, walk the warehouse, pack the boxes and type up an invoice.

I wanted to give them a proper ordering website. Shops log in, see what's in stock, and place an order. My mum gets a tidy list to pack from, and the invoice is sent with one tap. It works in English and Chinese.

I didn't write any of the code. I described what I wanted, in ordinary words, to an AI called Claude, and it built the site while I answered its questions and said what looked wrong. I had a first version working on the first evening, then kept asking for improvements over the next few days.

This guide shows exactly how, starting from switching on your computer. If you can send a text message and install an app, you can follow it.

<figure class="g-fig">
  <img src="/assets/guides/built-with-ai/shop-home.jpg" alt="The shop's home page: a search box, a banner saying 'Order your stock online', and photo tiles for product categories." loading="lazy">
  <figcaption>The finished shop, as a customer sees it. Every picture in this guide uses a demo copy with a made-up business name, products and prices.</figcaption>
</figure>

## What you need

- **A computer.** A Mac or a Windows PC.
- **An internet connection.**
- **A paid Claude plan.** The part of Claude that builds things is called *Claude Code*. It isn't in the free plan. The cheapest plan that includes it is **Pro**, which was US$20 a month when I wrote this (November 2026). You'll need a bank card. Current prices for your country are on [Anthropic's pricing page](https://claude.com/pricing).
- **The information your project is about.** For me it was a spreadsheet of every product, its code and its price. Most business software has an "Export" button that saves one. If you're not sure, ask whoever set your software up.
- **Some time.** My first version took one evening. I kept improving it for several days after that. You won't be typing code. You'll be answering questions and saying what looks wrong.

## The whole idea in one picture

Building something with Claude is like working with a very fast, very patient builder who has never met you. It doesn't know what you want until you tell it. So the work goes round in a loop.

<div class="g-loop">
  <div><strong>You say what you want</strong>, in your own words. Typos are fine.</div>
  <div><strong>It asks you questions</strong> until it understands, then writes a plan for you to approve.</div>
  <div><strong>It builds</strong>, then tests its own work automatically.</div>
  <div><strong>You try it</strong> on your own phone or computer, and say what's wrong.</div>
</div>
<p class="g-loop-note">Steps 3 and 4 repeat until you're happy.</p>

## Part 1: Getting set up

You only do this once. If you're not sure whether you have a Mac or Windows: a Mac has an Apple logo in the top-left corner of the screen, and Windows has a logo of four squares at the bottom.

1. **Switch on your computer and log in** as you normally would.
2. **Open your web browser.** That's the program you use to visit websites, such as Safari, Chrome or Edge. Click in the long box at the very top, type **claude.ai**, and press Enter (called Return on a Mac).
3. **Create an account.** Click to sign up, and follow the steps on the screen.
4. **Choose the Pro plan** (or a bigger one) from the [pricing page](https://claude.com/pricing), and pay with your card.
5. **Download the Claude app.** Go to [claude.com/download](https://claude.com/download) and choose the download for your computer. The file lands in your Downloads folder. Double-click it.
    - On a Mac, if a window appears showing the Claude icon next to an Applications folder, drag the icon onto the folder.
    - On Windows, follow the steps the installer shows you.
6. **Open the Claude app and sign in** with the account you just made.
    - On a Mac, press the Command and Space keys together, type **Claude**, and press Return.
    - On Windows, click the four-squares logo at the bottom of the screen, type **Claude**, and press Enter.
7. **Make a folder for your project.** A folder is a named place on your computer that holds files, like a drawer.
    - On a Mac, open Finder (the smiling face at the bottom of the screen), click **Documents** on the left, then choose **File → New Folder** from the menu at the top. Call it **my-shop**.
    - On Windows, open File Explorer (the yellow folder at the bottom of the screen), click **Documents**, right-click an empty white space, and choose **New → Folder**. Call it **my-shop**.
    - Then drag your spreadsheet into the **my-shop** folder.
8. **Click "Code"** at the top of the left-hand side of the Claude app. "Chat" is for ordinary conversations. "Code" is the part that can build things. If you only see small pictures there, rest your mouse pointer on each one to see its name.
9. **Choose your folder.** Under the box where you type, there is a row of buttons. Choose **Local**, which means "on this computer". Then click the folder button next to it, choose **Open folder…**, and pick **my-shop**.
10. **Leave the mode on "Manual".** In the same row is a button for how much Claude may do without asking. **Manual** means it asks you before it changes anything. For your first project, leave it there.

<div class="g-window" aria-hidden="true">
  <div class="g-bar"><i></i><i></i><i></i></div>
  <div class="g-body">
    <div class="g-side"><span>Chat</span><span class="on">Code</span></div>
    <div class="g-main">
      <div class="g-box">Type what you want to build…</div>
      <div class="g-row"><span class="tag">Local</span><span class="tag">my-shop</span><span class="tag">Manual</span></div>
    </div>
  </div>
</div>
<p class="g-note">A simplified drawing of the Claude app, not an exact screenshot. The highlighted buttons are steps 8 to 10. Apps change over time. If yours looks different, Anthropic keeps an official step-by-step guide <a href="https://code.claude.com/docs/en/desktop-quickstart">here</a>.</p>

<div class="g-tip"><p><strong>About "Manual" mode.</strong> When Claude wants to change something, it shows you exactly what it will change, and you approve or decline it. If you don't understand what it's asking, don't approve yet. Type <em>"what does this do, in plain English?"</em> and it will explain first.</p></div>

<div class="g-tip"><p><strong>Not sure what to type first?</strong> Something like this works well:</p><p><em>"Hello. I'd like to build an ordering website for my family's business. There's a spreadsheet of our products in this folder. Before you build anything, ask me questions one at a time until you understand what we need."</em></p></div>

## Part 2: The conversation

This is the part that surprised me most. I just talked to it. Here is roughly how it went, using my real messages, lightly edited to leave out names and a few private details.

### 1. Say what you want, plainly

My very first message, typos and all. My spreadsheet was still in my Downloads folder, so I told it where to look.

<div class="g-chat">
  <div class="g-msg g-me"><span class="g-who">Me</span>check my downloads folder, there is a file with the sales of my parents' business, skus, and prices, I want to make a website that allows you to create an account, and order, and there should be another login link where you can manage what is in and out of stock from store side</div>
</div>

("SKUs" are product codes.) That was enough to start. It found the spreadsheet, read every product, and noticed things I hadn't. Some items had no barcode. Some lines weren't really products at all, like "Freight" and "Discount".

### 2. Let it interview you

Before building anything, it asked me questions, one at a time, like a good builder would before quoting a job.

<div class="g-chat">
  <div class="g-msg g-ai"><span class="g-who">Claude</span>Walk me through how an order happens today, from a customer wanting stock to the boxes leaving the warehouse.</div>
  <div class="g-msg g-me"><span class="g-who">Me</span>my mum takes the order via text or wechat, my mum picks the stock, generates an invoice using an app… or customers come to the warehouse and they cash and carry it out, no online storefront</div>
</div>

When I asked for something that wasn't possible, it told me straight away and offered other options. I'd wanted new orders announced to my mum through a messaging app. It explained that a website can't send messages to a personal account on that app, and suggested a text message instead. I went with email.

### 3. Approve the plan

Next it wrote a design: a plain description of what the site would do, who it was for, and what it would *not* do. Before I saw it, a separate Claude, one that hadn't seen our conversation, read the design as if it had to build from it. It listed the questions it couldn't answer on its own.

Those were real business questions. Do the prices include tax? Can shops order less than a full carton? Should delivery fees go on the invoice? Should the site work in Chinese? I answered them all in one message:

<div class="g-chat">
  <div class="g-msg g-me"><span class="g-who">Me</span>inc gst for now, only portal invoices, and make it auto email-able after checking the stock is there in the portal order picking view, make the website nice for ipads. Inners and singles can be sold, splits are handles in person. Discounts + shipping + sundries should be able to add it, add chinese mode. …</div>
</div>

### 4. Let it build, and let it check itself

Then it built the site. You can watch it work through its list. Along the way it writes *tests*: small automatic checks that act like a customer clicking through the site, making sure orders, invoices and payments add up. They run again every time anything changes, so a new feature can't quietly break an old one.

It also found product photos by searching the web, sorted every product into categories, and wrote a user manual for my parents in English and Chinese.

<figure class="g-fig">
  <img src="/assets/guides/built-with-ai/pick-list.jpg" alt="The store's pick list for one order: products grouped by category with ordered and supplied quantities, a delivery line, the total, and a button saying 'Confirm stock and send invoice'." loading="lazy">
  <figcaption>My mum's side: the list she packs from. If she's short on something, she types what she actually packed, then taps one button to send the invoice.</figcaption>
</figure>

<figure class="g-fig">
  <img src="/assets/guides/built-with-ai/invoice.jpg" alt="An invoice showing the items supplied, the total, the payment received, and a 'Short supplied' note saying one item was ordered 5 and supplied 4." loading="lazy">
  <figcaption>The invoice the shop receives by email. Anything she couldn't supply is listed, so there are no surprises at the door.</figcaption>
</figure>

### 5. Try it yourself, and complain in your own words

This is your most important job. Open the site on your own phone. Tap everything. When something's off, just say so. You don't need technical words. This is a real message I sent ("cooked" is slang for broken):

<div class="g-chat">
  <div class="g-msg g-me"><span class="g-who">Me</span>mobile cart view cooked, too small can't see name qty subtotal cleanly</div>
  <div class="g-msg g-ai"><span class="g-who">Claude</span>Rebuilding the cart line for phones. Each item becomes two rows: photo and name on top with the remove button, then a quantity stepper and the line total underneath.</div>
</div>

And it did. Every request after that was just as plain: *"add global search and novelties category"*, *"ability to assign % discount to customers"*, *"allow admin to change product category and to add new categories"*.

<div class="g-trio">
  <figure class="g-fig">
    <img src="/assets/guides/built-with-ai/phone-catalogue.jpg" alt="The catalogue on a phone, showing products with photos, prices and Add to cart buttons." loading="lazy">
    <figcaption>Catalogue on a phone.</figcaption>
  </figure>
  <figure class="g-fig">
    <img src="/assets/guides/built-with-ai/phone-cart.jpg" alt="The cart on a phone, with each item's name, a quantity stepper, the line total and the subtotal." loading="lazy">
    <figcaption>The cart, after my complaint.</figcaption>
  </figure>
  <figure class="g-fig">
    <img src="/assets/guides/built-with-ai/phone-chinese.jpg" alt="The shop's home page in Chinese on a phone." loading="lazy">
    <figcaption>One tap switches to Chinese.</figcaption>
  </figure>
</div>

## Part 3: Putting it online

A website on your own computer can only be seen by you. To let shops reach it, it has to live on a computer that's always switched on and connected to the internet, called a *server*.

I already had a computer running for my own projects, so I asked Claude to set the shop up on that. It did the technical work, and stopped and asked me to step in whenever something needed me to log in to an account myself.

You don't need your own server. Ask Claude something like *"what's the simplest way to put this online, and what will it cost each month?"* It will suggest a hosting service. You create that account yourself, and Claude tells you what to click.

<figure class="g-fig">
  <img src="/assets/guides/built-with-ai/admin-products.jpg" alt="The store's product list, with a search box, category filters, and for each product a category dropdown and an In stock button." loading="lazy">
  <figcaption>The store side, where my mum switches products in and out of stock, moves them between categories, and adds new ones with a photo from her iPad.</figcaption>
</figure>

<div class="g-tip">
<p><strong>What this guide doesn't cover.</strong> Before real customers use a site you've built, think about:</p>
<ul>
<li><strong>Security:</strong> how people's logins, orders and details are protected.</li>
<li><strong>Backups:</strong> what happens if the computer it runs on breaks.</li>
<li><strong>A proper web address</strong> of your own.</li>
<li><strong>Running costs:</strong> your Claude plan, plus hosting and maybe a web address and email. Paid plans also have usage limits, so a big project may take a few sittings or a bigger plan.</li>
</ul>
<p>Claude can help with every one of these, so ask it. But before you trust a site with real customers' details or money, have a person who knows what they're doing look it over. An AI review is useful, but it isn't a security audit.</p>
</div>

## It makes mistakes, so make it check

Claude is good, but it isn't perfect. Here's what helped:

- **I asked it to get a second opinion.** Before anything important, a separate Claude reviewed the work. It caught real problems. One was a cart button that, tapped twice very quickly, could save the wrong quantity. Another was the site sending some business information to customers' browsers that they had no need to see. Both were fixed.
- **I checked things myself.** I opened the site on my own phone and tried it before my parents ever saw it.
- **It told me when it was unsure.** When it couldn't confirm something, it said so instead of guessing. For example, it couldn't be sure photos taken on my mum's iPad would come out the right way up, so it asked me to test that on the real device.

## Tips if you've never done this before

- **Talk to it like you'd text a capable friend.** Full sentences aren't required.
- **Describe what you see, not the fix.** "The cart is too small on my phone" works better than guessing at a solution.
- **Answer its questions in your own words.** The questions are where the real decisions happen.
- **Ask it to explain anything you don't understand** before you approve it.
- **Never paste a password, card number or bank login into the chat.** When something needs one, Claude will tell you where to type it yourself.
- **Ask it to test its work, and to have the work reviewed** before you rely on it.
- **Keep it small at first.** One clear job is easier to get right than ten at once.
- **Your judgement still matters.** It builds what you describe. You're the one who knows what your family, your customers or your business actually need.

## A few words you'll hear

- **Website, app:** for our purposes, the same thing. Something you open in a web browser.
- **Folder:** a named place on your computer that holds files, like a drawer.
- **Server:** a computer that's always on, so other people can reach your website.
- **Database:** where the website keeps its information: products, accounts, orders.
- **Test:** an automatic check that something still works.

That's it. The hardest part isn't technical. It's knowing what you want, and noticing when something isn't quite right. You already know how to do both.
