---
title: How to improve your site using Cloudflare.
published: true
---
Hello to my first actuall blog post! So, probably, alot of you are using cloudflare. *I guess thats also why you read this* - well,  as you can see in this graph i found some while ago, the marketshgare of cloudflare **just** as a CDN is massive.
![Cloudflare Usage](/assets/cloudflare-usage.png)
But it not just serves as a CDN. It's functions reach from DNS, to proxying, to DDOS protecting, just to [name a few](https://www.cloudflare.com/what-is-cloudflare/). And, while it's great on the webadmin's part, there are a lot of problems on the client's side, especially if you're trying to use tor or most of the vpns. But that isnt part of this blog either, eventhough I'm probably going to mention it soon ish.

# Improve the clients experience
Alright, so this part will vary for your thinking sometimes, but should be fine most of the time.<br>Most of this was found by just administrating some sites (in fact, i use cloudflare rn too), so it should work without anyproblems for almost all hosting solutions. 

### Enable Tor traffic to reach the site directly

This is quite a easy one, just go to Security > Firewall Rules and klick add rule. Give it a fancy name, and allow  **Country | equals | Tor** and action **allow**. 
![Tor Firewall rule](/assets/allow_tor_traffic.png)
This, at least for me, does not get your site ddosed faster. **I am NOT responsable for any ddos or other attacks, coming from enabling.** As always, DYR (Do your research). If you, as a web master know you're being attacked more often, you shouldnt enable this. But for anyone else, it's a nice thing for people circumventing censorship or just wanting to be anonymus to do.

### Caching settings (production)

So, I'd personally think these settings are only for production (e.g. you might not want to have your site crawled by the internet archive), but anyways, here we go! <br>
All these settings can be found by going to Caching > Configuration. Ideas are sortedby usefullness
1. Set the Browser Cache TTL to a higher time <br>
 It speeds up your site, does not enable easy rearranging though (you might have to clear some caches then). I personally have it set to 1 day.
2. Enable Always Online™ (may be already enabled)<br>
Does what it says, it "Keep your website online for visitors when your origin server is unavailable. Always Online serves limited copies of web pages to users instead of errors when your server is unreachable.". You'll have to agree to the [terms]https://www.cloudflare.com/supplemental-terms/#AOBeta), and you might as well DYR for the internet archive.
3. Enable Crawler hints
It trys to help with getting your site on search engines, didnt help much for me though. You'll have to, again, agree with the [terms](https://www.cloudflare.com/supplemental-terms/#crawler-hints).
4. Argo Tiered Cache (Under Caching > Tiered Cache)
Helps if you need a cdn of some kind. Havent had that much experince my self, but it basically trys to find the Server with the lowest load to serve as a CDN.

**The article is unfinished as is, but the tips are still valid**

###### Sources:
<font size="1">
https://kinsta.com/wp-content/uploads/2021/02/cdn-customer-count-chart-1.png - cloudflare-usage.png <br>
https://dash.cloudflare.com - Screenshots of settings <br>
https://developers.cloudflare.com/cache/about/edge-browser-cache-ttl/#browser-cache-ttl - caching ttl <br>
https://developers.cloudflare.com/cache/about/edge-browser-cache-ttl/#browser-cache-ttl - ​​
Browser Cache TTL <br>
https://blog.cloudflare.com/tiered-cache-smart-topology/ - Argo cache <br>
https://blog.cloudflare.com/crawler-hints-how-cloudflare-is-reducing-the-environmental-impact-of-web-searches/ - Crawler hints <br>
https://developers.cloudflare.com/cache/about/always-online/ - Always online