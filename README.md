# Galaxy Social

To create a post, follow these steps:

1. Create a pull request to the "toots" folder.
2. Inside the pull request, create a new file with the extension ".toot".
3. Use the following template for the post content:

```
---
social_media: bluesky, mastodon, matrix, slack
images: "1.jpg", "2.png"
alt_texts: "1", "2"
mentions: bluesky[a], mastodon[b]
hashtags: bluesky[a, b], mastodon[a, b]
---
Text
```

# Add a new social media

To create a new plugin, you have to add a Python file with the function `create_post(content, mentions, hashtags, images, alt_texts)` inside a class and add it to `plugins.yml` like this template:

```
  - name: name_of_the_social_media
    class: file_name.class_name
    enabled: true
    config:
      token: TOKEN_SAVED_IN_PUBLISH_CONTENT
```

The `name` is then used in the `social_media` tag in the toot file to determine the social media.

Just with `enabled: true`, the social media will be implemented.

In the config, you have to add all the variables needed for the class inside your plugin to initialize.

You have to then add tokens and variables needed to start the client to [GitHub secrets](https://docs.github.com/en/actions/security-guides/using-secrets-in-github-actions#creating-secrets-for-a-repository) and in `publish_content.yml` add an env variable like this template:


```
TOKEN_SAVED_IN_PUBLISH_CONTENT: ${{ secrets.TOKEN_SAVED_IN_GITHUB_SECRETS }}
```

# Social media implemented
- Bluesky
- Mastodon
- Matrix: hashtags and alt_text for image are not working!
- Slack: mentions and hashtags are not working!
