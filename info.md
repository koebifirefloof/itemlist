---
title: Info
layout: page
permalink: /info
store: false
---

{%- assign utils = false -%}
{%- assign lootboxes = false -%}
{%- assign puppeteer = false -%}
{%- for mod in site.data.modlist -%}
    {%- case mod.name -%}
        {%- when 'ToolkitUtils' %}
            {%- assign utils = true -%}
        {%- when 'ToolkitUtils - Testing' -%}
            {%- assign utils = true -%}
        {%- when 'Puppeteer' -%}
            {%- assign puppeteer = true -%}
        {%- when 'TwitchToolkit - Lootboxes' -%}
            {%- assign lootboxes = true -%}
    {%- endcase -%}
{%- endfor -%}


{%- assign bal = '!bal' -%}
{%- assign buy = '!buy' -%}
{%- for command in site.data.commands -%}
    {%- if command.data.isBal -%}
        {%- assign bal = command.usage -%}
        {%- continue -%}
    {%- endif -%}

    {%- if command.data.isBuy -%}
        {%- assign buy = command.usage -%}
        {%- continue -%}
    {%- endif -%}
{%- endfor -%}

# Welcome

Welcome to [{{ site.data.social.twitch }}](https://twitch.tv/{{ site.data.social.twitch }})'s stream.
This stream uses the mod
[Twitch Toolkit](https://steamcommunity.com/sharedfiles/filedetails/?id=1718525787) to provide an
interactive experience. There's a lot to the mod that may seem complicated to even more experienced
users, but this short guide will help you get the hang of things.

## What is Twitch Toolkit?

Twitch Toolkit is a mod by hodlhodl that allows viewers to affect the game in a number of ways. The
most prominent is its [store]({{- "/" | relative_url -}}), which allows you to purchase a number of
things the streamer curated. Depending on the purchase, these things appear in-game or affect the
game in some way. Another way viewers can interact with the game is through the mod's polls. The
choices in these polls depend heavily on what's enabled in the mod. This mod can cause a lot of chaos,
and Koebi reserves the right to remove anything that could be TOO disruptive.

## What Are Coins?

Coins are the mod's currency. You can view your balance by using the `{{ bal }}` command. 

{% if utils == true %}
You'll notice the balance command may have some new emojis. If that's the case, here is an overview
of the emojis as follows:

- 💰 represents the amount of coins you current have.
- ⚖ represents your current karma.
- 📈 represents the amount of coins you gain everytime the mod awards coins.
- 📉 represents the amount of coins you lose everytime to mod awards coins.

{% endif %}


You get one lootbox full of coins every stream! You can open this lootbox by using the `!openlootbox`
command, as well as check the number of lootboxes you have with `!lootboxes`.


<br/>
## What is Karma?

Karma is a system in the mod that tries to limit the amount of negative events a viewer can purchase at
one time. This system works by directly modifying that amount of coins viewers get everytime the mod
awards coins. This means that the lower you karma is, the lower your coin gain is. The hope is that
negative events get spread out more so the colony can recover.

## How Do I Use Twitch Toolkit?

You can use Twitch Toolkit in a number of ways -- the most prominent way is through its
[commands]({{- "/commands" | relative_url -}}). The more important command is the `{{- buy -}}`
command, which is the mods entry point into purchasing things from the store. Other notable commands
are the `!mypawn` commands, which allow you see various information about your pawn. We won't cover
every command here, but most commands should generally be self-descriptive or have a description of
what they do on the [commands]({{- "/commands" | relative_url -}}) page.


<br/>
## How do I buy a pawn?

Use `!buy pawn 1` to buy your way into the colony. It costs 2500 coins. Once created, Koebi can assign
you a fursona and set your sexuality preferences (gay, bisexual, polyamorous, asexual) manually. Being
straight still costs 3500 coins. You can only have one pawn in the colony at a time, if you try to buy
a second one, it will be deleted and you will not be refunded your coins!
