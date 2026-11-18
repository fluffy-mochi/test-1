# Release notification API example

An `after:release` hook can send a notification to a service your team runs. This example uses a stand-in notification
service at `releases.example.com`. Replace it with your own endpoint before using the hook.

## Request

Add the hook to `.release-it.json`. The service in this example accepts the released version as a form field.

```json
{
  "hooks": {
    "after:release": "curl --fail --data-urlencode 'version=${version}' https://releases.example.com/notifications"
  }
}
```

## Rate limit

The example API accepts 60 requests per minute per client. When the client exceeds its limit, the example service
returns HTTP 429 with a `Retry-After` header in seconds.

For example, a response with `Retry-After: 15` tells the client to wait 15 seconds before sending the next
notification. If several release jobs share one client, they also share its request budget.
