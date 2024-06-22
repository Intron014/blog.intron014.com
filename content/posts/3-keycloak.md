+++
title = '401 - Unauthorized'
description = 'Keycloak, a new beginning?'
date = 2023-05-19T00:00:00+02:00
draft = false
tags = ['Docker', 'SSO']
+++
It all began that day... when we decided to use a [SSO](https://url.intron014.com/nIbmm) called [Keycloak](https://url.intron014.com/eP51J) for all the server services that we have, such as Grafana, Gitea, Portainer, Cloudflare Tunnels... It was all going great, so well in fact, that we decided to remove the root account in Portainer in favour of the new fancy SSO, so we all got our new administrator accounts and all well and good, right?

![Keycloak](/static/522092326.png)


Wrong. Apparently the username that is given inside Portainer is the key to all, and if changed, Portainer wouldn't be able to ID the user, therefore, kicking them out. Yeah... that's what happenned, and to two of us, what are the chances?!

We scrambled looking inside Portainer's .sqlite file to find the usernames and change them, to no avail unfortunately. We were devastated after several hours trying to find a solution and trying to contact the third member of the server (who was vacationing somewhere with very poor cell reception), so the only thing that was left to do was to wait...

![PhpMyAdmin](/static/546897457.png)

But wait! "What if we changed the username in Keycloak to the one that is in Portainer?" - I said.

And so I did, entering the almighty [phpMyAdmin](https://url.intron014.com/IjQLZ) and trying to find the database that was holding all our usernames.
Once it was changed... voilá! There it was! Portainer in all it's admin glory. 

So, moral of the story? If it works, don't you dare touch it! :)