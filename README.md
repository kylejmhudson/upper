<img src="https://github.com/ostark/upper/blob/master/resources/upper.png" height="80px"/>


# The pep pill for your Craft site

Upper speeds up Craft dramatically using a **Cache Proxy** in front of your webserver. 

The Plugin adds the neccessary `Cache-Control` and `XKEY/Surrogate-Key/Cache-Tag` headers to your pages. 
When Entries or Sections get updated in the Control Panel it takes care of the cache invalidation. 

If you need an introduction to HTTP Caching, I highly recommend [this article](https://blog.fortrabbit.com/mastering-http-caching). 

## Supported Cache Drivers

* [KeyCDN](https://www.keycdn.com) (CDN/SaaS)
* [Fastly](https://www.fastly.com) (CDN/SaaS)
* Varnish with XKEY support (your own proxy)
* Dummy (does nothing)

## Installation

1. Install with Composer via `composer require ostark/upper` from your project directory
2. Install plugin with this command `php craft install/plugin upper` or in the Craft CP under Settings > Plugins
3. A new configuration file gets generated automatically in `your-project/config/upper.php`.



### Fastly Setup

```
UPPER_DRIVER=fastly
FASTLY_API_TOKEN=<REPLACE-ME>
FASTLY_SERVICE_ID=<REPLACE-ME>
```

### KeyCDN Setup

```
UPPER_DRIVER=keycdn
KEYCDN_API_KEY=<REPLACE-ME>
KEYCDN_ZONE_URL=<REPLACE-ME>.kxcdn.com
KEYCDN_ZONE_ID=<REPLACE-ME>
```

### Varnish Setup

```
UPPER_DRIVER=varnish
VARNISH_URL=<REPLACE-ME>
```

### Tuning

With `Cache-Control` headers you can disabled caching for certain templates:

```
{% header "Cache-Control: private, no-cache" %}
```



### Performance results
![example](https://github.com/ostark/upper/blob/master/resources/preformance.png)

### Cache Tag Headers
![example](https://github.com/ostark/upper/blob/master/resources/response-header.png)


## Disclaimer

Even if the name of the plugin and some wordings are intentional, the author does not glorify any drug abuse.
The plugin is inspired by the [joshangell/Falcon](https://github.com/joshangell/Falcon).
