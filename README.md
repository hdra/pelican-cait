# Cait

Cait is a theme for static site generator, [Pelican][pelican]

Cait is a simple responsive (kind of) theme consisting of mostly black, gray, and white.

## Features:
* Disqus comment. `DISQUS_SITENAME` must be defined in configuration file.
* Google Analytics. `GOOGLE_ANALYTICS` must be defined in configuration.
* Responsive theme.
* Landing and Contact Page.
* Pagination.

## Landing and Contact Page
** Only works on the latest version of Pelican. ( > 3.1.1 )
Cait includes templates for a landing page and a contact page. In order to use it,
the template name needs to be included in itself. The page has to go to your
static pages directory (which is defined in your pelican config file with the `PAGE_DIR`). 
It also need to include a metadata property for `heading and subheading`. 
An example of the landing page:

    Title: Landing
    Heading: Hello! My Name is John Doe
    Subheading: Some subheading sentence to put int.
    Template: landing

    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem, quia, modi suscipit deleniti veniam voluptatum corporis neque sit error earum recusandae velit alias unde laudantium explicabo veritatis laboriosam cum totam ipsum voluptatem dicta nemo necessitatibus! Repellat, laudantium, at deserunt velit similique natus quia quisquam ex tempore praesentium inventore quod eos.

For the contact page, change the 4th line to `Template: contact`.

In order to use the landing and contact template, several additional setting values must be specified
in the configuration file. 

### USE_CUSTOM_MENU
The landing page and contact templates includes a link to the other part of the site. These are specified
in the `CUSTOM_MENUITEMS` tuple. The links are included in the `(Title, url)` format. The url are specified
relative to the `SITEURL`.

    CUSTOM_MENUITEMS = (('Blog', `blog`),
                 ('Contact', 'contact'),
                 ('Projects', 'pages/projects'))

The blog templates aren't required to display the `CUSTOM_MENUITEMS`, in which case will display the 
links to the static pages of the site. To use `CUSTOM_MENUITEMS`, specify `USE_CUSTOM_MENU = True`
in the configuration file. Please not that by using the `CUSTOM_MENUITEMS`, the links
to the pages will not be displayed.

### SOCIAL
The landing page can includes links to several social networks. The links are shown in icons, using 
icons font provided with [FontAwesome][fa]. These are specified with the `SOCIAL` tuple in the 
configuration file, also in the `(title, url)` format. The title should be in lowercase, and it needs
to corresponds with the `icon-*` classes of FontAwesome. The title is only used to display the icon
and will not be displayed, so, any [icons][ic] from FontAwesome can be used as the display icon. Example:

    SOCIAL = (('twitter', 'https://twitter.com/example1'),
              ('facebook', 'https://www.facebook.com/example1'),
              ('google-plus', 'https://plus.google.com/example1'),
              ('google-plus-sign', 'https://plus.google.com/example2'),
              ('github-alt', 'https://github.com/example'),)

### CONTACT_EMAIL and CONTACTS
The contact page shows a list of contact methods. One of them is the email address. To display
email address, the `CONTACT_EMAIL` needs to be set in the configuration file. Additional 
contact information can be displayed in the same way as the social links, this time with the
`CONTACT_EMAIL` tuple.

    CONTACT_EMAIL = "me@example.com"
    CONTACTS = (('facebook', 'https://www.facebook.com/fbAcc'),
                ('twitter', 'https://twitter.com/twttrAcc'),)

#Screenshots
![Post index screenshot][sc1]

![Landing page screenshot][sc2]

![Post index narrow screenshot][sc3]

#LICENSE
MIT

[pelican]: http://getpelican.com
[fa]:http://fortawesome.github.io
[ic]: http://fortawesome.github.io/Font-Awesome/#icons-social
[sc1]: sc1.png
[sc2]: sc4.png
[sc3]: sc3.png
