# Launch checklist: new elevatepractices.com

For the day the rebuilt site (now on preview.elevatepractices.com) replaces the WordPress site on elevatepractices.com.

## 1. Redirects from old WordPress addresses

These old addresses already have a redirect page in this repo, so nothing breaks on launch day.
GitHub Pages can't send a true 301, so each one is a "noindex" page with a canonical tag and an instant forward.
Search engines treat that almost like a 301. For a true 301, add the same list as redirect rules wherever the domain's DNS lives (Cloudflare's free plan can do this).

| Old address | Goes to | Why |
| --- | --- | --- |
| /2780-2/ | /#services | Old ATOM System page. The ATOM section on the home page replaces it. Change to /atom-system/ if that page is built. |
| /home/ | / | Duplicate home page |
| /welcome-to-the-elevate-blog/ | /blog/ | 2015 placeholder post, removed from the blog list and sitemaps |
| /hello-world/ | /blog/ | WordPress sample post |
| /sample-page/ | / | WordPress sample page |
| /test/ | / | Test page |
| /blog-post-title/ through /blog-post-title-9/ | /blog/ | Template placeholder posts |
| /about/ | /elevate-practices-management-team/ | Old About page |
| /our-team/ | /elevate-practices-management-team/ | Old team page |
| /faqs/ | /#faq | Old FAQ page |
| /book-now/ | /book/ | Old booking page |

Before launch, crawl the live WordPress site once more for any address that isn't on this list or in sitemap.xml, and add a redirect page for it.

## 2. One call to action

Every booking button says "Book my free practice assessment" and goes to /book/.
The header button and the phone dock say "Free assessment" because space is tight there; the footer link says "Free practice assessment".
The booking calendar inside /book/ is a Go High Level widget. Its own title is set in Go High Level, so rename it there to "Practice Assessment" to match.

## 3. Switch-over

- [ ] Change CNAME from preview.elevatepractices.com to elevatepractices.com
- [ ] Replace robots.txt ("Disallow: /") with one that allows crawling and lists sitemap.xml
- [ ] Point the domain's DNS at GitHub Pages and turn on HTTPS
- [ ] Submit sitemap.xml in Google Search Console
- [ ] Test the redirects above on the live domain
