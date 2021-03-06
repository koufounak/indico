Changelog
=========


Version 2.0a2
-------------

*Unreleased*

Improvements
^^^^^^^^^^^^

- Hide category field in event creation dialog if there are no
  subcategories (:issue:`3112`)
- Remove length limit from registration form field captions (:issue:`3119`)
- Use semicolons instead of commas as separator when exporting list
  values (such as multi-select registration form fields) to CSV or
  Excel (:issue:`3060`)
- Use custom site title in page title (:issue:`3018`)
- Allow manually entering dates in datetime fields (:issue:`3136`)
- Send emails through a celery task. This ensures users do not get
  an error if the mail server is temporarily unavailable. Sending an
  email is also retried for a while in case of failure. In case of a
  persistent failure the email is dumped to the temp directory and
  can be re-sent manually using the new ``indico resend_email``
  command (:issue:`3121`)

Bugfixes
^^^^^^^^

- Do not intercept HTTP exceptions containing a custom response.
  When raising such exceptions we do not want the default handling
  but rather send the custom response to the client.
- Do not apply margin for empty root category sidebar (:issue:`3116`,
  thanks :user:`nop33`)
- Fix alignment of info-grid items on main conference page (:issue:`3126`)
- Properly align the label of the attachment folder title field
- Fix some rare unicode errors during exception handling/logging
- Clarify messages in session block rescheduling dialogs (:issue:`3080`)
- Fix event header bar in IE11 (:issue:`3135`)
- Fix footer on login page (:issue:`3132`)
- Use correct module name for abstract notification emails in the event log


Version 2.0a1
-------------

*Released on October 20, 2017*

This is the first release of the 2.0 series, which is an almost complete
rewrite of Indico based on a modern software stack and PostgreSQL.
