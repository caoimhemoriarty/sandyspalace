---
title: PiHole Blocking for Samsung Junk TVs
---

<div>
    <p>
        I hate modern technology, I fucking hate smart applications and the Internet of Things, and I utterly despite Smart TVs. Naturally I had to turn this into a hobby.
    </p>
    <p>
        I already have a Raspberry Pi 4B running <a href="https://pi-hole.net/">PiHole</a> for my home network, which I might make another blog post about. What this post relates to is the specific blocking of Samsung TV's dumb shit, and preventing it from updating the firmware.
    </p>
    <p>
        By default, Samsung Smart TVs send way too much analytics back to home base. Out of principle, I wanted to shut this down. Previous blocklists running on the PiHole proved this could work. 
    </p>
    <p>
        Also blocking firmware updates has now become crucial, as the newer updates include <a href="https://www.cnet.com/tech/home-entertainment/samsungs-2025-tvs-get-all-the-ai-extras-nobody-asked-for/">AI-generated total junk</a> that is burned into your home screen. The home screen is already fucking terrible as-is.
    </p>
    <p>
        With some light testing (read: adding lines until the updates stop and the TV doesn't break), I've created this blocklist that aims to block future updates, while still allowing the TV to function:
    </p>
    <p>
    <a href="https://sandyspalace.ie/assets/files/samsung_pihole.txt">Blocklist</a>
    </p>
    <p>
        I will update this post based on observations over the next few days. Feel free to link directly to the above URL, I've got plenty of server capacity.
    </p>
    <p>
        <b>5th Feb 2025</b>: PiHole is successfully blocking most Samsung CDN domains. Pop-up for firmware update hasn't appeared after a few soft resets. This may only occur a set amount of times per day, so I'll check for this tomorrow. TV otherwise working "well".
    </p>
    <p>
        <b>9th Feb 2025</b>: Popup notification for firmware updates have appeared again. I can't immediately see any queries going to Samsung domains. Fuckin delightful.
    </p>
    <p>
        <b>13th Feb 2025</b>: Still not seeing what request is slipping through PiHole. If the notification has been locally 'installed', then we could be in trouble. I'm never gonna install it, and can't figure out how to get it to fuck off.
    </p>
    <script defer src="https://comments.oakreef.ie/comentario.js"></script>
<comentario-comments></comentario-comments>
</div>