# Edge Tag Installation Guide

This guide provides step-by-step instructions for installing the Edge Tag tracking script on the Takeya and My Thermo Flask website.

## Overview

The Edge Tag script enables event tracking and data collection for the Takeya and My ThermoFlask websites. This installation requires code to be added to both the `<head>` section and various page templates throughout the site.

---

## Overview

### Edge Tag Technical Requirements

The implementation of Edge Tag requires the following:

1. **Inline code modification to the Takeya and My ThermoFlask website.** 
   - New code snippets that initialize Edge Tag and route event data through Edge Tag.

---

# Takeya

## Step 1: Install Base Script in Head Section

Copy the code below and paste it into the `<head>` of the Takeya website.

```html
<script>
  window.edgetag=window.edgetag||function(){(edgetag.stubs=edgetag.stubs||[]).push(arguments)};
</script>
<script async type="text/javascript" src="https://kkqbi.takeyausa.com/load"></script>

<script>
edgetag('init', {
    edgeURL: 'https://kkqbi.takeyausa.com',
    disableConsentCheck: false
  })
</script>

<script>
edgetag('consent', {all: false, necessary: true, advertising: false, analytics: false})
</script>
```

---

## Step 2: Add Event Tracking Scripts

Below are examples of the event snippets should be added to the body of the Takeya website. **All code snippets should be wrapped in `<script>` tags.**

### PageView Event

Add the below code to **every page** of the Takeya website:

```javascript
edgetag('tag', 'PageView')
```

### Purchase Event

Add the code below to the page template where `fbq('track', 'Purchase');` is used. The `value` and `currency` should be dynamically populated using the dataLayer.

```javascript
edgetag('tag', 'Purchase', { value: 10.0, currency: 'USD' })
```

---

## Step 3: User Data Collection

To improve event match rate, dynamically populate the code below based on the details provided at `https://takeyausa.com/checkouts`.

**Additional details:** [Edge Tag User Data Documentation](https://app.edgetag.io/docs/js#user)

**Note:** All code snippets should be wrapped in `<script>` tags.

```javascript
edgetag('data', {
    email: 'user@domain.com',
    phone: '+1234567890',
    firstName: 'John',
    lastName: 'Doe',
    city: 'fremont',
    state: 'CA',
    country: 'US',
    zip: '12345',
  })
```

## Step 4: Wicked Reports Tracking Script
Copy the code below and paste it into the `<head>` of the Takeya website.
```javascript
<script type="text/javascript" src="https://widget.wickedreports.com/v2/5148/wr-85b7833975cf37e6dae7ad4870acdee5.js" async></script>
```
---

# My Thermo Flask

## Step 1: Install Base Script in Head Section

Copy the code below and paste it into the `<head>` of the Thermo Flask website.

```html
<script>
  window.edgetag=window.edgetag||function(){(edgetag.stubs=edgetag.stubs||[]).push(arguments)};
</script>
<script async type="text/javascript" src="https://rtrvr.mythermoflask.com/load"></script>

<script>
edgetag('init', {
    edgeURL: 'https://rtrvr.mythermoflask.com',
    disableConsentCheck: false
  })
</script>

<script>
edgetag('consent', {all: false, necessary: true, advertising: false, analytics: false})
</script>
```

---

## Step 2: Add Event Tracking Scripts

Below are examples of the event snippets should be added to the body of the Thermo Flask website. **All code snippets should be wrapped in `<script>` tags.**

### PageView Event

Add the below code to **every page** of the Thermo Flask website:

```javascript
edgetag('tag', 'PageView')
```

### Purchase Event

Add the code below to the page template where `fbq('track', 'Purchase');` is used. The `value` and `currency` should be dynamically populated using the dataLayer.

```javascript
edgetag('tag', 'Purchase', { value: 10.0, currency: 'USD' })
```

---

## Step 3: User Data Collection

To improve event match rate, dynamically populate the code below based on the details provided at `mythermoflask.com/checkouts`.

**Additional details:** [Edge Tag User Data Documentation](https://app.edgetag.io/docs/js#user)

**Note:** All code snippets should be wrapped in `<script>` tags.

```javascript
edgetag('data', {
    email: 'user@domain.com',
    phone: '+1234567890',
    firstName: 'John',
    lastName: 'Doe',
    city: 'fremont',
    state: 'CA',
    country: 'US',
    zip: '12345',
  })
```

## Step 4: Wicked Reports Tracking Script
Copy the code below and paste it into the `<head>` of the Thermo Flask website.
```javascript
<script type="text/javascript" src="https://widget.wickedreports.com/v2/4985/wr-f3fe88438743cab4a7228429b57255fa.js" async></script>
```
---

## Important Notes

- Ensure all JavaScript code snippets are wrapped in `<script>` tags when implementing
- Dynamic values (such as purchase amounts, user data) should be populated from your dataLayer or backend data
- The user data fields should be populated with actual user information from the checkout process

---

## Related Documentation

- [Edge Tag JavaScript SDK Documentation](https://app.edgetag.io/docs/)

---



