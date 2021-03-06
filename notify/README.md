

# notify
`import "github.com/betterdoctor/kit/notify"`

* [Overview](#pkg-overview)
* [Index](#pkg-index)

## <a name="pkg-overview">Overview</a>
Package notify provides functions for sending notifications to the team




## <a name="pkg-index">Index</a>
* [func Slack(url, title, message string) error](#Slack)


#### <a name="pkg-files">Package files</a>
[doc.go](/src/github.com/betterdoctor/kit/notify/doc.go) [slack.go](/src/github.com/betterdoctor/kit/notify/slack.go) 





## <a name="Slack">func</a> [Slack](/src/target/slack.go?s=789:833#L14)
``` go
func Slack(url, title, message string) error
```
Slack notifies the slack URL with the title and message.
If an empty string is passed for URL the notification is skipped without error,
this allows for code to conditionally send notifications. For example an
application could use a `SLACK_WEBHOOK_URL` environment variable to toggle on/off
notifications without producing errors for the application.

Example:


	// `SLACK_WEBHOOK_URL` behaves like a toggle for enabling/disabling notifications
	if err := notify.Slack(os.Getenv("SLACK_WEBHOOK_URL"), "heeeeey", "yoou guyyyszz <ANNOYING_GIF>"); err != nil {
	  // do something w/ err
	}

An error will only be returned if there is an issue with the network or Slack API








- - -
Generated by [godoc2md](http://godoc.org/github.com/davecheney/godoc2md)
