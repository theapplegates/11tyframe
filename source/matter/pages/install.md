---js
{
  date:      `2019-11-01`,
  layout:    `frame.njk`,
  permalink: `install.html`,
  tags:      [ `post` ],

  eleventyExcludeFromCollections: false,
  no_comments: true,

  title_s:    `Install 11ty Frame`,
  subtitle_s: `How to install your 11ty Frame blog`,
  abstract_s: `Follow these instructions`,
  author_s:   `Me`,
}
---
[comment]: # (======== Post ========)
# Installing 11ty Frame blog

You are just a few lines away from your blog.{ data--="page_intro" }

{% _anchor %}
## Let's have a post!
{% end_anchor %}


Once installed and deployed
{% _short_note %}
Using Netlify is the easiest way, but any alternative is as simple.
{% end_short_note %}
, you have to modify the entries found in the `install.js` file located at the root of your source directory
{% _short_note %}
the `AUTHOR_s` and `EMAIL_s` properties are slightly different in the `install.js` file, but it's because the {{A_o.NAME_s}} demo site requires real initial values.
{% end_short_note %}
.


{% _code_block %}
    title_s: 'source/install.js',
    lang_s: 'javascript',
[//]:#(_code_block)
{% raw %}
AUTHOR_s     : 'yourname',                        //: Your github name
EMAIL_s      : 'yourname@yourmail.com',           //: Your github e-mail
ID_s         : '11tyframe',                       //: Your github repository
NAME_s       : '11ty Frame',                      //: Your site name
URL_s        : `https://11tyframe.netlify.com/`,  //: Your CDN site address
LOCAL_s      : 'http://127.0.0.1:5500/',          //: Your local address and port for development
COLLECTION_s : 'post',                            //: The **Eleventy tag** for your posts collection

description_o:                                    //: descriptions for SEO
{
  DESCRIPT_s: '11ty Frame blog',
  GLOBAL_s:   'Eleventy,static site generator',
},
{% endraw %}
{% end_code_block %}


Once you have completed this step, you just have to rebuilt your site with this command:
{% _short_note %}
from your {{A_o.NAME_s}} `source` directory.
{% end_short_note %}

{% _code_block %}
    title_s: 'shell command',
    lang_s: 'shell',
[//]:#(_code_block)
{% raw %}
npx eleventy --config=make/11ty/make.js
{% endraw %}
{% end_code_block %}


Then, begin to write your first posts
{% _short_note %}
probably replacing the `index.md` and `install.md` files in the `matter/pages` directory...
{% end_short_note %}
! For thurther help, please refer to the **[11tyTips]{{U_o.OUTLINK_s}}** site which is the model of your fresh new site.


{% _anchor %}
## Commenting or not commenting?
{% end_anchor %}


If you do you want to have comments on some or all of your blog pages, you have to configure {{A_o.NAME_s}} commenting system: [utteranc.es]{{U_o.OUTLINK_s}}. All you have to do is to follow the [instructions]{{U_o.OUTLINK_s}}.


If you don't want to have comments on any page, just add a property `no_comments` in its section: here is what this `install` page source does, just _commenting out_ (sic) the `no_comments` property.


{% _code_block %}
    title_s: 'source/matter/pages.install.md',
    lang_s: 'javascript',
[//]:#(_code_block)
{% raw %}
---js
{
  date:      `2019-11-01`,
  layout:    `frame.njk`,
  permalink: `install.html`,
  tags:      [ `post` ],

  eleventyExcludeFromCollections: false,
  no_comments: true,    //: there will be no comments for this page!

  title_s:    `Install 11ty Frame`,
  subtitle_s: `How to install your 11ty Frame blog`,
  abstract_s: `Follow these instructions`,
  author_s:   `Me`,
}
---
{% endraw %}
{% end_code_block %}


[comment]: # (======== Links ========)

[11tyTips]: https://11tytips.netlify.com
[utteranc.es]: https://github.com/utterance/utterances
[instructions]: https://utteranc.es