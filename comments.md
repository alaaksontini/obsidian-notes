### Fields

|Property Name|Description|Type|
|---|---|---|
|`id`|The comment ID|`string`|
|`attachment`|Link, video, sticker, or photo attached to the comment|[`StoryAttachment`](https://developers.facebook.com/docs/graph-api/reference/story-attachment/)|
|`can_comment`|Whether the viewer can reply to this comment|`bool`|
|`can_remove`|Whether the viewer can remove this comment|`bool`|
|`can_hide`|Whether the viewer can hide this comment. Only visible to a page admin|`boolean`|
|`can_like`|Whether the viewer can like this comment|`boolean`|
|`can_reply_privately`|Whether the viewer can send a private reply to this comment (Page viewers only)|`boolean`|
|`comment_count`|Number of replies to this comment|`int32`|
|`created_time`|The time this comment was made|`datetime`|
|`from`|The person that made this comment|[`User`](https://developers.facebook.com/docs/graph-api/reference/user/)|
|`like_count`|Number of times this comment was liked|`int32`|
|`message`|The comment text|`string`|
|`message_tags`|An array of Profiles tagged in `message`.|`object[]`|
|`object`|The comment on a post that contains a photo or video, including those in dynamic posts. Otherwise, this is empty.|`Object`|
|`parent`|For comment replies, this the comment that this is a reply to.|[`Comment`](https://developers.facebook.com/docs/graph-api/reference/comment)|
|`private_reply_conversation`|For comments with private replies, gets conversation between the Page and author of the comment (Page viewers only)|[`Conversation`](https://developers.facebook.com/docs/graph-api/reference/conversation)|
|`user_likes`|Whether the viewer has liked this comment.|`bool`|

[](https://developers.facebook.com/docs/graph-api/reference/v17.0/comment#)