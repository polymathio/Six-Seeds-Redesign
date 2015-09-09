#SixSeeds @ Patheos: *Preliminary Functional Specifications and Feature List*

## The Primary Goal

We are aware of Pathos's upcoming "go-to-market" plan and intend to conduct this redesign in a way which demonstrate's Patheos' potential as a home for sub-branded content.

We are conducting this re-design with a data-driven methodology. We want to increase visitor metrics and thereby increase revenue.

The balance of visitor metrics is a complicated thing, but most metrics correspond closely to bounce-rate. If therefore, we can decrease bounce rate without decreasing revenue-dollars/page-view, we will result in a net growth in revenue.

## Recommended Technical Set-Up
We have talked to Ben at Avalon and we are both fairly confident that the best way to handle this is to create a second Wordpress-Multisite install on a new server. Provided we have access to your current analytics we should be able to provide an estimate for any new server costs this would cause.

We will create a WP-Multisite with sub-sites for all the channel blogs, a channel-theme and sub-themes for the blogs themselves. Each sub-theme will be able to be customized (within reason) to adapt to the blogger's personal brand (hero styles, etc.)

#### Reasons for Choosing a Separate WP-Multisite Installation

- Enable post-indexing of the entire channel. This will allow us to perform complex queries channel-wide, meaning we can have more granular control over where we are pulling which content. (I.E. - Authors would not have to be removed from the SixSeeds Channel to avoid having ALL of their posts listed under "family" if they cover more than just one topic)
- Enable rich channel-wide search.
- Enable Categorization of posts to create "sub-channels" if necessary.

#### New Channel-Wide Features Enabled by Separate Install

- Unlimited Scrolling on blogs
    - At the bottom of each post we will lazy-load a related post and the user can keep scrolling. This is a strategy used by some of the best content sites on the web to increase articles per visit and thus boost ad views and time on site.

- Post Indexing
    - This will allow for complex queries, for example, querying all posts across all sub-blogs in a certain category. This should allow us to avoid the current difficulties with channel population.

- Domain Mapping and URL rewrites 
    - We will make sure the average user cannot tell that they are on a different Wordpress install (aside from visual differences in the theme) by doing URL rewrites from the Patheos server to the new server.

- Categorization within the channel
    - This will allow us to potentially create sub-channels as SixSeeds grows, should we need to further categorize content.

- REST API
    - This will allow for third party syndication of the content, should it be needed, and will also speed the development of blog theme features.

#### Potential Downsides

- Admins and Authors will need to have two accounts. Sessions will not persist between the main Pathos Wordpress install and the Six-Seeds install

### Page Templates To be Re-Designed

- Context Specific Sub-Templates
   - Header Navigation
      - *Navigation on the main channel pages will primarily include channel level pages.*
	      - Blog List
	      - About SixSeeds
      - *Navigation on the sub-blog pages will primarily include blog level pages. Examples:*
         - About Page
         - Contextual categories
   - Footer
      - Recent posts (channel or blog wide based on context)
   - Related Posts
   

- Channel Level Templates
    - Channel Index
    - Blog List
    - Category Index
    - Channel Search Page

- Blog Level Templates
    - Blog Index
    - Single Post
    - Category Index
    - Blog Search Page
    - Author About Page


### Existing Elements of Pages
Below is a list of the existing elements of each of the pages we wish to redesign. We will make recommendations regarding some of these.

#### Single Blog Post Page

We belive the most important page redesign is the single blog-post template and we would like to start the design thinking on this template. Below is a list of every element which is present on the single blog-post template as it currently exists:

##### [1] Top Bar Navigation (Patheos Properties)
Contains links to Patheos Properties and related enterprises:

- Patheos Shop
- Patheos Press
- Patheos Labs

##### [2] Patheos Branded Banner
This contains:

- Patheos Logo
- A banner Ad
- Internal Nav
	- Family Channel
	- Blogs
	- More Channels
	- Public Square
	- NewsWatch
	- Book Club
	- Religion Library
	- Store


##### [3] Specific Blog Branded Banner
This contains:

- Breadcrumb navigation from Patheos Home to Blog
- Patheos-wide search box
- A small brand banner specific to the blog:
	- [Example](http://wp.production.patheos.com/blogs/seanlowe/files/2014/07/cropped-Sean-Blog22.jpg)
- Channel level Newsletter Subscription and social.
- Blog Level Navigation




##### [3] Sidebar

This is the main content section, the reason users are on the page. Currently it contains:

- Previous / Next Post links
- Post Title
- Post Meta-Data
	- Post Date
	- Author
	- Number of Comments with Anchor Link to comment section
- Main Article Body
- Promo for Family Channel and Artist Social
- More Post Metadata
    - Categories
    - Tags
    - Number of Comments
- Social Sharing Widget
- Related Posts
- Previous / Next Post links again
- External related posts widget (advertisement)
- Disqus comments


##### [4] Main Article Container

This currently contains all manner of widgets, ads, cross promotion, etc.

- Square Banner Ad
- Blog Level Newsletter subscriptions
- Blog Level Social Links
- Popular at Channel
- Square Banner Ad
- Patheos Level Internal Ad
- Blog Level Internal Ad
- Blog Category Dropdown
- Blog Archive Dropdown
- Trending at Channel
- Square Banner Ad
- Recent Comments
- Square Banner Ad

### Suggested Refactoring of Elements of Pages

#### Single Blog Post Page

##### Create single navigation bar while on blog level pages
- Include strong blog-level branding as the primary branding on the left.
- Simplify navigation to include blog-level navigation as primary destinations, with inter-level navigation contained within dropdowns

##### Group Patheos and SixSeeds branded items in branded dropdowns while on blog-level pages
- Patheos Dropdown: Mega-Box style dropdown with multiple styles of elements
    - Combine sections [1] and [2] within a single dropdown at the top of the page (containing all Patheos branded items)
    - Move Patheos level Social and Newsletter subscription material within the Patheos Dropdown
- SixSeeds Dropdown: Mega-Box style dropdown with multiple styles of elements
    - Move SixSeeds level Social and Newsletter subscription material within the SixSeeds Dropdown

##### Keep Author Social Channels in sidebar
- We want to avoid overwhelming users with too many social icons. Confused users don't click on things and multiple social icons, just like the classic "multiple download button scam" make users mistrust their decisions and not click at all.
- We should keep the visible social icons constrained to the current page-level. So on single blog post pages, we will show the Author's social info in the sidebar and contain Platform and Channel level social/newsletter sign-up to the brand dropdowns.

##### Condense Popular/Trending Posts
- Showing both "Popular at Patheos Family" and "Trending at Patheos Family" is redundant. To avoid overwhelming users, we will Show only one of these (Currently leaning toward trending)

##### Move social sharing and comments (All the "commmunity elements") to a fixed scrolling bottom bar that tracks with the user.
- This keep these items front and center for the user.
- We are aiming to convey that this bar is full of tools useful to the engaged user.

