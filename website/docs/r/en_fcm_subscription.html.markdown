---
subcategory: 'Event Notifications'
layout: 'ibm'
page_title: 'IBM : ibm_en_subscription_android'
description: |-
  Manages Event Notifications Android subscription.
---

# ibm_en_subscription_android

Create, update, or delete a FCM subscription by using IBM Cloud™ Event Notifications.

## Example usage

```terraform
resource "ibm_en_subscription_android" "android_subscription" {
  instance_guid    = ibm_resource_instance.en_terraform_test_resource.guid
  name           = "Android Subscription"
  description    = "Android Subscription for Notification"
  destination_id = ibm_en_destination_android.destinationandroidnew.destination_id
  topic_id       = ibm_en_topic.topic1.topic_id
}
```

## Argument reference

Review the argument reference that you can specify for your resource.

- `instance_guid` - (Required, Forces new resource, String) Unique identifier for IBM Cloud Event Notifications instance.

- `name` - (Requires, String) Subscription name.

- `description` - (Optional, String) Subscription description.

- `destination_id` - (Requires, String) Destination ID.

- `topic_id` - (Required, String) Topic ID.


## Attribute reference

In addition to all argument references listed, you can access the following attribute references after your resource is created.

- `id` - (String) The unique identifier of the `android_subscription`.

- `subscription_id` - (String) The unique identifier of the created subscription.

- `updated_at` - (Required, String) Last updated time.

## Import

You can import the `ibm_en_subscription_android` resource by using `id`.
The `id` property can be formed from `instance_guid`, and `subscription_id` in the following format:

```
<instance_guid>/<subscription_id>
```

- `instance_guid`: A string. Unique identifier for IBM Cloud Event Notifications instance.
- `subscription_id`: A string. Unique identifier for Subscription.

**Example**

```
$ terraform import ibm_en_subscription_android.android_subscription <instance_guid>/<subscription_id>
```
