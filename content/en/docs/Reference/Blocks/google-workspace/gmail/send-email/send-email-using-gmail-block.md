---
title: "Send Email Using Gmail"
linkTitle: "Send Email Using Gmail"
description: "Sends an email using the Gmail SMTP server."
---

{{< figure src="/blocks/google-workspace-send-email-using-gmail-block-icon.png" alt="Icon" class="block-icon" >}}

# {{% param title %}}

<p class="namespace">(Cortex.Blocks.GoogleWorkspace.Gmail.SendEmail.SendEmailUsingGmailBlock)</p>

## Description

Connects to the [SMTP][] server hosted by [Gmail][] using the specified [Basic Email Session Details][Basic Email Session Details Property], and sends an [Email Message][Email Message Property].

[Close Session][Close Session Property] can be specified to choose whether the connection to the [SMTP][] server is closed or is kept open for use on subsequent Send Email Using SMTP Server blocks.

## Examples

## Properties

### Email Message

### Gmail Session Details

### Close Session

## Exceptions

## Remarks

### Known Limitations

[Email Message Property]: {{< ref "#email-message" >}}
[Basic Email Session Details Property]: {{< ref "#basic-email-session-details" >}}
[Close Session Property]: {{< ref "#close-session" >}}

[SASL]: {{< url "Cortex.Reference.Glossary.P-T.SASL" >}}
[SMTP]: {{< url "Cortex.Reference.Glossary.P-T.SMTP" >}}
[SSL]: {{< url "Cortex.Reference.Glossary.P-T.SSL" >}}
[TLS]: {{< url "Cortex.Reference.Glossary.P-T.TLS" >}}
[BCC Glossary]: {{< url "Cortex.Reference.Glossary.A-E.BCC" >}}
[CC Glossary]: {{< url "Cortex.Reference.Glossary.A-E.CC" >}}
[CRL]: {{< url "Cortex.Reference.Glossary.A-E.CRL" >}}
[Gmail]: {{< url "Cortex.Reference.Glossary.F-J.Gmail" >}}
[Outlook]: {{< url "Cortex.Reference.Glossary.K-O.Outlook" >}}
[RFC 5321]: {{< url "IETF.Email.RFC5321" >}}