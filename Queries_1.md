Authentication
Need to detect user app language.

1. What all social media we should add ?

- Gmail, Apple -> API (No SDK) - Prompt password

2. Is there any role wise management ?

- Creator (any post) (may have extra privilege) / Consumer (no post)

3. Will it be a separate service or with api gateway ?

- API gateway with Messaging Service (Socket events)

Posts

1. Like, Comment and Share will be shown to all other users?

- Any one can see anyone's likes, comment.

2. Will there be followers and followings?

- Any one can see anyone's likes, comment.

3. Is there transcoding and resizing? If yes what?

- Videos - Yes (ffmpeg) (resolutions - will be shared by francis) -> THIS SHOULD BE A SEPARATE SERVICE, NOT WITH MAIN POST SERVICE. [Min-?? Max-??] [VOD, HLS]
- Image - Yes (Sharp etc) (resolutions - will be shared by francis)

4. Will the media type will be mix and match ?

- Image, Text, Video, Text-Video, Image-Text, IMAGE-VIDEO?

5. Post and live video both are diff? - Not needed
6. NSFW

- Yes [Blocked if(%age is > 80) else (70-80) blocked and sent to Manual]
- No [Allowed]
- Doubtful [Manual]

6. What all moderation will have? - Answered in point 5
7. Languages?

- App Language, Content language [Text translations, Audio translations - try to ber as realtime as possible]

Messaging

1. Why Banuba is needed for messaging?

- Realtime video recording and send as a message to group or 1-1 chat.
- Chat can have diff [type] - general, from admin, alerts(miss-calls,etc), notification, payment
- can have [content-type] - text, video, image, audio, payment

Payment

1. Blinqpay Auth communication? [Diff] [Re-auth before processing payment]

Need not to review now

1. What kind of product?
2. Who will add a product?
   etc

[Expose multiple endpoints]
Auth - > Auth and token generation
Post - Token verification
Message - > Token verification
Payment- > Token verification
Service5-> Token verification
Service7-> Token verification
.
.

[Expose only 1 endpoint]
Auth + API GATEWAY- > Auth and token generation and Token verification
Post - Req redirected here
Message - Req redirected here - X
Payment- Req redirected here
Service5- Req redirected here
Service7- Req redirected here
.
.

[Expose 1 endpoint and 1 socket endpoint] [This is Vikash's Recommendation]
Auth + API GATEWAY- > Auth and token generation and Token verification
Post - Req redirected here
Message - Token verification
Payment- Req redirected here
Service5- Req redirected here
Service7- Req redirected here
.
.
