# galaxy-social

To create a post, follow these steps:

1. Create a pull request in the "toots" folder.
2. Inside the pull request, create a new file with the extension ".toot".
3. Use the following template for the post content:

```
---
social_media: bluesky, mastodon
images: "1.jpg", "2.png"
alt_texts: "1", "2"
mentions: bluesky[a], mastodon[b]
hashtags: bluesky[a, b], mastodon[a, b]
---
Text
```