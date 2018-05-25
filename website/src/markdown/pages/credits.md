# Credits and Trade-offs

Hey, it's Ryan Florence here.

## Why did you make this?

I created Reach Router for two reasons: I needed a router to play around with React Suspense and slapped one together, then I really liked it so I kept going. (2) I want to help push the React community to be more accessible by default.

## Credits

In May of 2014 I created the first version of React Router and was involved with the project all the way to the end of 2017 at version 4. Because of that, Reach Router is clearly influenced by React Router and all of the ideas of the contributors who built it.

To me, Reach Router is everything I missed about v3 and everything I love about v4, plus a couple things I've always wanted to add (focus management and relative links).

## Trade-offs (mostly compared to React Router)

* Size. I'm aiming to come in under 3kb for a modern React app (where API polyfills aren't needed). That makes some extra features harder to include.

* No complex route patterns. There are no optional params, or anything like them, it's just static paths, params, and trailing wildcard.

* No history blocking. I found that the only use-case I had was preventing the user from navigating away from a half-filled out form. Not only is it pretty easy to just save the form state to session storage and bring it back when they return, but history blocking doesn't happen when you navigate away from the app (say to another domain). This kept me from actually using history blocking and always opting to save the form state to session storage.

* No React Native support. Not yet anyway. An important goal is "accessible by default". Assuming a DOM makes this goal easier to attain and maintain. Also, there's a sea of navigation projects for React Native that I'm not interested in swimming in! Maybe in the future, though.
