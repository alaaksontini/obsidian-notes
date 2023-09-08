| Field                                                                                                    | Description                                                                                                                   |
| -------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `id`token with structure: ID                                                                             | ID of the query                                                                                                               |
| `description`string                                                                                      | Long description of the metric[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)               |
| `description_from_api_doc`string                                                                         | The description of the metric, retrieved from the API doc(https\://developers.facebook.com/docs/graph-api/reference/insights) |
| `name`string                                                                                             | The Insights metric requested[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)                |
| `period`enum                                                                                             | The period of time used for the aggregation[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)  |
| `title`string                                                                                            | Short description of the metric[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)              |
| `values`list\<InsightsValue> | The different values for this metric[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)         |


## Insight Values

| Field                                       | Description |
| ------------------------------------------- | ----------------------------------------------------------- |
| `campaign_id`string                         | campaign\_id[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)                                 |
| `end_time`datetime                          | The time from which the data are aggregated[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)  |
| `engagement_source`string                   | engagement\_source[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)                           |
| `message_type`string                        | message\_type[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)                                |
| `messaging_channel`string                   | messaging\_channel[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)                           |
| `recurring_notifications_entry_point`string | recurring\_notifications\_entry\_point[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)       |
| `recurring_notifications_frequency`string   | recurring\_notifications\_frequency[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)          |
| `recurring_notifications_topic`string       | recurring\_notifications\_topic[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)              |
| `start_time`datetime                        | The start time which the data are aggregated[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields) |
| `value`(integer) or (map) or (float)        | The value of the aggregated data[Default](https://developers.facebook.com/docs/graph-api/using-graph-api/#fields)             |


### Limitations

* Page Insights data is only available on Pages with 100 or more likes.

* Most metrics will update once every 24 hours.

* Only the last two years of insights data is available.

* The values for `period` are calculated from the initial collection of the data point.

* "Period" in the tables below only refers to the time frame for which the metric can be accessed in an aggregated form.

* The value "lifetime" means the time period for which the insights data is available. By default, this time period is 2 years or shorter.

* Only 90 days of insights can be viewed at one time when using the `since` and `until` parameters.

* When using `since` and `until`, the `since` date data will be included in the first `value` returned.

* Unique impression insights values are calculated independently.

  * Total page reach may not always be exactly equal to the sum of paid and non-paid unique values.
  * Total page reach may not always be exactly equal to the sum of `viral_unique` and `organic_unique`.

* When an organic post is boosted, metrics for paid post impressions will include both organic and paid reach.

* Demographic metrics, such as age, gender, and location, are only returned if there is data for 100 or more people.

* Breakdown metrics for Page post and Page view insights will only return non-zero values.

* Several video related metrics only return accurate values if the person requesting the metric is the Page video post creator.

* If you reshare a video post of another Page and retrieve its insights, the metrics return a value of 0. Metrics that return 0 for resharers are denoted with "Returns 0 for reshared videos" in their description.

* If you neglect to indicate a specific metric or metrics for the endpoint, you will receive an error response with code `3001`, with subcode `1504028` and an error message that states: "No metric was specified to be fetched. Please specify one or more metrics to be fetched and try again."

* Interactions on Reels are not included.


### Metrics

Metric names indicate whether a metric is for a Page or a Page post.

| Suffix    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `_unique` | Indicates that the metric shows the number of unique users who performed a specific action, for example `page_impressions_unique`. **Metrics generated with the `_unique` suffix are approximate and may not be 100% accurate.**                                                                                                                                                                                                                                                                  |
| `_login`  | Indicates whether a person was logged into Facebook, for example, `page_tab_views_login_top`.                                                                                                                                                                                                                                                                                                                                                                                                     |
| `_logout` | Indicates whether a person is logged out of Facebook, for example `page_views_logout`.                                                                                                                                                                                                                                                                                                                                                                                                            |
| `_source` | Indicates that the metric will be broken down into a list of referral sources, for example `page_fans_by_like_source`. External referrals are broken down by domain. Internal referrals are broken down by Facebook-specific features such as **Profile**, **Search**, **Requests**, **Suggestions**, **Stream**, etc. In these cases the `value` returned will be an object containing a series of key-value pairs where the key is the source name and the value is the metric for that source. |
| `*`       | Indicates that a metric is refreshed several times during the day, for example `page_impressions_unique*`.                                                                                                                                                                                                                                                                                                                                                                                        |

### Page CTA Clicks

|Metric Name|Description|Values for `period`|
|---|---|---|
|`page_total_actions`|The number of clicks on your Page's contact info and call-to-action button.|day, week, days_28|
|`page_cta_clicks_logged_in_total`|Total number of clicks on the Page CTA button by people who are logged in to Facebook.|day, week, days_28|
|`page_cta_clicks_logged_in_unique`|Unique number of clicks on the Page CTA button by people who are logged in to Facebook.|day, week, days_28|
|`page_cta_clicks_by_site_logged_in_unique`|Number of people who are logged in to Facebook and clicked on the CTA button, broken down by www, mobile, api or other.|day, week, days_28|
|`page_cta_clicks_by_age_gender_logged_in_unique`|Number of people who are logged in to Facebook and clicked the Page CTA button, broken down by age and gender group.|day, week, days_28|
|`page_cta_clicks_logged_in_by_country_unique`|Number of people who are logged in to Facebook and clicked the Page CTA button, broken down by country.|day, week|
|`page_cta_clicks_logged_in_by_city_unique`|Number of people who are logged in to Facebook and clicked the Page CTA button, broken down by city.|day, week|
|`page_call_phone_clicks_logged_in_unique`|Number of people who logged into Facebook and clicked the Call Now button.|day, week, days_28|
|`page_call_phone_clicks_by_age_gender_logged_in_unique`|Number of people who logged in to Facebook and clicked the Call Now button, broken down by age and gender group.|day, week, days_28|
|`page_call_phone_clicks_logged_in_by_country_unique`|Number of people who logged into Facebook and clicked the Call Now button, broken down by countries.|day, week|
|`page_call_phone_clicks_logged_in_by_city_unique`|Number of people who logged into Facebook and clicked the Call Now button, broken down by city.|day, week|
|`page_call_phone_clicks_by_site_logged_in_unique`|The number of people who clicked your Page's phone number or Call now button while they were logged into Facebook, broken down by the type of device they used.|day, week, days_28|
|`page_get_directions_clicks_logged_in_unique`|Number of people who logged in to Facebook and clicked the Get Directions button.|day, week, days_28|
|`page_get_directions_clicks_by_age_gender_logged_in_unique`|Number of people who logged into Facebook and clicked the Get Directions button, broken down by age and gender group.|day, week, days_28|
|`page_get_directions_clicks_logged_in_by_country_unique`|Number of people who logged in to Facebook and clicked the Get Directions button, broken down by country.|day, week|
|`page_get_directions_clicks_logged_in_by_city_unique`|Number of people who logged in to Facebook and clicked the Get Directions button, broken down by city.|day, week|
|`page_get_directions_clicks_by_site_logged_in_unique`|Number of people who logged in to Facebook and clicked the Get Directions button, broken down by www, mobile, api or other.|day, week, days_28|
|`page_website_clicks_logged_in_unique`|Number of people who logged in to Facebook and clicked the goto website CTA button.|day, week, days_28|
|`page_website_clicks_by_age_gender_logged_in_unique`|Number of people who logged into Facebook and clicked the goto website CTA button, broken down by age and gender group.|day, week, days_28|
|`page_website_clicks_logged_in_by_country_unique`|Number of people who logged in to Facebook and clicked the goto website CTA button, broken down by country.|day, week|
|`page_website_clicks_logged_in_by_city_unique`|Number of people who logged in to Facebook and clicked the goto website CTA button, broken down by city.|day, week|
|`page_website_clicks_by_site_logged_in_unique`|Number of people who logged in to Facebook and clicked the Page CTA button, broken down by www, mobile, api and other.|day, week, days_28|

### Page Engagement

The "like" reaction counts include both "like" and "care" reactions.

|Metric Name|Description|Values for `period`|
|---|---|---|
|`page_engaged_users`|The number of people who engaged with your Page. Engagement includes any click.|day, week, days_28|
|`page_post_engagements*`|The number of times people have engaged with your posts through reactions, comments, shares and more.|day, week, days_28|
|`page_consumptions`|The number of times people clicked on any of your content.|day, week, days_28|
|`page_consumptions_unique`|The number of people who clicked on any of your content.|day, week, days_28|
|`page_consumptions_by_consumption_type`|The number of times people clicked on any of your content, by type. Types include [`link_click`, `other_click`, `photo_view`, and `video_view`](https://www.facebook.com/business/help/787506997938504).|day, week, days_28|
|`page_consumptions_by_consumption_type_unique`|The number of people who clicked on any of your content, by type.|day, week, days_28|
|`page_places_checkin_total`|The number of times people checked into a place.|day, week, days_28|
|`page_places_checkin_total_unique`|The number of people who checked into a place.|day, week, days_28|
|`page_places_checkin_mobile`|The number of times people checked into a place using mobile phones.|day, week, days_28|
|`page_places_checkin_mobile_unique`|The number of people who checked into a place using mobile phones.|day, week, days_28|
|`page_places_checkins_by_age_gender`|gender and age of people who checked in at your Place.|day|
|`page_places_checkins_by_locale`|top locales of people who checked into your Place.|day|
|`page_places_checkins_by_country`|top countries of people who checked into your Place.|day|
|`page_negative_feedback`|The number of times people took a negative action (e.g., un-liked or hid a post).|day, week, days_28|
|`page_negative_feedback_unique`|The number of people who took a negative action (e.g., un-liked or hid a post).|day, week, days_28|
|`page_negative_feedback_by_type`|The number of times people took a negative action broken down by type. (See [possible types](https://developers.facebook.com/docs/graph-api/reference/v2.5/insights#negative-feedback-type))|day, week, days_28|
|`page_negative_feedback_by_type_unique`|The number of people who took a negative action broken down by type. (See [possible types](https://developers.facebook.com/docs/graph-api/reference/v2.5/insights#negative-feedback-type))|day, week, days_28|
|`page_positive_feedback_by_type`|The number of times people took a positive action broken down by type. (See [possible types](https://developers.facebook.com/docs/graph-api/reference/v2.5/insights#positive-feedback-types))|day, week, days_28|
|`page_positive_feedback_by_type_unique`|The number of people who took a positive action broken down by type. (See [possible types](https://developers.facebook.com/docs/graph-api/reference/v2.5/insights#positive-feedback-types))|day, week, days_28|
|`page_fans_online`|The number of your fans who saw any posts on Facebook on a given day, broken down by hour of day in PST/PDT.|day|
|`page_fans_online_per_day`|The number of your fans who saw any posts on Facebook on a given day.|day|
|`page_fan_adds_by_paid_non_paid_unique`|The number of new people who have liked your Page broken down by paid and non-paid.|day|

### Page Impressions

|Metric Name|Description|Values for `period`|
|---|---|---|
|`page_impressions*`|The number of times any content from your Page or about your Page entered a person's screen. This includes posts, stories, ads, as well other content or information on your Page.|day, week, days_28|
|`page_impressions_unique*`|The number of people who had any content from your Page or about your Page enter their screen. This includes posts, stories, check-ins, ads, social information from people who interact with your Page and more.|day, week, days_28|
|`page_impressions_paid*`|The number of times any post or story content from your Page or about your Page entered a person's screen through paid distribution such as an ad.|day, week, days_28|
|`page_impressions_paid_unique*`|The number of people who had any content from your Page or about your Page enter their screen through paid distribution such as an ad.|day, week, days_28|
|`page_impressions_organic_v2*`|The number of times any post or story content from your Page or about your Page entered a person's screen through unpaid distribution.|day, week, days_28|
|`page_impressions_organic_unique_v2*`|The number of people who had any content from your Page or about your Page enter their screen through unpaid distribution. This includes posts, stories, check-ins, social information from people who interact with your Page and more.|day, week, days_28|
|`page_impressions_viral*`|The number of times any content from your Page or about your Page entered a person's screen with social information attached. Social information displays when a person's friend interacted with your Page, post or story. This includes when someone's friend likes or follows your Page, engages with a post, shares a photo of your Page and checks into your Page.|day, week, days_28|
|`page_impressions_viral_unique*`|The number of people who had any content from your Page or about your Page enter their screen through with social information attached. As a form of organic distribution, social information displays when a person's friend interacted with your Page, post or story. This includes when someone's friend likes or follows your Page, engages with a post, shares a photo of your Page and checks into your Page.|day, week, days_28|
|`page_impressions_nonviral*`|The number of times any content from your Page entered a person's screen. This does not include content created about your Page with social information attached. Social information displays when a person's friend interacted with your Page, post or story. This includes when someone's friend likes or follows your Page, engages with a post, shares a photo of your Page and checks into your Page.|day, week, days_28|
|`page_impressions_nonviral_unique*`|The number of people who had any content from your Page enter their screen. This does not include content created about your Page with social information attached. As a form of organic distribution, social information displays when a person's friend interacted with your Page, post or story. This includes when someone's friend likes or follows your Page, engages with a post, shares a photo of your Page and checks into your Page.|day, week, days_28|
|`page_impressions_by_story_type`|Total impressions of posts published by a friend about your Page by type. (See [possible types](https://developers.facebook.com/docs/graph-api/reference/v2.5/insights#page-story-types))|day, week, days_28|
|`page_impressions_by_story_type_unique`|The number of people who saw posts published by a friend about your Page by type. (See [possible types](https://developers.facebook.com/docs/graph-api/reference/v2.5/insights#page-story-types))|day, week, days_28|
|`page_impressions_by_city_unique`|The number of people who have seen any content associated with your Page by city.|day, week, days_28|
|`page_impressions_by_country_unique`|The number of people who have seen any content associated with your Page by country.|day, week, days_28|
|`page_impressions_by_locale_unique`|The number of people who have seen any content associated with your Page by user selected language.|day, week, days_28|
|`page_impressions_by_age_gender_unique`|The number of people who saw any content by your Page or about your Page, grouped by age and gender. This number is an estimate.|day, week, days_28|
|`page_impressions_frequency_distribution`|The number of people your Page reached broken down by how many times people saw any content about your Page.|day, week, days_28|
|`page_impressions_viral_frequency_distribution`|The number of people your Page reached from a story published by a friend, broken down by how many times people saw stories about your Page.|day, week, days_28|

### Page Posts

|Metric Name|Description|Values for `period`|
|---|---|---|
|`page_posts_impressions*`|The number of times your Page's posts entered a person's screen. Posts include statuses, photos, links, videos and more.|day, week, days_28|
|`page_posts_impressions_unique*`|The number of people who had any of your Page's posts enter their screen. Posts include statuses, photos, links, videos and more.|day, week, days_28|
|`page_posts_impressions_paid*`|The number of times your Page's posts entered a person's screen through paid distribution such as an ad.|day, week, days_28|
|`page_posts_impressions_paid_unique*`|The number of people who had any of your Page's posts enter their screen through paid distribution such as an ad.|day, week, days_28|
|`page_posts_impressions_organic*`|The number of times your Page's posts entered a person's screen through unpaid distribution.|day, week, days_28|
|`page_posts_impressions_organic_unique*`|The number of people who had any of your Page's posts enter their screen through unpaid distribution.|day, week, days_28|
|`page_posts_served_impressions_organic_unique`|The number of people who were served your Page's posts in their Feed whether it entered their screen or not. Posts include statuses, photos, links, videos and more.|day, week, days_28|
|`page_posts_impressions_viral*`|The number of times your Page's posts entered a person's screen with social information attached. Social information displays when a person's friend interacted with you Page or post. This includes when someone's friend likes or follows your Page, engages with a post, shares a photo of your Page and checks into your Page.|day, week, days_28|
|`page_posts_impressions_viral_unique*`|The number of people who had any of your Page's posts enter their screen with social information attached. As a form of organic distribution, social information displays when a person's friend interacted with you Page or post. This includes when someone's friend likes or follows your Page, engages with a post, shares a photo of your Page and checks into your Page.|day, week, days_28|
|`page_posts_impressions_nonviral*`|The number of times your Page's posts entered a person's screen. This does not include content created about your Page with social information attached. Social information displays when a person's friend interacted with you Page or post. This includes when someone's friend likes or follows your Page, engages with a post, shares a photo of your Page and checks into your Page.|day, week, days_28|
|`page_posts_impressions_nonviral_unique*`|The number of people who had any posts by your Page enter their screen. This does not include content created about your Page with social information attached. As a form of organic distribution, social information displays when a person's friend interacted with you Page or post. This includes when someone's friend likes or follows your Page, engages with a post, shares a photo of your Page and checks into your Page.|day, week, days_28|
|`page_posts_impressions_frequency_distribution`|The number of people who saw your Page posts, broken down by how many times people saw your posts.|day, week, days_28|

### Page Post Engagement

|Metric Name|Description|Values for `period`|
|---|---|---|
|`post_engaged_users*`|The number of people who clicked anywhere in your posts.|lifetime|
|`post_negative_feedback*`|The number of times people took a negative action in your post (e.g. hid it).|lifetime|
|`post_negative_feedback_unique*`|The number of people who took a negative action in your post (e.g., hid it).|lifetime|
|`post_negative_feedback_by_type*`|The number of times people took a negative action in your post broken down by type.|lifetime|
|`post_negative_feedback_by_type_unique*`|The number of people who took a negative action in your post broken down by type.|lifetime|
|`post_engaged_fan`|People who have liked your Page and engaged with your post.|lifetime|
|`post_clicks*`|The number of times people clicked on anywhere in your posts without generating a story.|lifetime|
|`post_clicks_unique*`|The number of people who clicked anywhere in your post without generating a story.|lifetime|
|`post_clicks_by_type*`|The number of times people clicked on anywhere in your posts without generating a story, by consumption type.|lifetime|
|`post_clicks_by_type_unique*`|The number of people who clicked anywhere in your post without generating a story, by consumption type.|lifetime|

#### Negative Feedback Types

Negative feedback types for `page_negative_feedback_by_type` metrics.

|Name|Description|
|---|---|
|`hide_clicks`|Hide this story|
|`hide_all_clicks`|Hide all posts from this page|
|`report_spam_clicks`|Report an object as a spam|
|`unlike_page_clicks`|Unlike a page|

#### Positive Feedback Types

Positive feedback types for `page_positive_feedback_by_type` metrics.

|Name|Description|
|---|---|
|`answer`|Answer a question|
|`claim`|Claim an offer|
|`comment`|Comment on a story|
|`like`|Like a story|
|`link`|Share a story|
|`other`|Other types, such as checkins|
|`rsvp`|Respond to an event|

### Page Post Impressions

|Metric Name|Description|Values for `period`|
|---|---|---|
|`post_impressions*`|The number of times your Page's post entered a person's screen. Posts include statuses, photos, links, videos and more.|lifetime|
|`post_impressions_unique*`|The number of people who had your Page's post enter their screen. Posts include statuses, photos, links, videos and more.|lifetime|
|`post_impressions_paid*`|The number of times your Page's post entered a person's screen through paid distribution such as an ad.|lifetime|
|`post_impressions_paid_unique*`|The number of people who had your Page's post enter their screen through paid distribution such as an ad.|lifetime|
|`post_impressions_fan*`|The number of impressions for your Page post by people who have liked your Page.|lifetime|
|`post_impressions_fan_unique*`|The number of people who have like your Page who saw your Page post.|lifetime|
|`post_impressions_fan_paid*`|The number of impressions for your Page post by people who like your Page in an Ad or Sponsored Story.|lifetime|
|`post_impressions_fan_paid_unique*`|The number of people who have like your Page and saw your Page post in an Ad or Sponsored Story.|lifetime|
|`post_impressions_organic*`|The number of times your Page's posts entered a person's screen through unpaid distribution.|lifetime|
|`post_impressions_organic_unique*`|The number of people who had your Page's post enter their screen through unpaid distribution.|lifetime|
|`post_impressions_viral*`|The number of times your Page's post entered a person's screen with social information attached. Social information displays when a person's friend interacted with you Page or post. This includes when someone's friend likes or follows your Page, engages with a post, shares a photo of your Page and checks into your Page.|lifetime|
|`post_impressions_viral_unique*`|The number of people who had your Page's post enter their screen with social information attached. As a form of organic distribution, social information displays when a person's friend interacted with you Page or post. This includes when someone's friend likes or follows your Page, engages with a post, shares a photo of your Page and checks into your Page.|lifetime|
|`post_impressions_nonviral*`|The number of times your Page's post entered a person's screen. This does not include content created about your Page with social information attached. Social information displays when a person's friend interacted with you Page or post. This includes when someone's friend likes or follows your Page, engages with a post, shares a photo of your Page and checks into your Page.|lifetime|
|`post_impressions_nonviral_unique*`|The number of people who had your Page's post enter their screen. This does not include content created about your Page with social information attached. As a form of organic distribution, social information displays when a person's friend interacted with you Page or post. This includes when someone's friend likes or follows your Page, engages with a post, shares a photo of your Page and checks into your Page.|lifetime|
|`post_impressions_by_story_type*`|The number of times this post was seen via a story published by a friend of the person viewing the post.|lifetime|
|`post_impressions_by_story_type_unique*`|The number of people who saw your Page post in a story from a friend, by story type.|lifetime|

### Page Post Reactions

The "like" reaction counts include both "like" and "care" reactions.

|Metric Name|Description|Values for `period`|
|---|---|---|
|`post_reactions_like_total`|Total "like" reactions of a post.|lifetime|
|`post_reactions_love_total`|Total "love" reactions of a post.|lifetime|
|`post_reactions_wow_total`|Total "wow" reactions of a post.|lifetime|
|`post_reactions_haha_total`|Total "haha" reactions of a post.|lifetime|
|`post_reactions_sorry_total`|Total "sad" reactions of a post.|lifetime|
|`post_reactions_anger_total`|Total "anger" reactions of a post.|lifetime|
|`post_reactions_by_type_total`|Total post reactions by type.|lifetime|

### Page Reactions

The "like" reaction counts include both "like" and "care" reactions.

|Metric Name|Description|Values for `period`|
|---|---|---|
|`page_actions_post_reactions_like_total`|Daily total post "like" reactions of a page.|day, week, days_28|
|`page_actions_post_reactions_love_total`|Daily total post "love" reactions of a page.|day, week, days_28|
|`page_actions_post_reactions_wow_total`|Daily total post "wow" reactions of a page.|day, week, days_28|
|`page_actions_post_reactions_haha_total`|Daily total post "haha" reactions of a page.|day, week, days_28|
|`page_actions_post_reactions_sorry_total`|Daily total post "sorry" reactions of a page.|day, week, days_28|
|`page_actions_post_reactions_anger_total`|Daily total post "anger" reactions of a page.|day, week, days_28|
|`page_actions_post_reactions_total`|Daily total post reactions of a page by type.|day|

### Page User Demographics

|Metric Name|Description|Values for `period`|
|---|---|---|
|`page_fans`|The total number of people who have liked your Page.|day|
|`page_fans_locale`|Aggregated language data about the people who like your Page based on the default language setting selected when accessing Facebook.|day|
|`page_fans_city`|Aggregated Facebook location data, sorted by city, about the people who like your Page.|day|
|`page_fans_country`|The number of people, aggregated per country, that like your Page. Only the 45 countries with the most people that like your Page are included.|day|
|`page_fans_gender_age`|The number of likes of your Facebook Page. This metric is estimated.|day|
|`page_fan_adds`|The number of new people who have liked your Page.|day|
|`page_fan_adds_unique`|The number of new people who have liked your Page.|day, week, days_28|
|`page_fans_by_like_source`|This is a breakdown of the number of Page likes from the most common places where people can like your Page. (See [possible types](https://developers.facebook.com/docs/graph-api/reference/v2.5/insights#page-like-sources))|day|
|`page_fans_by_like_source_unique`|The number of people who liked your Page, broken down by the most common places where people can like your Page. (See [possible types](https://developers.facebook.com/docs/graph-api/reference/v2.5/insights#page-like-sources))|day|
|`page_fan_removes`|Unlikes of your Page.|day|
|`page_fan_removes_unique`|Unlikes of your Page.|day, week, days_28|
|`page_fans_by_unlike_source_unique`|The number of people who unliked your Page, broken down by the most common ways people can unlike your Page.|day|
