# tx-discourse-theme

This is the Discourse theme for Transifex community (community.transifex.com).

Documentation for this repo was provided from [How to develop custom
themes][source].

This repository follows the [GitHub Flow guidelines][github-flow].

## Usage

After installation updates are applied sequentially based on commit hierarchy.
In normal development flow this won't be a problem. However, If you attempt to
reset or checkout an older commit it won't work because Discourse will presume
that the commit is already there and not provide you the opportunity to update.
To do so you must move forward in the history (perhaps in the worse case using
an `--allow-empty` commit).

### Production

For the initial install login to Discourse as an admin and navigate to the Admin
menu then the Customize section. There is an **Import** button. When you click
on it a modal popup will ask for **From the web** when selected enter the
following URL:

    https://github.com/XXXXX

From here you can set the **Transifex community** theme as the default for
the site.

As there are changes to this repository those changes can be reflected by
clicking that theme in the **Admin | Customize | Themes** section and then in
the **Custom CSS/HTML** section there is a button labeled **Check for Updates**.

Discourse does not subscribe to any branch which means it defaults to the main
one provided by GitHub (in this case `master`).

## File Structure

```text
.
├── about.json
├── common/
│   ├── common.scss
│   ├── header.html
│   ├── after_header.html
│   ├── footer.html
│   ├── head_tag.html
│   ├── body_tag.html
│   └── embedded.scss
├── desktop/
│   ├── desktop.scss
│   ├── header.html
│   ├── after_header.html
│   ├── footer.html
│   ├── head_tag.html
│   └── body_tag.html
└── mobile/
    ├── mobile.scss
    ├── header.html
    ├── after_header.html
    ├── footer.html
    ├── head_tag.html
    └── body_tag.html
```

### `about.json`

A JSON document used for meta data such as theme name and color schemes.

More detail is available on [How to develop custom themes][source].

### `common/`

Customizations that are common across both desktop and mobile. The files in
this directory follows this naming convention:

| Filename            | Description |
|---------------------|-------------|
| `common.scss`       | Main SCSS to use. Override default selectors here. |
| `header.html`       | HTML content to include in the site header. |
| `after_header.html` | HTML content to include after the site header. |
| `footer.html`       | HTML content to include in the site footer. |
| `head_tag.html`     | HTML content to include before the `</head>` tag. |
| `body_tag.html`     | HTML content to include before the `</body>` tag. |
| `embedded.scss`     | SCSS to include when a shared post is embedded via an IFRAME on other sites. |

### `desktop/`

Customizations that are specific to the desktop browser/screen size. The files
in this directory follows this naming convention:

| Filename            | Description |
|---------------------|-------------|
| `desktop.scss`      | Desktop only SCSS to use. Override default selectors here. |
| `header.html`       | HTML content to include in the site header. |
| `after_header.html` | HTML content to include after the site header. |
| `footer.html`       | HTML content to include in the site footer. |
| `head_tag.html`     | HTML content to include before the `</head>` tag. |
| `body_tag.html`     | HTML content to include before the `</body>` tag. |

### `mobile/`

Customizations that are specific to mobile browsers/screen size. The files in
this directory follows this naming convention:

| Filename            | Description |
|---------------------|-------------|
| `mobile.scss`       | Mobile only SCSS to use. Override default selectors here. |
| `header.html`       | HTML content to include in the site header. |
| `after_header.html` | HTML content to include after the site header. |
| `footer.html`       | HTML content to include in the site footer. |
| `head_tag.html`     | HTML content to include before the `</head>` tag. |
| `body_tag.html`     | HTML content to include before the `</body>` tag. |

[source]: https://meta.discourse.org/t/how-to-develop-custom-themes/60848
[github-flow]: https://guides.github.com/introduction/flow/
