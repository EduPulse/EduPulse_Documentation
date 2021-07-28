# Design Spec
## User
    role: user role
        -> admin
        -> moderator
        -> academic
            * academic_student
            * academic_staff
        -> general
    academic_state: whether request for academic user accepted or not
        -> state: 
            * accepted
            * rejected
    notifications
        -> status: whether notification viewed or not
    following_tags:
        -> type: fallowing a user tag or a content tag
            * user tag
            * content tag
    subscribed_notifications: content user subscribed to get notified
        -> content_type
            * post
            * comment
        -> content_id: post or comment id
    posts: list of post ids that are created by the given user.
    collections: add to library option is implement here. they may have several collections and under one collection can save may posts.

## Post
    status: either published or not
        * published
        * draft
    versions
        -> version: this version number
        -> contributer: user who contributed (single), or original author in v0
    type
        * article
        * video
        * document
        * audio
        * picture
        * pin: post that pinning an another post
    pin: pin information if this is a pin
    visibility: post visibility
        * visible
        * hidden
        * removed: removed by an moderator. only shown to the creator and moderators
    comments: comment threads
        -> content: textual content

## Report
    type: against type
        * user: sent to admin
        * insititute: sent to admin
        * post: sent to moderator
        * comment: sent to moderator
    closed: true or false
    closed_info: 
        -> user_id: user who closed the report. either moderator or admin
        -> action: final action taken
            * user_banned
            * hidden: comment or post hidden
            * rejected: report rejected

## Academic User Request
    status: user promotion request status
        * accepted
        * rejected
        * pending

## Advertiser
    Here, we are storing advertisement under companies. if company did not already publish advertisement on system, there details will be stored on the system, else advertisement details will be saved under company. 
    advertisements
        -> type: this indicate what sort of content is available ob the advertisement.
            * video
            * text
            * picture => slid shows
        -> images: list of images for the slidshow
        -> redirect_link: link that need to navigate ones click on the advertisement.
        -> related_tags: list of tags, that advertisement more related to.
        -> payment_details
            -> payment_method: NEED TO DISCUSS
