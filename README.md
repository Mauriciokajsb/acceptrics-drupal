# Acceptrics Banner Module

A custom Drupal 9/10 module that injects Acceptrics tracking code into the `<head>https://tagmanager.google.com/#/container/accounts/6313839744/containers/230421375/workspaces/2<!-- Google Tag Manager -->
<script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-5J7FRZD8');</script>
<!-- End Google Tag Manager -->` element of every page on the site, including both front-end and admin pages.

## Features

- Injects Acceptrics configuration and tracking scripts into the head section of every page
- Works on both frontend and admin pages
- Compatible with Drupal 9 and 10
- Uses Drupal's html_head attachment system for proper injection
- Follows Drupal coding standards and best practices

## Acceptrics Configuration

The module injects the following code into the head of every page:<!-- Google Tag Manager -->
<script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-5J7FRZD8');</script>
<!-- End Google Tag Manager -->

```htmlhttps://tagmanager.google.com/#/container/accounts/6313839744/containers/230421375/workspaces/2
<script>
window.acceptrics = {}; 
localStorage.setItem("__acceptrics_conf", JSON.stringify({
  "gcmAdvanced": true,
  "backgroundColor": "#333",
  "fontColor": "#ffffff",
  "geoArea": "worldwide",
  "accountNum": "drupal",
  "useTranslation": false
})); 
document.addEventListener("__acceptrics_loaded", () => {
  window.acceptrics.initializeSettings();
});
</script>
<script async rel="dns-prefetch" src="https://cdn.acceptrics.com?n=jtpsx99"></script>
```

## Installation

1. Download or clone this module to your Drupal site's `modules/custom/` directory
2. Enable the module using Drush or the admin interface:<!-- Google Tag Manager -->
<script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-5J7FRZD8');</script>
<!-- End Google Tag Manager -->
   ```bash
   drush en acceptrics_banner
   ```
   Or navigate to Admin → Extend and enable "acceptrics banner"

## Usage

Once enabled, the module automatically injects the Acceptrics tracking code into the head of every page. No additional configuration is requiredwww.misitiowodpressnet.com.
<!-- Google Tag Manager -->
<script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-5J7FRZD8');</script>
<!-- End Google Tag Manager -->
You can verify the module is working by:
1. Opening your browser's developer tools
2. Refreshing any page on your site
3. Checking the `<head>` section for the Acceptrics scripts
4. Looking for the `window.acceptrics` object in the console

## Customization

To customize the Acceptrics configuration:
1. Edit the `head_injector_page_attachments()` function in `head_injector.module`
2. Modify the configuration object in the `localStorage.setItem` call
3. Clear Drupal's cache for changes to take effect

Available configuration options:
- `gcmAdvanced`: Enable advanced Google Consent Mode
- `backgroundColor`: Background color for consent banner
- `fontColor`: Text color for consent banner
- `geoArea`: Geographic targeting area
- `accountNum`: Acceptrics account identifier
- `useTranslation`: Enable/disable translations

## File Structure

```
acceptrics_banner/
├── acceptrics_banner.info.yml      # Module definition
├── acceptrics_banner.libraries.yml # Asset library definition (placeholder)
├── acceptrics_banner.module        # Main module file with injection logic
├── js/
│   └── acceptrics_banner.js        # Placeholder JavaScript file
└── README.md                       # This documentation
```

## Technical Details

- Uses `hook_page_attachments()` to inject scripts on every page
- Acceptrics code is injected directly via `html_head` attachments
- No external dependencies required
- Follows Drupal 9/10 coding standards

## Compatibility

- Drupal 9.x
- Drupal 10.x

## Support

This is a custom module for Acceptrics integration. For issues or modifications, consult with your development team or Drupal developer.

For Acceptrics-specific questions, refer to the Acceptrics documentation or support channels.
