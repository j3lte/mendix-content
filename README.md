# Outlook MSG Parser

![LOGO](/content/marketplace_icon.png)

This is a module that enables a Mendix Developer to parse Outlook MSG files that are stored as FileDocument objects.

## Contents
### Domain Model

![Domain Model](/content/domain-model.png)

### Java Action

The module contains 2 Java Actions:

- **Parse MSG File from FileDocument**
  - This will take a FileDocument and create non-persistent objects that are represented in the Domain Model
    - Please open the entities to see the attached documentation
  - It returns the OutlookMSG object, the other objects can be retrieved over a reference
  - There are two lists of Attachments:
    - FileAttachments: These are attachments that are added by the user (what we typically see as an attachment)
    - EmbeddedAttachments: These are attachments that are embedded in the e-mail and rarely used
  - Attachments have a Download ID that can be used in the other Java Action:
- **Download MSG Attachment**
  - This will take a FileDocument and the Download ID and return a FileDocument (or empty) as the attachment
  - See example Microflow, it includes some checks and error handling

## Issues/requests?

This module is published as Community Supported. If you have issues, please report them on Github: [https://github.com/j3lte/mendix-content/issues](https://github.com/j3lte/mendix-content/issues)

_Need more help? Or maybe help with your Mendix project?_

[Check out CaffCode](https://caffcode.com)
