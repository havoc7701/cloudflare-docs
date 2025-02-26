---
pcx_content_type: reference
title: Settings
meta:
  title: Zaraz settings
---

# Zaraz settings

To configure Zaraz's general settings, select [**Zaraz**](https://dash.cloudflare.com/?to=/:account/:zone/zaraz) > **Settings**. Make sure you save your changes, by selecting the **Save** button after making them.

## Workflow

Allows you to choose between working in Real-time or Preview & Publish modes. By default, Zaraz instantly publishes all changes you make in your account. Choosing Preview & Publish lets you test your settings before committing to them. Refer to [Preview mode](/zaraz/history/preview-mode/) for more information.

## Web API

### Debug Key

The debug key is used to enable Debug Mode. Refer to [Debug mode](/zaraz/web-api/debug-mode/) for more information.

### E-commerce tracking

Toggle this option on to enable the Zaraz E-commerce API. Refer to [E-commerce](/zaraz/web-api/ecommerce/) for more information.

## Compatibility

### Data layer compatibility mode

Cloudflare Zaraz offers backwards compatibility with the `dataLayer` function found in tag management software, used to track events and other parameters. You can toggle this option off if you do not need it. Refer to [Data layer compatibility mode](/zaraz/advanced/datalayer-compatibility/) for more information.

### Single Page Application support

When you toggle Single Page Application support off, the `pageview` trigger will only work when loading a new web page. When enabled, Zaraz's `pageview` trigger will work every time the URL changes on a single page application. This is also known as virtual page views.

## Privacy

Zaraz offers privacy settings you can configure, such as:

- **Remove URL query parameters**: Removes all query parameters from URLs. For example, `https://example.com/?q=hello` becomes `https://example.com/`.

- **Trim IP addresses**: Trims part of the IP address before passing it to server-side loaded tools, to hide it from third-parties.

- **Clean User Agent strings**: Clear sensitive information from the User Agent string by removing information such as operating system version, extensions installed, among others.

- **Remove external referrers**: Hides the page referrers URL if the hostname is different from the website's.

- **Cookie domain**: Choose the domain on which Zaraz will set your tools' cookies. By default, Zaraz will attempt to save the cookies on the highest-level domain possible, meaning that if your website is on `foo.example.com`, the cookies will be saved on `example.com`. You can change this behavior and configure the cookies to be saved on `foo.example.com` by entering a custom domain here.

## Injection

### Auto-inject script

This option automatically injects the script needed for Zaraz to work on your website. It is turned on by default.

If you turn this option off, Zaraz will stop automatically injecting its script on your domain. If you still want Zaraz functionality, you will need to add the Zaraz script manually. Refer to [Load Zaraz manually](/zaraz/advanced/load-zaraz-manually/) for more information.

### Iframe injection

When toggled on, the Zaraz script will also be injected into `iframe` elements.

## Endpoints

Specify custom URLs for Zaraz's scripts. You need to use a valid pathname:

```txt
/<PATHNAME>/<FILE.JS>
```

This is an example of a custom pathname to host Zaraz's initialization script:

```txt
/my-server/my-scripts/start.js
```

### HTTP Events API

Refer to [HTTP Events API](/zaraz/http-events-api/) for more information on this endpoint.

## Other

### Bot Score Threshold

Choose whether to prevent Zaraz from loading on suspected bot-initiated requests. This is based on the request's [bot score](/bots/concepts/bot-score/) which is an estimate, and therefore cannot be guaranteed to be always accurate.

The options are:

- **Block none**: Load Zaraz for all requests, even if those come from bots.
- **Block automated only**: Prevent Zaraz from loading on requests from requests in the [**Automated** category](/bots/concepts/bot-score/#bot-groupings).
- **Block automated and likely automated**: Prevent Zaraz from loading on requests from requests in the [**Automated** and **Likely Automated** category](/bots/concepts/bot-score/#bot-groupings).

### Context Enricher

Refer to the [Context Enricher](/zaraz/advanced/context-enricher/) for more information on this setting.
