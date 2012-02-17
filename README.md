Init scripts
==

These are my personal init scripts that I use in my systems for:

- `nginx` - server
- `phpfcgi` - php fastcgi proxy
- `node` - node.js proxy
- `rw` - start services needed for my website
- `noderw` - start services needed for the node.js version of my website

I've broken these down by linux flavour (I only use two flavours):

- debian
- centos

Usage
--

To set this up all you have to do is create symlinks from `/etc/init.d/` to the `<linux-flavour>/init` folder.

```
ln -s /home/robin/Projects/initsetup/debian/init/nginx /etc/init.d/.
ln -s /home/robin/Projects/initsetup/debian/init/node /etc/init.d/.
ln -s /home/robin/Projects/initsetup/debian/init/phpfcgi /etc/init.d/.
ln -s /home/robin/Projects/initsetup/debian/init/rw /etc/init.d/.
ln -s /home/robin/Projects/initsetup/debian/init/noderw /etc/init.d/.
```

### Dependencies

`php` will need to be installed for `phpfcgi` to work.

#### Node

`node` has a dependency on `node_server.js` from my `web-controllers` project existing at `/var/web-controllers/node_server.js`.

```
git clone git://github.com/nottrobin/web-controllers.git /var/web-controllers
```

#### Nginx

Nginx server will try to read its configuration out of `/etc/nginx/nginx.conf`.

