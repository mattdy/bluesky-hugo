# Bluesky posts on Hugo Blogs
I've taken the code put together by [Oliver Menzel](https://bsky.app/profile/ollim365.menzel.it) [as described here](https://www.menzel.it/post/2024/11/set-comments-experience-bluesky-posts/) and modified it for use on my [Hugo](https://gohugo.io/) blog which uses the [Congo theme](https://github.com/jpanther/congo).

Full credit and huge thanks to the original author for pulling this together - I've made a few modifications such as:
- Providing links to the reply posts
- Providing links to the authors profile on [bsky.app](https://bsky.app/)
- Showing Reply / Repost / Like counters (inspiration taken from [here](https://github.com/nsideras/bluesky-js-comments))
- Updating CSS to play nicely with my theme

Further details available [on my blog](https://mattdyson.org/blog/2024/11/bluesky-posts-as-hugo-blog-comments/) where you can see this code in action.

## How to install
1. Copy the `comments.html` file to `layouts/partials/comments.html`
2. Add your own DID or handle on lines 8 and 21 of `comments.html` (... or find a better way of doing this through site parameters and submit a PR?!)
3. Copy the contents of `custom.css` into `assets/css/custom.css`, creating the file if it doesn't exist
4. Ensure that `config/_default/params.toml` contains `showComments=true` under `[article]`

## How to use
You can then add `blueskythread: <YOUR POST ID>` to your [front matter](https://gohugo.io/content-management/front-matter/) on any post.
The ID required can be gathered from looking at the end of the post URL such as `https://bsky.app/profile/mattdyson.org/post/3lbmodxdc222t` - in this case the ID would be `3lbmodxdc222t`.
After the page is loaded, a request should then be made to the Bluesky public API, and replies to your post should appear as comments!
