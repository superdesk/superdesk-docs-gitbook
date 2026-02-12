# 18 superdesk api

Superdesk features a **Content API**, and as of Superdesk v1.33, Superdesk now features a new API: The **Superdesk Production API.** The Content API allows third-party apps to interact with content that has been published through Superdesk. The Production API allows third-party apps to consume content within Superdesk that has yet to be published. This API is important for facilitating the integration of other apps with Superdesk. Up till now, the Superdesk Content API was the only API aimed for third-party apps, but (by design) it only provides access to published content. While working with news organisations, we identified the need for providing access to production content as well, thus this new API.

Useful resources:

* The initial Production API Reference: https://superdesk.readthedocs.io/en/latest/production\_api.html
* The new authentication server (for granting apps access to the API): https://superdesk.readthedocs.io/en/latest/auth\_server.html
* Complementary JSON schema: https://github.com/superdesk/superdesk-core/blob/master/docs/superdesk-ninjs-schema.json
