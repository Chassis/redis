# Redis
A Chassis extension to install and configure Redis on your server.

## Usage
1. Add this extension to your extensions directory `git clone git@github.com:Chassis/redis.git extensions/redis` or alternatively add the following to one of your [`.yaml`](https://github.com/Chassis/Chassis/blob/master/config.yaml) files:
   ```
   extensions:
     - chassis/redis
   ```
2. Run `vagrant provision`
3. Install `wp-redis` plugin, and symlink `object-cache.php` to your content directory, if you haven't already. example:
```
vagrant ssh
wp plugin install wp-redis
WPCONTENTDIR=$(wp eval 'echo WP_CONTENT_DIR;')
cd $WPCONTENTDIR
ln -s wp-redis/object-cache.php .
```

(Note: wp-redis might be handling the symlinking part soon, see [#126](https://github.com/pantheon-systems/wp-redis/issues/126), eliminating the need for step 3 altogether)

## Contributors

Props to [@shadyvb](https://github.com/shadyvb/) for the initial versions of the extension, and our [contributors](https://github.com/Chassis/redis/graphs/contributors).
