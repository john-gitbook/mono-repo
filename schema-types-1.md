# Schema Types

<details>

<summary><strong>Table of Contents</strong></summary>

* [Query](broken-reference)
* [Mutation](broken-reference)
* [Objects](broken-reference)
  * [AdminLogin](broken-reference)
  * [ConnectivityStatus](broken-reference)
  * [DailyCheckCount](broken-reference)
  * [DailySchedule](broken-reference)
  * [EndUserRef](broken-reference)
  * [EndUserState](broken-reference)
  * [FeatureExplainabilityItem](broken-reference)
  * [GeoCoordinates](broken-reference)
  * [GeoLocation](broken-reference)
  * [GetEndUserOutput](broken-reference)
  * [GetEndUsersByIpConnection](broken-reference)
  * [GroupExplainabilityItem](broken-reference)
  * [IpAddressInfo](broken-reference)
  * [ItemList](broken-reference)
  * [KeyValuePair](broken-reference)
  * [LabelCount](broken-reference)
  * [ListAdminLoginsConnection](broken-reference)
  * [ListEndUsersConnection](broken-reference)
  * [LocationWithPrevalence](broken-reference)
  * [PublicEndUser](broken-reference)
  * [PublicEndUserDetails](broken-reference)
  * [PublicEndUserTrustScore](broken-reference)
  * [PublicIntegrationStatus](broken-reference)
  * [PublicProviderEndUserDetails](broken-reference)
  * [PublicRiskyActivityCounts](broken-reference)
  * [PublicScoreExplainabilitySummary](broken-reference)
  * [PublicUserDevice](broken-reference)
  * [PublicUserSignInInfo](broken-reference)
  * [TotalHits](broken-reference)
  * [TotalWithMedian](broken-reference)
  * [TypedKeyValuePair](broken-reference)
* [Inputs](broken-reference)
  * [DailyScheduleInput](broken-reference)
  * [ItemListInput](broken-reference)
  * [KeyValuePairInput](broken-reference)
  * [ListEndUsersInput](broken-reference)
  * [OrderBy](broken-reference)
  * [RegisterWebhookWithApiKey](broken-reference)
  * [RegisterWebhookWithDuoSecurityClient](broken-reference)
  * [TimestampRange](broken-reference)
* [Enums](broken-reference)
  * [ActivityResultType](broken-reference)
  * [DataType](broken-reference)
  * [DeviceType](broken-reference)
  * [EndUserStatus](broken-reference)
  * [HttpMethod](broken-reference)
  * [LevelOfTrust](broken-reference)
  * [ListType](broken-reference)
  * [Order](broken-reference)
  * [OsType](broken-reference)
  * [Provider](broken-reference)
  * [TrustScoreGroupId](broken-reference)
  * [TrustScoreModelType](broken-reference)
  * [TrustScoreVersion](broken-reference)
  * [TrustScoreWeight](broken-reference)
  * [UserTypeClassification](broken-reference)
  * [WorkflowState](broken-reference)
* [Scalars](broken-reference)
  * [AWSDate](broken-reference)
  * [AWSDateTime](broken-reference)
  * [AWSEmail](broken-reference)
  * [AWSIPAddress](broken-reference)
  * [AWSJSON](broken-reference)
  * [AWSPhone](broken-reference)
  * [AWSTime](broken-reference)
  * [AWSTimestamp](broken-reference)
  * [AWSURL](broken-reference)
  * [Boolean](broken-reference)
  * [Float](broken-reference)
  * [ID](broken-reference)
  * [Int](broken-reference)
  * [String](broken-reference)

</details>

## Query

| Field                          |  Argument | Type                                             | Description                                                                                                                                                                                                                                                |
| ------------------------------ | --------: | ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ping**                       |           | [Boolean](broken-reference)!                     | Ping the API to check if it is up and running.                                                                                                                                                                                                             |
| **getEndUserState**            |           | [EndUserState](broken-reference)!                | Fetch a concise summary of end-user information, including key fields and relevant details. Use this query when you want to get a basic end-user digest.                                                                                                   |
|                                |     login | [String](broken-reference)!                      | End-user's email address.                                                                                                                                                                                                                                  |
| **getEndUsersByIp**            |           | [GetEndUsersByIpConnection](broken-reference)!   | Retrieve end-users associated with a specified IP address.                                                                                                                                                                                                 |
|                                | ipAddress | [String](broken-reference)!                      | IP Address.                                                                                                                                                                                                                                                |
|                                |  pageSize | [Int](broken-reference)                          | Number of items per page. Default pageSize is 50. Max pageSize is 1000.                                                                                                                                                                                    |
|                                | pageToken | [String](broken-reference)                       | Token for paginating through the result set.                                                                                                                                                                                                               |
| **getEndUser**                 |           | [GetEndUserOutput](broken-reference)!            | Fetch end-user's detailed information, including including devices, integrations, factors and more. Use this query when you want to get a comprehensive end-user details.                                                                                  |
|                                |     login | [String](broken-reference)!                      | End-user's email address.                                                                                                                                                                                                                                  |
| **listEndUsers**               |           | [ListEndUsersConnection](broken-reference)!      | Fetch the list of end-users. Use this query to retrieve a large number of items using paging. The default page size is 100, and the maximum page size is 1000. Page token is used to retrieve the next page. If not provided, the first page is retrieved. |
|                                |     input | [ListEndUsersInput](broken-reference)!           | Input data end-users listing.                                                                                                                                                                                                                              |
|                                |  pageSize | [Int](broken-reference)                          | Number of items per page. Default pageSize is 100. Max pageSize is 500.                                                                                                                                                                                    |
|                                | pageToken | [String](broken-reference)                       | Token for paginating through the result set.                                                                                                                                                                                                               |
| **getTotalCheckFailingCounts** |           | \[[DailyCheckCount](broken-reference)!]!         | Experimental API for PoC purposes.                                                                                                                                                                                                                         |
| **listAdminLogins**            |           | [ListAdminLoginsConnection](broken-reference)!   |                                                                                                                                                                                                                                                            |
|                                |  pageSize | [Int](broken-reference)                          |                                                                                                                                                                                                                                                            |
|                                | pageToken | [String](broken-reference)                       |                                                                                                                                                                                                                                                            |
| **getIntegrationsStatus**      |           | \[[PublicIntegrationStatus](broken-reference)!]! |                                                                                                                                                                                                                                                            |

## Mutation

| Field                                    | Argument | Type                                                      | Description                                                                                                                                                                                        |
| ---------------------------------------- | -------: | --------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **registerWebhookWithApiKey**            |          | [ID](broken-reference)!                                   | Register a Webhook Notification Target with an API key as a target for Failed Check findings. See more at [https://docs.oort.io/integrations/webhooks](https://docs.oort.io/integrations/webhooks) |
|                                          |    input | [RegisterWebhookWithApiKey](broken-reference)!            | Input data for registering a webhook with an API key.                                                                                                                                              |
| **registerWebhookWithDuoSecurityClient** |          | [ID](broken-reference)!                                   | Register a Webhook Notification Target with Duo Secret Client as a target for Failed Check findings.                                                                                               |
|                                          |    input | [RegisterWebhookWithDuoSecurityClient](broken-reference)! | Input data for registering a webhook with Duo Security Client.                                                                                                                                     |
| **unregisterWebhook**                    |          | [Boolean](broken-reference)!                              | Unregister a Webhook Notification Target.                                                                                                                                                          |
|                                          |       id | [ID](broken-reference)!                                   | ID of the webhook to unregister.                                                                                                                                                                   |

## Objects

### AdminLogin

| Field           | Argument | Type                                     | Description |
| --------------- | -------: | ---------------------------------------- | ----------- |
| **login**       |          | [String](broken-reference)!              |             |
| **displayName** |          | [String](broken-reference)               |             |
| **lastSignIn**  |          | [PublicUserSignInInfo](broken-reference) |             |

### ConnectivityStatus

| Field          | Argument | Type                       | Description |
| -------------- | -------: | -------------------------- | ----------- |
| **statusCode** |          | [Int](broken-reference)!   |             |
| **payload**    |          | [String](broken-reference) |             |
| **reason**     |          | [String](broken-reference) |             |

### DailyCheckCount

| Field     | Argument | Type                        | Description |
| --------- | -------: | --------------------------- | ----------- |
| **day**   |          | [String](broken-reference)! |             |
| **total** |          | [Int](broken-reference)!    |             |

### DailySchedule

| Field      | Argument | Type                     | Description |
| ---------- | -------: | ------------------------ | ----------- |
| **hour**   |          | [Int](broken-reference)! |             |
| **minute** |          | [Int](broken-reference)! |             |

### EndUserRef

Represents a reference to an end-user.

| Field            | Argument | Type                        | Description                                     |
| ---------------- | -------: | --------------------------- | ----------------------------------------------- |
| **id**           |          | [ID](broken-reference)!     | The end-user ID in Cisco Identity Intelligence. |
| **displayName**  |          | [String](broken-reference)! | The end-user's display name.                    |
| **login**        |          | [String](broken-reference)! | End-user's email address.                       |
| **referenceUrl** |          | [String](broken-reference)  | End-user's URL in Cisco Identity Intelligence.  |

### EndUserState

Represents a concise summary of end-user information, including key fields and relevant details.

| Field                         | Argument | Type                                           | Description                                                                                |
| ----------------------------- | -------: | ---------------------------------------------- | ------------------------------------------------------------------------------------------ |
| **id**                        |          | [ID](broken-reference)!                        | The end-user ID in Cisco Identity Intelligence.                                            |
| **displayName**               |          | [String](broken-reference)!                    | The end-user's display name.                                                               |
| **login**                     |          | [String](broken-reference)!                    | End-user's email address.                                                                  |
| **employeeId**                |          | \[[String](broken-reference)!]                 | List of employee IDs associated with the end-user in the Identity Provider and HR systems. |
| **status**                    |          | [String](broken-reference)!                    | The aggregated end-user status in the identity providers.                                  |
| **userTypeClassification**    |          | [UserTypeClassification](broken-reference)     | The end-user classification in Cisco Identity Intelligence.                                |
| **managerLogin**              |          | [String](broken-reference)                     | End-user's manager email address.                                                          |
| **ipAddresses**               |          | \[[IpAddressInfo](broken-reference)!]          | List of IP Addresses used by the end-user.                                                 |
| **lastSignInLocation**        |          | [GeoLocation](broken-reference)                | Deprecated. Do not use!                                                                    |
| **phoneNumber**               |          | [String](broken-reference)                     | End-user's phone number.                                                                   |
| **unusedApplications**        |          | \[[String](broken-reference)!]                 | Names of applications the end-user has access and did not access in the past 30 days.      |
| **usedApplications**          |          | \[[String](broken-reference)!]                 | Names of applications the end-user has access and accessed in the past 30 days.            |
| **usedFactors**               |          | \[[String](broken-reference)!]                 | Authentication factors used by the end-user.                                               |
| **referenceUrl**              |          | [String](broken-reference)                     | End-user's URL in Cisco Identity Intelligence.                                             |
| **registeredLocationDetails** |          | [GeoLocation](broken-reference)                | The end-user's registered location                                                         |
| **workingLocationDetails**    |          | \[[LocationWithPrevalence](broken-reference)!] | List of the locations the end-user works in.                                               |

### FeatureExplainabilityItem

| Field         | Argument | Type                                 | Description |
| ------------- | -------: | ------------------------------------ | ----------- |
| **featureId** |          | [String](broken-reference)!          |             |
| **details**   |          | \[[KeyValuePair](broken-reference)!] |             |

### GeoCoordinates

| Field         | Argument | Type                      | Description |
| ------------- | -------: | ------------------------- | ----------- |
| **latitude**  |          | [Float](broken-reference) |             |
| **longitude** |          | [Float](broken-reference) |             |

### GeoLocation

IP Address geolocation information.

| Field       | Argument | Type                       | Description                                    |
| ----------- | -------: | -------------------------- | ---------------------------------------------- |
| **city**    |          | [String](broken-reference) | The city name.                                 |
| **state**   |          | [String](broken-reference) | The state name.                                |
| **country** |          | [String](broken-reference) | two-letter country code defined in ISO 3166-1. |

### GetEndUserOutput

| Field                      | Argument | Type                                                  | Description                                        |
| -------------------------- | -------: | ----------------------------------------------------- | -------------------------------------------------- |
| **endUserDetails**         |          | [PublicEndUserDetails](broken-reference)!             | The unified end-user details across all providers. |
| **providerEndUserDetails** |          | \[[PublicProviderEndUserDetails](broken-reference)!]! | The array of end-user details by provider.         |

### GetEndUsersByIpConnection

End-users associated with a specified IP address.

| Field         | Argument | Type                                | Description                                                                                                 |
| ------------- | -------: | ----------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| **items**     |          | \[[EndUserRef](broken-reference)!]! | Itemized list of end-users associated with a specified IP address.                                          |
| **pageToken** |          | [String](broken-reference)          | Token for paginating through the result set. If pageToken is undefined, there are no more results to fetch. |

### GroupExplainabilityItem

| Field        | Argument | Type                                              | Description |
| ------------ | -------: | ------------------------------------------------- | ----------- |
| **groupId**  |          | [TrustScoreGroupId](broken-reference)!            |             |
| **severity** |          | [Int](broken-reference)                           |             |
| **weight**   |          | [TrustScoreWeight](broken-reference)              |             |
| **details**  |          | \[[FeatureExplainabilityItem](broken-reference)!] |             |

### IpAddressInfo

IP Address information.

| Field         | Argument | Type                            | Description                         |
| ------------- | -------: | ------------------------------- | ----------------------------------- |
| **ipAddress** |          | [String](broken-reference)!     | IP Address.                         |
| **location**  |          | [GeoLocation](broken-reference) | IP Address geolocation information. |

### ItemList

| Field        | Argument | Type                            | Description |
| ------------ | -------: | ------------------------------- | ----------- |
| **listType** |          | [ListType](broken-reference)!   |             |
| **items**    |          | \[[String](broken-reference)!]! |             |

### KeyValuePair

| Field     | Argument | Type                        | Description |
| --------- | -------: | --------------------------- | ----------- |
| **key**   |          | [String](broken-reference)! |             |
| **value** |          | [String](broken-reference)! |             |

### LabelCount

| Field     | Argument | Type                        | Description |
| --------- | -------: | --------------------------- | ----------- |
| **value** |          | [String](broken-reference)! |             |
| **count** |          | [Int](broken-reference)!    |             |

### ListAdminLoginsConnection

| Field         | Argument | Type                                | Description |
| ------------- | -------: | ----------------------------------- | ----------- |
| **items**     |          | \[[AdminLogin](broken-reference)!]! |             |
| **pageToken** |          | [String](broken-reference)          |             |

### ListEndUsersConnection

End-users list.

| Field         | Argument | Type                                   | Description                                                                                                 |
| ------------- | -------: | -------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| **items**     |          | \[[PublicEndUser](broken-reference)!]! | Itemized list of end-users.                                                                                 |
| **pageToken** |          | [String](broken-reference)             | Token for paginating through the result set. If pageToken is undefined, there are no more results to fetch. |

### LocationWithPrevalence

| Field                      | Argument | Type                             | Description |
| -------------------------- | -------: | -------------------------------- | ----------- |
| **location**               |          | [GeoLocation](broken-reference)! |             |
| **userLocationPrevalence** |          | [Float](broken-reference)!       |             |

### PublicEndUser

Represents end-user basic data.

| Field                      | Argument | Type                                        | Description                                                                                   |
| -------------------------- | -------: | ------------------------------------------- | --------------------------------------------------------------------------------------------- |
| **id**                     |          | [ID](broken-reference)!                     | The end-user ID in Cisco Identity Intelligence.                                               |
| **displayName**            |          | [String](broken-reference)                  | The end-user's display name.                                                                  |
| **login**                  |          | [String](broken-reference)!                 | End-user's login.                                                                             |
| **emails**                 |          | \[[String](broken-reference)!]              | List of end-user emails associated with the end-user in the Identity Provider and HR systems. |
| **status**                 |          | [EndUserStatus](broken-reference)           | The unified status of the end-user across all providers.                                      |
| **company**                |          | [String](broken-reference)                  | The company the end-user belongs to.                                                          |
| **department**             |          | [String](broken-reference)                  | The department the end-user belongs to.                                                       |
| **title**                  |          | [String](broken-reference)                  | The end-user's title.                                                                         |
| **userTypeClassification** |          | [UserTypeClassification](broken-reference)  | The unified classification of the end-user type across all providers.                         |
| **employeeIds**            |          | \[[String](broken-reference)!]              | List of employee IDs associated with the end-user in the Identity Provider and HR systems.    |
| **linkedEndUserLogins**    |          | \[[String](broken-reference)!]              | List of linked end-users' logins.                                                             |
| **groupNames**             |          | \[[String](broken-reference)!]              | List of names of the groups the end-user is a member of. Maximum 10 items.                    |
| **hasMoreGroups**          |          | [Boolean](broken-reference)!                | The indication if more groups exist for the end-user.                                         |
| **phoneNumbers**           |          | \[[String](broken-reference)!]              | The end-user's phone numbers used for authentication.                                         |
| **managerLogin**           |          | [String](broken-reference)                  | The end-user's manager login.                                                                 |
| **devices**                |          | \[[PublicUserDevice](broken-reference)!]    | List of devices the end-user uses.                                                            |
| **mfaEnabled**             |          | [Boolean](broken-reference)                 | Indicates if the MFA is enabled for the end-user.                                             |
| **lastSignIn**             |          | [PublicUserSignInInfo](broken-reference)    | The last sign details for the end-user.                                                       |
| **lastActive**             |          | [AWSDateTime](broken-reference)             | The last active timestamp for the end-user.                                                   |
| **failingChecks**          |          | \[[String](broken-reference)!]              | The checks that the end-user has failed.                                                      |
| **firstCreatedDate**       |          | [AWSDateTime](broken-reference)             | The first created date of the account across all providers.                                   |
| **providers**              |          | \[[Provider](broken-reference)!]!           | List of provider types for the integrations the end-user data is collected from.              |
| **referenceUrl**           |          | [String](broken-reference)!                 | End-user's URL in Cisco Identity Intelligence.                                                |
| **endUserTrustScore**      |          | [PublicEndUserTrustScore](broken-reference) | The end user trust score                                                                      |

### PublicEndUserDetails

Represents end-user data.

| Field                      | Argument | Type                                       | Description                                                                                   |
| -------------------------- | -------: | ------------------------------------------ | --------------------------------------------------------------------------------------------- |
| **id**                     |          | [ID](broken-reference)!                    | The end-user ID in Cisco Identity Intelligence.                                               |
| **displayName**            |          | [String](broken-reference)!                | The end-user's display name.                                                                  |
| **login**                  |          | [String](broken-reference)!                | End-user's email address.                                                                     |
| **status**                 |          | [EndUserStatus](broken-reference)!         | The unified status of the end-user across all providers.                                      |
| **userIds**                |          | \[[String](broken-reference)!]             | List of end-user IDs associated with the end-user in the Identity Provider and HR systems.    |
| **emails**                 |          | \[[String](broken-reference)!]             | List of end-user emails associated with the end-user in the Identity Provider and HR systems. |
| **company**                |          | [String](broken-reference)                 | The company the end-user belongs to.                                                          |
| **department**             |          | [String](broken-reference)                 | The department the end-user belongs to.                                                       |
| **title**                  |          | [String](broken-reference)                 | The end-user's title.                                                                         |
| **userTypeClassification** |          | [UserTypeClassification](broken-reference) | The unified classification of the end-user type across all providers.                         |
| **employeeIds**            |          | \[[String](broken-reference)!]             | List of employee IDs associated with the end-user in the Identity Provider and HR systems.    |
| **linkedEndUserLogins**    |          | \[[String](broken-reference)!]             | List of linked end-users' logins.                                                             |
| **groupNames**             |          | \[[String](broken-reference)!]             | List of names of the groups the end-user is a member of.                                      |
| **phoneNumbers**           |          | \[[String](broken-reference)!]             | The end-user's phone numbers used for authentication.                                         |
| **managerLogin**           |          | [String](broken-reference)                 | The end-user's manager login.                                                                 |
| **devices**                |          | \[[PublicUserDevice](broken-reference)!]   | List of devices the end-user uses.                                                            |
| **mfaEnabled**             |          | [Boolean](broken-reference)                | Indicates if the MFA is enabled for the end-user.                                             |
| **lastSignIn**             |          | [PublicUserSignInInfo](broken-reference)   | The last sign details for the end-user.                                                       |
| **lastActive**             |          | [AWSDateTime](broken-reference)            | The last active timestamp for the end-user.                                                   |
| **firstCreatedDate**       |          | [AWSDateTime](broken-reference)            | The first created date of the account across all providers.                                   |
| **failingChecks**          |          | \[[String](broken-reference)!]             | The checks that the end-user has failed.                                                      |
| **referenceUrl**           |          | [String](broken-reference)!                | End-user's URL in Cisco Identity Intelligence.                                                |

### PublicEndUserTrustScore

| Field                          | Argument | Type                                                 | Description                   |
| ------------------------------ | -------: | ---------------------------------------------------- | ----------------------------- |
| **levelOfTrust**               |          | [LevelOfTrust](broken-reference)!                    | The end user's level of trust |
| **scoreExplainabilitySummary** |          | [PublicScoreExplainabilitySummary](broken-reference) | Score explainability summary  |

### PublicIntegrationStatus

| Field               | Argument | Type                                    | Description |
| ------------------- | -------: | --------------------------------------- | ----------- |
| **integrationId**   |          | [ID](broken-reference)!                 |             |
| **integrationName** |          | [String](broken-reference)!             |             |
| **status**          |          | [ActivityResultType](broken-reference)! |             |
| **date**            |          | [AWSDateTime](broken-reference)!        |             |
| **error**           |          | [String](broken-reference)              |             |

### PublicProviderEndUserDetails

| Field                      | Argument | Type                                       | Description                                                                       |
| -------------------------- | -------: | ------------------------------------------ | --------------------------------------------------------------------------------- |
| **userId**                 |          | [String](broken-reference)!                | The end-user userId.                                                              |
| **provider**               |          | [Provider](broken-reference)!              | The type of the provider.                                                         |
| **firstName**              |          | [String](broken-reference)                 | The end-user's first name.                                                        |
| **lastName**               |          | [String](broken-reference)                 | The end-user's last name.                                                         |
| **displayName**            |          | [String](broken-reference)                 | The end-user's display name.                                                      |
| **login**                  |          | [String](broken-reference)!                | End-user's email address.                                                         |
| **email**                  |          | [String](broken-reference)                 | End-user primary email address.                                                   |
| **status**                 |          | [EndUserStatus](broken-reference)!         | The unified status of the end-user across all providers.                          |
| **company**                |          | [String](broken-reference)                 | The company the end-user belongs to.                                              |
| **department**             |          | [String](broken-reference)                 | The department the end-user belongs to.                                           |
| **title**                  |          | [String](broken-reference)                 | The end-user's title.                                                             |
| **userTypeClassification** |          | [UserTypeClassification](broken-reference) | The unified classification of the end-user type across all providers.             |
| **employeeId**             |          | [String](broken-reference)                 | Employee ID associated with the end-user in the Identity Provider and HR systems. |
| **managerLogin**           |          | [String](broken-reference)                 | The end-user's manager login.                                                     |
| **mfaEnabled**             |          | [Boolean](broken-reference)                | Indicates if the MFA is enabled for the end-user.                                 |
| **lastSignIn**             |          | [PublicUserSignInInfo](broken-reference)   | The last sign details for the end-user.                                           |
| **creationDate**           |          | [AWSDateTime](broken-reference)            | The creation date of the account across.                                          |
| **lastUpdated**            |          | [AWSDateTime](broken-reference)            | The last updated date of the account.                                             |

### PublicRiskyActivityCounts

| Field            | Argument | Type                               | Description |
| ---------------- | -------: | ---------------------------------- | ----------- |
| **total**        |          | [Int](broken-reference)!           |             |
| **levelOfTrust** |          | \[[LabelCount](broken-reference)!] |             |

### PublicScoreExplainabilitySummary

| Field                           | Argument | Type                                            | Description |
| ------------------------------- | -------: | ----------------------------------------------- | ----------- |
| **riskyActivityCounts**         |          | [PublicRiskyActivityCounts](broken-reference)!  |             |
| **combinedScoreExplainability** |          | \[[GroupExplainabilityItem](broken-reference)!] |             |

### PublicUserDevice

| Field           | Argument | Type                            | Description                                 |
| --------------- | -------: | ------------------------------- | ------------------------------------------- |
| **deviceId**    |          | [String](broken-reference)!     | The device ID.                              |
| **displayName** |          | [String](broken-reference)      | The device display name.                    |
| **os**          |          | [OsType](broken-reference)      | The device OS type.                         |
| **lastSeen**    |          | [AWSDateTime](broken-reference) | The last time the end-user used the device. |
| **deviceType**  |          | [DeviceType](broken-reference)  | The device type: access or authentication.  |
| **provider**    |          | [Provider](broken-reference)!   | The provider type.                          |

### PublicUserSignInInfo

| Field         | Argument | Type                             | Description                            |
| ------------- | -------: | -------------------------------- | -------------------------------------- |
| **timestamp** |          | [AWSDateTime](broken-reference)! | The end-user's sign-in timestamp.      |
| **result**    |          | [String](broken-reference)       | The end-user's sign-in result.         |
| **reason**    |          | [String](broken-reference)       | The end-user's sign-in failure reason. |
| **ipAddress** |          | [String](broken-reference)       | The end-user's sign-in IP address.     |
| **location**  |          | [GeoLocation](broken-reference)  | The end-user's sign-in location.       |

### TotalHits

| Field        | Argument | Type                        | Description |
| ------------ | -------: | --------------------------- | ----------- |
| **count**    |          | [Int](broken-reference)!    |             |
| **relation** |          | [String](broken-reference)! |             |

### TotalWithMedian

| Field      | Argument | Type                       | Description |
| ---------- | -------: | -------------------------- | ----------- |
| **total**  |          | [Int](broken-reference)!   |             |
| **median** |          | [Float](broken-reference)! |             |

### TypedKeyValuePair

| Field        | Argument | Type                        | Description |
| ------------ | -------: | --------------------------- | ----------- |
| **key**      |          | [String](broken-reference)! |             |
| **value**    |          | [String](broken-reference)! |             |
| **type**     |          | [String](broken-reference)  |             |
| **minValue** |          | [Int](broken-reference)     |             |
| **maxValue** |          | [Int](broken-reference)     |             |

## Inputs

### DailyScheduleInput

| Field      | Type | Description              |   |
| ---------- | ---- | ------------------------ | - |
| **hour**   |      | [Int](broken-reference)! |   |
| **minute** |      | [Int](broken-reference)! |   |

### ItemListInput

| Field        | Type | Description                     |   |
| ------------ | ---- | ------------------------------- | - |
| **listType** |      | [ListType](broken-reference)!   |   |
| **items**    |      | \[[String](broken-reference)!]! |   |

### KeyValuePairInput

| Field     | Type | Description                 |   |
| --------- | ---- | --------------------------- | - |
| **key**   |      | [String](broken-reference)! |   |
| **value** |      | [String](broken-reference)! |   |

### ListEndUsersInput

| Field       | Type | Description                     |   |
| ----------- | ---- | ------------------------------- | - |
| **orderBy** |      | \[[OrderBy](broken-reference)!] |   |

### OrderBy

| Field     | Type | Description                 |   |
| --------- | ---- | --------------------------- | - |
| **name**  |      | [String](broken-reference)! |   |
| **order** |      | [Order](broken-reference)   |   |

### RegisterWebhookWithApiKey

Input for registering a webhook with an API key.

| Field          | Type | Description                     |                                                                                                                    |
| -------------- | ---- | ------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **name**       |      | [String](broken-reference)!     | Part of the name of the webhook. The webhook name is a combination of the name and a random suffix for uniqueness. |
| **endpoint**   |      | [String](broken-reference)!     | The URL of the webhook endpoint.                                                                                   |
| **apiKeyName** |      | [String](broken-reference)!     | The name of the API key to use for the webhook. Sent in the webhook payload headers as the header name.            |
| **apiKey**     |      | [String](broken-reference)!     | The value of the API secret key to use for the webhook. Sent in the webhook payload headers as the header value.   |
| **checkIds**   |      | \[[String](broken-reference)!]! | The list of Cisco Identity Intelligence check IDs to subscribe to.                                                 |

### RegisterWebhookWithDuoSecurityClient

Input for registering a webhook with Duo Security Client.

| Field                        | Type | Description                     |                                                                                                      |
| ---------------------------- | ---- | ------------------------------- | ---------------------------------------------------------------------------------------------------- |
| **name**                     |      | [String](broken-reference)!     | Part of the name of the webhook. The webhook name is a combination of the name and a Webhook prefix. |
| **duoIntegrationInstanceId** |      | [String](broken-reference)!     | The ID of the existing Duo integration instance.                                                     |
| **checkIds**                 |      | \[[String](broken-reference)!]! | The list of Cisco Identity Intelligence check IDs to subscribe to.                                   |

### TimestampRange

| Field              | Type | Description                 |   |
| ------------------ | ---- | --------------------------- | - |
| **startTimestamp** |      | [String](broken-reference)! |   |
| **endTimestamp**   |      | [String](broken-reference)  |   |

## Enums

### ActivityResultType

| Value                | Description |
| -------------------- | ----------- |
| **SUCCESS**          |             |
| **PARTIAL\_SUCCESS** |             |
| **FAILURE**          |             |
| **TIMEOUT**          |             |
| **INFO**             |             |
| **STARTED**          |             |
| **BLOCKED**          |             |
| **NONE**             |             |

### DataType

| Value                           | Description |
| ------------------------------- | ----------- |
| **ADMINISTRATORS**              |             |
| **APPS**                        |             |
| **APPS\_TO\_GROUPS**            |             |
| **APPS\_TO\_USERS**             |             |
| **EVENT\_LOGS**                 |             |
| **AUDIT\_LOGS**                 |             |
| **ACTIVITY\_LOGS**              |             |
| **ADDITIONAL\_LOGS**            |             |
| **FACTORS\_TO\_USERS**          |             |
| **GROUPS**                      |             |
| **GROUP\_OWNERS**               |             |
| **GROUPS\_TO\_USERS**           |             |
| **DIRECT\_REPORTS**             |             |
| **DIRECTORY\_ROLES**            |             |
| **IDP**                         |             |
| **USERS**                       |             |
| **DEVICES**                     |             |
| **ORGANIZATION\_DEVICES**       |             |
| **NETWORK\_DEVICES**            |             |
| **NETWORK\_DEVICE\_GROUPS**     |             |
| **REGISTERED\_DEVICES**         |             |
| **OWNED\_DEVICES**              |             |
| **RISKY\_USERS**                |             |
| **RISKY\_USER\_EVENTS**         |             |
| **NAMED\_LOCATIONS**            |             |
| **IP\_CIDR\_LIST**              |             |
| **IP\_THREAT\_INSIGHTS**        |             |
| **POLICIES**                    |             |
| **POLICY\_RULES**               |             |
| **POLICY\_SUMMARY**             |             |
| **SERVICE\_PRINCIPAL**          |             |
| **API\_TOKEN**                  |             |
| **EVENT\_HUB**                  |             |
| **AUTHENTICATORS**              |             |
| **AUTHENTICATORS\_TO\_USERS**   |             |
| **SIGNIN\_LOGS**                |             |
| **LOGIN\_HISTORY**              |             |
| **LOGIN\_GEO**                  |             |
| **AUTH\_CONFIG**                |             |
| **USER\_LOGIN**                 |             |
| **END\_USER\_LOGINS**           |             |
| **PROFILES**                    |             |
| **CONDITIONAL\_ACCESS\_POLICY** |             |
| **PROVISIONING\_EVENTS**        |             |
| **ORGANIZATIONS**               |             |
| **USER\_EMAILS**                |             |
| **USER\_ENTERPRISE\_EMAILS**    |             |
| **COLLABORATORS**               |             |
| **MEMBER\_INVITATIONS**         |             |
| **COLLABORATOR\_INVITATIONS**   |             |
| **PERMISSION\_SETS**            |             |
| **USER\_SCHEMA**                |             |
| **MAILBOX\_SETTINGS**           |             |
| **MESSAGE\_RULES**              |             |
| **DEVICE\_AUDIT\_EVENTS**       |             |
| **AUTH\_API**                   |             |
| **ENDPOINTS**                   |             |
| **TOKENS**                      |             |
| **WEBAUTHNCREDENTIALS**         |             |
| **BYPASS\_CODES**               |             |
| **SIGNIN\_ACTIVITY**            |             |
| **SESSIONS**                    |             |
| **ROLES\_TO\_USERS**            |             |

### DeviceType

| Value              | Description |
| ------------------ | ----------- |
| **ACCESS**         |             |
| **AUTHENTICATION** |             |

### EndUserStatus

| Value                 | Description |
| --------------------- | ----------- |
| **ACTIVE**            |             |
| **INACTIVE**          |             |
| **DEPROVISIONED**     |             |
| **LOCKED\_OUT**       |             |
| **PASSWORD\_EXPIRED** |             |
| **PROVISIONED**       |             |
| **RECOVERY**          |             |
| **STAGED**            |             |
| **SUSPENDED**         |             |
| **INCONSISTENT**      |             |
| **DELETED**           |             |
| **DISABLED**          |             |
| **BLOCKED**           |             |
| **TRANSIENT**         |             |
| **UNKNOWN**           |             |
| **ENABLED**           |             |
| **DEACTIVATED**       |             |

### HttpMethod

| Value       | Description |
| ----------- | ----------- |
| **GET**     |             |
| **POST**    |             |
| **PUT**     |             |
| **HEAD**    |             |
| **OPTIONS** |             |
| **PATCH**   |             |
| **DELETE**  |             |

### LevelOfTrust

| Value            | Description |
| ---------------- | ----------- |
| **TRUSTED**      |             |
| **FAVORABLE**    |             |
| **NEUTRAL**      |             |
| **QUESTIONABLE** |             |
| **UNTRUSTED**    |             |
| **UNKNOWN**      |             |

### ListType

| Value       | Description |
| ----------- | ----------- |
| **allow**   |             |
| **block**   |             |
| **ignore**  |             |
| **include** |             |

### Order

| Value    | Description |
| -------- | ----------- |
| **asc**  |             |
| **desc** |             |

### OsType

| Value               | Description |
| ------------------- | ----------- |
| **WINDOWS**         |             |
| **WINDOWS\_MOBILE** |             |
| **MACOS**           |             |
| **IOS**             |             |
| **ANDROID**         |             |
| **LINUX**           |             |
| **CHROME\_OS**      |             |
| **UNKNOWN**         |             |

### Provider

| Value          | Description |
| -------------- | ----------- |
| **AUTH0**      |             |
| **AWS**        |             |
| **AZURE\_AD**  |             |
| **OKTA**       |             |
| **HRIS**       |             |
| **SLACK**      |             |
| **DUO**        |             |
| **G\_SUITE**   |             |
| **WORKDAY**    |             |
| **SALESFORCE** |             |
| **GIT\_HUB**   |             |
| **ISE**        |             |
| **WEBEX\_CI**  |             |

### TrustScoreGroupId

| Value                        | Description |
| ---------------------------- | ----------- |
| **ACCOUNT\_LOGIN\_BEHAVIOR** |             |
| **ACTIONS\_IN\_SESSION**     |             |
| **APPLICATION**              |             |
| **DEVICE**                   |             |
| **EXTERNAL\_THREAT**         |             |
| **FIRST\_FACTOR**            |             |
| **SECOND\_FACTOR**           |             |
| **NETWORK**                  |             |
| **PERMISSION**               |             |
| **SESSION**                  |             |
| **ACCOUNT\_VALIDITY**        |             |

### TrustScoreModelType

| Value           | Description |
| --------------- | ----------- |
| **NEW\_USER**   |             |
| **KNOWN\_USER** |             |

### TrustScoreVersion

| Value  | Description |
| ------ | ----------- |
| **V1** |             |

### TrustScoreWeight

| Value            | Description |
| ---------------- | ----------- |
| **NO\_RISK**     |             |
| **LOW\_RISK**    |             |
| **MEDIUM\_RISK** |             |
| **HIGH\_RISK**   |             |

### UserTypeClassification

| Value                     | Description |
| ------------------------- | ----------- |
| **INTERNAL**              |             |
| **EXTERNAL**              |             |
| **MISSING**               |             |
| **UNCLASSIFIED**          |             |
| **INCONSISTENT**          |             |
| **SERVICE\_ACCOUNT**      |             |
| **SHARED\_MAILBOX**       |             |
| **LINKED\_USER\_ACCOUNT** |             |
| **CONFERENCE\_ROOM**      |             |
| **EQUIPMENT\_MAILBOX**    |             |
| **OTHER\_MAILBOX**        |             |

### WorkflowState

| Value       | Description |
| ----------- | ----------- |
| **SUCCESS** |             |
| **ERROR**   |             |
| **UNKNOWN** |             |
| **RUNNING** |             |

## Scalars

### AWSDate

The AWSDate scalar type represents a valid extended ISO 8601 Date string. In other words, this scalar type accepts date strings of the form YYYY-MM-DD. This scalar type can also accept time zone offsets. For example, 1970-01-01Z, 1970-01-01-07:00 and 1970-01-01+05:30 are all valid dates. The time zone offset must either be Z (representing the UTC time zone) or be in the format ±hh:mm:ss. The seconds field in the timezone offset will be considered valid even though it is not part of the ISO 8601 standard.

### AWSDateTime

The AWSDateTime scalar type represents a valid extended ISO 8601 DateTime string. In other words, this scalar type accepts datetime strings of the form YYYY-MM-DDThh:mm:ss.sssZ. The field after the seconds field is a nanoseconds field. It can accept between 1 and 9 digits. The seconds and nanoseconds fields are optional (the seconds field must be specified if the nanoseconds field is to be used). The time zone offset is compulsory for this scalar. The time zone offset must either be Z (representing the UTC time zone) or be in the format ±hh:mm:ss. The seconds field in the timezone offset will be considered valid even though it is not part of the ISO 8601 standard.

### AWSEmail

The AWSEmail scalar type represents an Email address string that complies with RFC 822. For example, username@example.com is a valid Email address.

### AWSIPAddress

The AWSIPAddress scalar type represents a valid IPv4 or IPv6 address string.

### AWSJSON

The AWSJSON scalar type represents a JSON string that complies with RFC 8259.

Maps like {"upvotes": 10}, lists like \[1,2,3], and scalar values like "AWSJSON example string", 1, and true are accepted as valid JSON. They will automatically be parsed and loaded in the resolver mapping templates as Maps, Lists, or Scalar values rather than as the literal input strings. Invalid JSON strings like {a: 1}, {'a': 1} and Unquoted string will throw GraphQL validation errors.

### AWSPhone

The AWSPhone scalar type represents a valid Phone Number. Phone numbers are serialized and deserialized as Strings. Phone numbers provided may be whitespace delimited or hyphenated. The number can specify a country code at the beginning but this is not required.

### AWSTime

The AWSTime scalar type represents a valid extended ISO 8601 Time string. In other words, this scalar type accepts time strings of the form hh:mm:ss.sss. The field after the seconds field is a nanoseconds field. It can accept between 1 and 9 digits. The seconds and nanoseconds fields are optional (the seconds field must be specified if the nanoseconds field is to be used). This scalar type can also accept time zone offsets.

For example, 12:30Z, 12:30:24-07:00 and 12:30:24.500+05:30 are all valid time strings.

The time zone offset must either be Z (representing the UTC time zone) or be in the format hh:mm:ss. The seconds field in the timezone offset will be considered valid even though it is not part of the ISO 8601 standard.

### AWSTimestamp

The AWSTimestamp scalar type represents the number of seconds that have elapsed since 1970-01-01T00:00Z. Timestamps are serialized and deserialized as numbers. Negative values are also accepted and these represent the number of seconds till 1970-01-01T00:00Z.

### AWSURL

The AWSURL scalar type represents a valid URL string. The URL may use any scheme and may also be a local URL (Ex: [http://localhost/](http://localhost/)). URLs without schemes are considered invalid. URLs which contain double slashes are also considered invalid.

### Boolean

The `Boolean` scalar type represents `true` or `false`.

### Float

The `Float` scalar type represents signed double-precision fractional values as specified by [IEEE 754](https://en.wikipedia.org/wiki/IEEE\_floating\_point).

### ID

The `ID` scalar type represents a unique identifier, often used to refetch an object or as key for a cache. The ID type appears in a JSON response as a String; however, it is not intended to be human-readable. When expected as an input type, any string (such as `"4"`) or integer (such as `4`) input value will be accepted as an ID.

### Int

The `Int` scalar type represents non-fractional signed whole numeric values. Int can represent values between -(2^31) and 2^31 - 1.

### String

The `String` scalar type represents textual data, represented as UTF-8 character sequences. The String type is most often used by GraphQL to represent free-form human-readable text.
