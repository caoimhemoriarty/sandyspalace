---
title: New Dedicated Server Time!
---

<div>
    <p>
        Did I need a new server? Absolutely not. So here we are.
    </p>
    <p>
        My existing Leaseweb server (provided via Hosting By Design) is a fairly capable machine:
        <ul>
            <li>CPU: Xeon E3-1230</li>
            <li>RAM: 32GB</li>
            <li>Storage: 4 x 8 TB HDDs, configured in a RAID 5 array</li>
            <li>Connection: Dedicated 1GBps line, 100TB monthly traffic cap</li>
        </ul>
    </p>
    <p>
        However I want to make a few improvements.
    </p>
    <p>
        First, and most importantly, I'm fucking itchy and just love trying new shit out.
    </p>
    <p>
        Otherwise, I was eager to try different RAID configurations to see what could speed up my seedbox. Price wasn't a major concern, but I felt I wasn't utilising parts of my existing setup, mostly with the HDD configuration.
    </p>
    <p>
        Hetzner and OVH were my main alternative choices, however I couldn't justify the cost of the OVH servers. They were too over-specced on non-HDD elements, which I don't need as much right now. Therefore I waited for a decent price on a Hetzner server auction, and snapped this up:
        <ul>
            <li>CPU: Xeon E3-1271</li>
            <li>RAM: 32GB</li>
            <li>Storage: 4 x 10 TB HDDs, configured in a RAID 10 array</li>
            <li>Connection: Dedicated 1GBps line, unlimited traffic cap</li>
        </ul>
    </p>
    <p>
        Not exactly an earth-shattering change. The CPU upgrade isn't noteworthy. The monthly traffic cap likely won't exceed 50TB with my existing setup. So the major gains came from the RAID 10 configuration, which I am still exploring the optimisation side of.
    </p>
    <p>
        Here have been my adventures so far in getting it set up and replacing my old server:
    </p>
    <p>
        <b>Rescue system + Linux install:</b> Easy af, same as Leaseweb. RAID configuration was configured via the Hetzner rescue system rather than during setup with Hosting By Design, which was a neat change.
    </p>
    <p>
        <b>Swizzin install:</b> Same setup, just run {% highlight plaintext %}bash <(curl -sL s5n.sh) && . ~/.bashrc{% endhighlight %}then stare at the Advanced Options while touching none of them, wait a few mins, and done.
    </p>
    <p>
        <b>Application install:</b> A bit trickier this time. All installs were done through Swizzin's Box system, same as last time - Nginx, File Browser, Jellyfin, Panel, QBitTorrent, Plex, Vsftpd. However, a huge roadblock was <a href="https://linustechtips.com/topic/1531520-plex-blocks-ip-addresses-from-hetzner-as-of-october-12-2023/"> Hetzner server IP addresses being blocked by Plex</a>. I tried working around this, but couldn't find a usable solution.
    </p>
    <p>
        Therefore I had to find a new media server, and Jellyfin (my preferred client) was notoriously difficult working with IP addresses with self-signed SSL certificates. This is fine when connecting via PCs and other tech you actually control, much less so on a Smart TV. They simply don't let the user override the security warning. The main solution to this seems to be buying a cheap domain name annually, getting an independent SSL certificate issued for it, then connecting your media server to it. However, I'm a lazy cheapskate :3
    </p>
    <p>
        Enter Emby, the semi-closed-source client that Jellyfin forked away from. Same as Plex, the Quick Connect feature is what let me circumvent the SSL self-signed certificate issue. Functionally it's 95% similar to Jellyfin, but I'm not as smug when using it. However, a huge advantage is that it can be located easily on Smart TV's app stores, making it much more straightforward to install versus Jellyfin, which required root/dev access.
    </p>
    <p>
        <b>Porting old server files</b>: Still ongoing. Most files are permanently seeded on QBitTorrent, so I just mass copied the Magnet IDs of the torrents to re-download them on the new server. Which has the additional bonus of letting the other seeds in the network share the network load :3
    </p>
    <p>
        For any files I wasn't torrenting, running {% highlight plaintext %}scp -r /directory_to_copy root@XXX.XXX.XXX.XX:/directory_to_copy_to {% endhighlight %} is sufficient. Probably. Still ongoing.
    </p>
    <p>
        Once fully ported, I plan to run some speed comparisons, test the performance gain of the RAID 10 configuration, then drop the slower server.
    </p>
    <p>
        <b>20th Feb Update:</b> I have decided that Hetzner actually sucks
    </p>
    <p>
        <img src="/assets/images/blog/hetzner.png">
    </p>

</div>