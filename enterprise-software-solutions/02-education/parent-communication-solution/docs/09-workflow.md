# 09 - Parent Communication Workflows

## The Translation Workflow
1. Teacher sends message in **English**.
2. Messaging engine identifies recipient's preferred language (**Spanish**).
3. Payload sent to Translation API in the background.
4. Message saved in DB with both original and translated text.
5. Push notification sent to parent in Spanish.
6. Parent opens app and sees the message in their native tongue.

## The Interview Booking Workflow
1. Teacher sets "Available Hours" for a parent meeting.
2. System generates unique slots and notifies the class parents.
3. Parent selects a slot via the mobile app.
4. System confirms booking and adds it to the calendars of both parties.
5. Automatic reminder sent 1 hour before the meeting.
