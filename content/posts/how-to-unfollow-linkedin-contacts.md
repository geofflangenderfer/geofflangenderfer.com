---
title: "How to Unfollow Linkedin Contacts"
date: 2020-05-28T11:08:38-05:00
draft: true
---

- My linkedin feed is a mess. The feed is made up of content from those you follow. So, we can clean it up by resetting our follower count to zero.
- Navigate to your Linkedin following page https://www.linkedin.com/feed/following/
Javascript code:
- while followers > 0
  - scroll to end of page to load all contacts
  - copy this javascript into the console and press enter
  - right-click + inspect any 'Following' profile card
  - replace `startEmberId` with number found (`id="ember61"` -> 61)

```javascript
const sleep = (milliseconds) => {
  return new Promise(resolve => setTimeout(resolve, milliseconds))
}
for (let i=0;i<1000;i++) {
  sleep(1000).then(() => {
    let startEmberId = 60
    document.querySelector(`#ember${startEmberId+i}`).click()
    console.log(`clicked #ember${startEmberId+i}`)
  })
}
```
