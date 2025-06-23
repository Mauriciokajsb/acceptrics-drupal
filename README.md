# Acceptrics Banner Module

A custom Drupal 9/10 module that injects Acceptrics tracking code into the `<head>` element of every page on the site, including both front-end and admin pages.

## Features

- Injects Acceptrics configuration and tracking scripts into the head section of every page
- Works on both frontend and admin pages
- Compatible with Drupal 9 and 10
- Uses Drupal's html_head attachment system for proper injection
- Follows Drupal coding standards and best practices

## Acceptrics Configuration

The module injects the following code into the head of every page:

```html
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
2. Enable the module using Drush or the admin interface:
   ```bash
   drush en head_injector
   ```
   Or navigate to Admin → Extend and enable "head injector"

## Usage

Once enabled, the module automatically injects the Acceptrics tracking code into the head of every page. No additional configuration is required.

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
head_injector/
├── head_injector.info.yml      # Module definition
├── head_injector.libraries.yml # Asset library definition (placeholder)
├── head_injector.module        # Main module file with injection logic
├── js/
│   └── head_injector.js        # Placeholder JavaScript file
└── README.md                   # This documentation
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
