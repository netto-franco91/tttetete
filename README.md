# Email

The component sends emails, making it possible to configure the BCC and CC fields. <br>
It is possible to send emails via interface and service.

- [Event Listeners](#Event-Listeners)
- [Handler Methods](#Handler-Methods)
- [Service Methods](#Service-Methods)
- <a href="#" target="_blank">Demo link</a>
- <a href="#" target="_blank">Design Spec link</a>


## Event Listeners
- [onClick](#onClick)
### onClick
----
#### :clock230: When?
This event was triggered on the element's click.  <br>
The event cannot be listen through Odin (Schematics). <br>
It only can be listen by the HTML creator, see on exemple section.  <br>

#### :bookmark_tabs: Parameters
**schematic:** _(Object)_  Function schematic <br>
**handler:** _(Object)_ Component handler <br>
**event:** Not available

#### :pencil2: Example

The event cannot be listen through Odin (Schematics). <br>
It only can be listen by the HTML creator, example about how to create the HTML below.  <br>
<br>
<b>HTML File:</b>
```html
<div>
    <button ng-click="openEmail()">Show Email</button>
</div>
```
<b>JavaScript File:</b>
```javascript
scope.openEmail = function() {
  let email = emailFactory.create();
  email.subject("test subject");
  email.senderEmail("sender@email.com");
  email.recipientEmails("recipient@email.com");
  email.username("Joao");
  email.contactName("John");
  email.content("This is a default message");

  let beforeSend = (email) =>{
    if(email.contactName !== "John"){
      email.content = "Not default message";
    }
    alert("beforeSend function called!");
  };

  let afterSend = () =>{
    alert("afterSend function called!");
  };

  let afterError = () =>{
    alert("afterError function called!");
  };

  emailPopupFactory.show(email.build(), beforeSend, afterSend, undefined, afterError);
```

## Handler Methods
- [setBccEnabled](#setBccEnabled)
- [setBccVisible](#setBccVisible)
- [setCcEnabled](#setCcEnabled)
- [setCcVisible](#setCcVisible)


### setBccEnabled
----
#### :page_with_curl: Description
This method is used to enable the BCC field. Default value 'true'

#### :bookmark_tabs: Parameters
Boolean

#### :pencil2: Example
```javascript
feature.register(myModule, 'myFeature', 1, MyFeature, 1);

function sendEmail(emailFactory, emailService) {
  emailFactory.setBccEnabled(false);
}
```

### setBccVisible
----
#### :page_with_curl: Description
This method is used to visible the BCC field. Default value 'true'

#### :bookmark_tabs: Parameters
Boolean

#### :pencil2: Example
```javascript
feature.register(myModule, 'myFeature', 1, MyFeature, 1);

function sendEmail(emailFactory, emailService) {
  emailFactory.setBccVisible(false);
}
```

### setCcEnabled
----
#### :page_with_curl: Description
This method is used to enable the CC field. Default value 'true'

#### :bookmark_tabs: Parameters
Boolean

#### :pencil2: Example
```javascript
feature.register(myModule, 'myFeature', 1, MyFeature, 1);

function sendEmail(emailFactory, emailService) {
  emailFactory.setCcEnabled(false);
}
```

### setCcVisible
----
#### :page_with_curl: Description
This method is used to visible the CC field. Default value 'true'

#### :bookmark_tabs: Parameters
Boolean

#### :pencil2: Example
```javascript
feature.register(myModule, 'myFeature', 1, MyFeature, 1);

function sendEmail(emailFactory, emailService) {
  emailFactory.setCcVisible(false);
}
```


## Service Methods
- [Send e-mails](#send-emails)
- [Send e-mails With Reports](#send-emails-with-reports)

 ### Send e-mails
----
#### :page_with_curl: Description
Send emails using the w-email service.

#### :pencil2: Example
```javascript
feature.register(myModule, 'myFeature', 1, MyFeature, 1);

function MyFeature(emailFactory, emailService) {
  'ngInject';

  var email = emailFactory.create();

  email.senderEmail($scope.from)
  .subject($scope.subject)
  .contactName($scope.name)
  .username($scope.username)
  .content($scope.message);

  //some other options
  let separator = ';';
  email.recipientEmails($scope.to, separator)
  .recipientsCc($scope.cc, separator)
  .recipientsBcc($scope.bcc, separator);

  //attachments
  email.attachments($scope.attachments)
  .replyEmail($scope.replayTo)
  .requestReadReceipt($scope.requestRead)
  .isHtmlContent($scope.contentType);

  //forceUseSystemParamsCredentials
  //used to force the system to use credentials configured in System Menu (parameter 38 and 40)
  //instead the credentials of current user.
  //Obs: The default is false.
  email.forceUseSystemParamsCredentials(true);

  //attachmentLogo
  //Is optional parameter for the sending of the logo of the establishment in the attachment.
  //Values (true or false)
  email.attachmentLogo(true);

  email = email.build();// u need to build the object after filled it after your params are ready, just pass them to emailService and its done

  emailService.sendEmail(email).then(function(response) {
    alert("Success" + response);
  },
  function(status) {
    alert("Error" + status.message);
  });
}
```


 ### Send e-mails With Reports
----
#### :page_with_curl: Description
Send emails with reports using the w-email service.

#### :pencil2: Example
```javascript
feature.register(myModule, 'myFeature', 1, MyFeature, 1);

function MyFeature(emailFactory, emailService) {
  'ngInject';

  var email = emailFactory.create();

  email.senderEmail($scope.from)
  .subject($scope.subject)
  .contactName($scope.name)
  .username($scope.username)
  .content($scope.message);

  //some other options
  let separator = ';';
  email.recipientEmails($scope.to, separator)
  .recipientsCc($scope.cc, separator)
  .recipientsBcc($scope.bcc, separator);

  //attachments
  email.attachments($scope.attachments)
  .replyEmail($scope.replayTo)
  .requestReadReceipt($scope.requestRead)
  .isHtmlContent($scope.contentType);

  //reports
  let reportsParam = [];
  reportsParam[0] = ReportService.createReportParam('WATE', 66379, { NR_CIRURGIA: 10 }, '', '', false, null);
  email.reports(reportsParam);
  // Obs: When reports don't return records and it's configurate to don't print without records,
  // the report isn't attachment in the email.

  //forceUseSystemParamsCredentials
  //used to force the system to use credentials configured in System Menu (parameter 38 and 40)
  //instead the credentials of current user.
  //Obs: The default is false.
  email.forceUseSystemParamsCredentials(true);

  //attachmentLogo
  //Is optional parameter for the sending of the logo of the establishment in the attachment.
  //Values (true or false)
  email.attachmentLogo(true);

  email = email.build();// u need to build the object after filled it after your params are ready, just pass them to emailService and its done

  emailService.sendEmailWithReports(email, email.reports).then(function(response) {
    alert("Success" + response);
  },
  function(status) {
    alert("Error" + status.message);
  });
}
```
