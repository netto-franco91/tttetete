# Email

The component sends emails, making it possible to configure the BCC and CC fields. <br>
It is possible to send emails via interface and service.

- [Event Listeners](#Event-Listeners)
- [Handler Methods](#Handler-Methods)
- [Service Methods](#Service-Methods)
- <a href="https://github.com/philips-emr/tasy-framework/blob/dev/packages/framework-demo/src/main/components/w-email/" target="_blank">Demo link</a>
- <a href="http://design.emr.philips.com.br/library/wip/components/input-controls/emailbox/" target="_blank">Design Spec link</a>


## Event Listeners
- [onLoad](#onLoad)
### onLoad
----
#### :clock230: When?
This event was triggered on the element's click.  <br>
The event cannot be listen through Odin (Schematics). <br>
It only can be listen by the HTML creator, see on exemple section.  <br>

#### :bookmark_tabs: Parameters
*schematic:* (Object)  Function schematic <br>
*handler:* (Object) Component handler <br>
*event:* Not available

#### :pencil2: Example

The event cannot be listen through Odin (Schematics). <br>
It only can be listen by the HTML creator, example about how to create the HTML below.  <br>
<br>
<b>HTML File:</b>
html
<div>
    <tasy-wemail w-onload="loaded($handler)"></tasy-wemail>
</div>

<b>JavaScript File:</b>
```javascript
$scope.loaded = (handler) => {
  $scope.handler = handler;
}
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

#### :leftwards_arrow_with_hook: Return
Not available

#### :pencil2: Example
```javascript
import { Controller } from '@philips/odin-ext';
import { WDBPanel } from 'odin-utils/controllers';

@Controller({ domain: 'atePac/AtePacA1', code: 726168 })
export default class SendGuidanceEmailOkClick extends WDLGPanelButton 
  @Inject('emailFactory')
  emailFactory;
  
  setBccEnabled(emailFactory, emailService) {
    emailFactory.setBccEnabled(false);
  }
}
```

### setBccVisible
----
#### :page_with_curl: Description
This method is used to visible the BCC field. Default value 'true'

#### :bookmark_tabs: Parameters
Boolean

#### :leftwards_arrow_with_hook: Return
Not available

#### :pencil2: Example
```javascript
import { Controller } from '@philips/odin-ext';
import { WDBPanel } from 'odin-utils/controllers';

@Controller({ domain: 'atePac/AtePacA1', code: 726168 })
export default class SendGuidanceEmailOkClick extends WDLGPanelButton 
  @Inject('emailFactory')
  emailFactory;
  
  setBccVisible(emailFactory, emailService) {
    emailFactory.setBccVisible(false);
  }
}
```


### setCcEnabled
----
#### :page_with_curl: Description
This method is used to enable the CC field. Default value 'true'

#### :bookmark_tabs: Parameters
Boolean

#### :leftwards_arrow_with_hook: Return
Not available

#### :pencil2: Example
```javascript
import { Controller } from '@philips/odin-ext';
import { WDBPanel } from 'odin-utils/controllers';

@Controller({ domain: 'atePac/AtePacA1', code: 726168 })
export default class SendGuidanceEmailOkClick extends WDLGPanelButton 
  @Inject('emailFactory')
  emailFactory;
  
  setCcEnabled(emailFactory, emailService) {
    emailFactory.setCcEnabled(false);
  }
}
```


### setCcVisible
----
#### :page_with_curl: Description
This method is used to visible the CC field. Default value 'true'

#### :bookmark_tabs: Parameters
Boolean

#### :leftwards_arrow_with_hook: Return
Not available

#### :pencil2: Example
```javascript
import { Controller } from '@philips/odin-ext';
import { WDBPanel } from 'odin-utils/controllers';

@Controller({ domain: 'atePac/AtePacA1', code: 726168 })
export default class SendGuidanceEmailOkClick extends WDLGPanelButton 
  @Inject('emailFactory')
  emailFactory;
  
  setCcVisible(emailFactory, emailService) {
    emailFactory.setCcVisible(false);
  }
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
import { Controller, Inject } from '@philips/odin-ext';
import { WDLGPanelButton } from 'odin-utils/controllers';

@Controller({ domain: 'atePac/AtePacA1', code: 726168 })
export default class SendGuidanceEmailOkClick extends WDLGPanelButton {
  @Inject('emailFactory')
  emailFactory;

  @Inject('emailService')
  emailService;

  sendEmail(schematics, ieAttachment) {
    let email = this.emailFactory.create();
    email.subject($scope.subject);
    email.senderEmail($scope.from);

    //some other options
    let separator = ';';
    email.recipientEmails($scope.to, separator);
    email.recipientsCc($scope.cc, separator);
    email.recipientsBcc($scope.bcc, separator);

    email.username($scope.username);
    email.contactName($scope.contact);
    email.content($scope.message);
    email.htmlContent(true);
    
    //attachments
    email.attachments($scope.attachments);
    email.requestReadReceipt($scope.requestRead);

    //forceUseSystemParamsCredentials
    //used to force the system to use credentials configured in System Menu (parameter 38 and 40)
    //instead the credentials of current user.
    //Obs: The default is false.
    email.forceUseSystemParamsCredentials(true);

    email = email.build();
    return this.emailService.sendEmail(email);
  }
}
```


 ### Send e-mails With Reports
----
#### :page_with_curl: Description
Send emails with reports using the w-email service.

#### :pencil2: Example
```javascript
import { Controller, Inject } from '@philips/odin-ext';
import { WDLGPanelButton } from 'odin-utils/controllers';

@Controller({ domain: 'atePac/AtePacA1', code: 726168 })
export default class SendGuidanceEmailOkClick extends WDLGPanelButton {
  @Inject('emailFactory')
  emailFactory;

  @Inject('emailService')
  emailService;

  sendEmail(schematics, ieAttachment) {
    let email = this.emailFactory.create();
    email.subject($scope.subject);
    email.senderEmail($scope.from);

    //some other options
    let separator = ';';
    email.recipientEmails($scope.to, separator);
    email.recipientsCc($scope.cc, separator);
    email.recipientsBcc($scope.bcc, separator);

    email.username($scope.username);
    email.contactName($scope.contact);
    email.content($scope.message);
    email.htmlContent(true);
    
    //attachments
    email.attachments($scope.attachments);
    email.requestReadReceipt($scope.requestRead);

    //forceUseSystemParamsCredentials
    //used to force the system to use credentials configured in System Menu (parameter 38 and 40)
    //instead the credentials of current user.
    //Obs: The default is false.
    email.forceUseSystemParamsCredentials(true);

    //reports
    let reportsParam = [];
    reportsParam[0] = ReportService.createReportParam('WATE', 66379, { NR_CIRURGIA: 10 }, '', '', false, null);
    email.reports(reportsParam);
    // Obs: When reports don't return records and it's configurate to don't print without records,
    // the report isn't attachment in the email.
  
    email = email.build();
    return this.emailService.sendEmailWithReports(email, email.reports);
  }
}
```
