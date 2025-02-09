# Create and Manage Subscriptions

## Attributes of a Subscription

- ackTimeoutSeconds.

  Specifies the max amount of time for the server to mark the record as
  unacknowledged, after which the record will be sent again.

- maxUnackedRecords.

  The maximum amount of unacknowledged records allowed. After exceeding the size
  set, the server will stop sending records to corresponding consumers.

## Create a subscription

Every subscription has to specify which stream to subscribe to, which means you
have to make sure the stream to be subscribed has already been created.

When creating a subscription, you can provide the attributes mentioned like
this:

```java
// CreateSubscriptionExample.java
```

## Delete a subscription

To delete a subscription without the force flag, you need to make sure that
there is no active subscription consumer.

### Delete a subscription with the force flag

If you do want to delete a subscription with running consumers, enable force
deletion. While force deleting a subscription, the subscription will be in
deleting state and closing running consumers, which means you will not be able
to join, delete or create a subscription with the same name. After the deletion
completes, you can create a subscription with the same name. However, this new
subscription will be a brand new subscription. Even if they subscribe to the
same stream, this new subscription will not share the consumption progress with
the deleted subscription.

```java
// DeleteSubscriptionExample.java
```

## List subscriptions

To list all subscriptions in HStream

```java
// ListSubscriptionsExample.java
```
