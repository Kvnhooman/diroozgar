# The Signal MVP

## Firestore Data Model (Schema)

```
users/{userId}
  - email: string
  - createdAt: timestamp
  reflections/{postId}
    - postId: string
    - body: string
    - createdAt: timestamp
    - updatedAt: timestamp

posts/{postId}
  - title: string
  - body: string (markdown)
  - imageUrl: string | null
  - createdAt: timestamp
  - createdBy: string (admin userId)

invites/{code}
  - code: string
  - isActive: boolean
  - usedBy: string | null
  - usedAt: timestamp | null
  - createdAt: timestamp
```

## Project Directory Structure

```
mobile-app/
  app/
    _layout.js
    (app)/
      feed.js
      post/
        [id].js
    (auth)/
      sign-up.js
  components/
    PostCard.js
  lib/
    auth-context.js
    firebase.js
firestore.rules
```

## Firestore Security Rules

See `firestore.rules` for the full rule set, including locked-down reflections and admin-only post writes.
