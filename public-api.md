# Schema Types

<details>
  <summary><strong>Table of Contents</strong></summary>

  * [Query]<a href='#query'>
  * <a href='#query'>
  * [Mutation](#mutation)
  * [link text](#query)
    * [AdminLogin](#adminlogin)
    * [ConnectivityStatus](#connectivitystatus)
    * [DailyCheckCount](#dailycheckcount)
    * [DailySchedule](#dailyschedule)
    * [EndUserRef](#enduserref)
    * [EndUserState](#enduserstate)
    * [FeatureExplainabilityItem](#featureexplainabilityitem)
    * [GeoCoordinates](#geocoordinates)
    * [GeoLocation](#geolocation)
    * [GetEndUserOutput](#getenduseroutput)
    * [GetEndUsersByIpConnection](#getendusersbyipconnection)
    * [GroupExplainabilityItem](#groupexplainabilityitem)
    * [IpAddressInfo](#ipaddressinfo)
    * [ItemList](#itemlist)
    * [KeyValuePair](#keyvaluepair)
    * [LabelCount](#labelcount)
    * [ListAdminLoginsConnection](#listadminloginsconnection)
    * [ListEndUsersConnection](#listendusersconnection)
    * [LocationWithPrevalence](#locationwithprevalence)
    * [PublicEndUser](#publicenduser)
    * [PublicEndUserDetails](#publicenduserdetails)
    * [PublicEndUserTrustScore](#publicendusertrustscore)
    * [PublicIntegrationStatus](#publicintegrationstatus)
    * [PublicProviderEndUserDetails](#publicproviderenduserdetails)
    * [PublicRiskyActivityCounts](#publicriskyactivitycounts)
    * [PublicScoreExplainabilitySummary](#publicscoreexplainabilitysummary)
    * [PublicUserDevice](#publicuserdevice)
    * [PublicUserSignInInfo](#publicusersignininfo)
    * [TotalHits](#totalhits)
    * [TotalWithMedian](#totalwithmedian)
    * [TypedKeyValuePair](#typedkeyvaluepair)
  * [Inputs](#inputs)
    * [DailyScheduleInput](#dailyscheduleinput)
    * [ItemListInput](#itemlistinput)
    * [KeyValuePairInput](#keyvaluepairinput)
    * [ListEndUsersInput](#listendusersinput)
    * [OrderBy](#orderby)
    * [RegisterWebhookWithApiKey](#registerwebhookwithapikey)
    * [RegisterWebhookWithDuoSecurityClient](#registerwebhookwithduosecurityclient)
    * [TimestampRange](#timestamprange)
  * [Enums](#enums)
    * [ActivityResultType](#activityresulttype)
    * [DataType](#datatype)
    * [DeviceType](#devicetype)
    * [EndUserStatus](#enduserstatus)
    * [HttpMethod](#httpmethod)
    * [LevelOfTrust](#leveloftrust)
    * [ListType](#listtype)
    * [Order](#order)
    * [OsType](#ostype)
    * [Provider](#provider)
    * [TrustScoreGroupId](#trustscoregroupid)
    * [TrustScoreModelType](#trustscoremodeltype)
    * [TrustScoreVersion](#trustscoreversion)
    * [TrustScoreWeight](#trustscoreweight)
    * [UserTypeClassification](#usertypeclassification)
    * [WorkflowState](#workflowstate)
  * [Scalars](#scalars)
    * [AWSDate](#awsdate)
    * [AWSDateTime](#awsdatetime)
    * [AWSEmail](#awsemail)
    * [AWSIPAddress](#awsipaddress)
    * [AWSJSON](#awsjson)
    * [AWSPhone](#awsphone)
    * [AWSTime](#awstime)
    * [AWSTimestamp](#awstimestamp)
    * [AWSURL](#awsurl)
    * [Boolean](#boolean)
    * [Float](#float)
    * [ID](#id)
    * [Int](#int)
    * [String](#string)

</details>

## Query
<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>ping</strong></td><td></td>
<td valign="top"><a href="#boolean">Boolean</a>!</td>
<td>

Ping the API to check if it is up and running.

</td>
</tr>
<tr>
<td valign="top"><strong>getEndUserState</strong></td><td></td>
<td valign="top"><a href="#enduserstate">EndUserState</a>!</td>
<td>

Fetch a concise summary of end-user information, including key fields and relevant details.
Use this query when you want to get a basic end-user digest.

</td>
</tr>
<tr>
<td></td><td valign="top">login</td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

End-user's email address.

</td>
</tr>
<tr>
<td valign="top"><strong>getEndUsersByIp</strong></td><td></td>
<td valign="top"><a href="#getendusersbyipconnection">GetEndUsersByIpConnection</a>!</td>
<td>

Retrieve end-users associated with a specified IP address.

</td>
</tr>
<tr>
<td></td><td valign="top">ipAddress</td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

IP Address.

</td>
</tr>
<tr>
<td></td><td valign="top">pageSize</td>
<td valign="top"><a href="#int">Int</a></td>
<td>

Number of items per page. Default pageSize is 50. Max pageSize is 1000.

</td>
</tr>
<tr>
<td></td><td valign="top">pageToken</td>
<td valign="top"><a href="#string">String</a></td>
<td>

Token for paginating through the result set.

</td>
</tr>
<tr>
<td valign="top"><strong>getEndUser</strong></td><td></td>
<td valign="top"><a href="#getenduseroutput">GetEndUserOutput</a>!</td>
<td>

Fetch end-user's detailed information, including including devices, integrations, factors and more.
Use this query when you want to get a comprehensive end-user details.

</td>
</tr>
<tr>
<td></td><td valign="top">login</td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

End-user's email address.

</td>
</tr>
<tr>
<td valign="top"><strong>listEndUsers</strong></td><td></td>
<td valign="top"><a href="#listendusersconnection">ListEndUsersConnection</a>!</td>
<td>

Fetch the list of end-users.
Use this query to retrieve a large number of items using paging.
The default page size is 100, and the maximum page size is 1000.
Page token is used to retrieve the next page. If not provided, the first page is retrieved.

</td>
</tr>
<tr>
<td></td><td valign="top">input</td>
<td valign="top"><a href="#listendusersinput">ListEndUsersInput</a>!</td>
<td>

Input data end-users listing.

</td>
</tr>
<tr>
<td></td><td valign="top">pageSize</td>
<td valign="top"><a href="#int">Int</a></td>
<td>

Number of items per page. Default pageSize is 100. Max pageSize is 500.

</td>
</tr>
<tr>
<td></td><td valign="top">pageToken</td>
<td valign="top"><a href="#string">String</a></td>
<td>

Token for paginating through the result set.

</td>
</tr>
<tr>
<td valign="top"><strong>getTotalCheckFailingCounts</strong></td><td></td>
<td valign="top">[<a href="#dailycheckcount">DailyCheckCount</a>!]!</td>
<td>

Experimental API for PoC purposes.

</td>
</tr>
<tr>
<td valign="top"><strong>listAdminLogins</strong></td><td></td>
<td valign="top"><a href="#listadminloginsconnection">ListAdminLoginsConnection</a>!</td>
<td></td>
</tr>
<tr>
<td></td><td valign="top">pageSize</td>
<td valign="top"><a href="#int">Int</a></td>
<td></td>
</tr>
<tr>
<td></td><td valign="top">pageToken</td>
<td valign="top"><a href="#string">String</a></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>getIntegrationsStatus</strong></td><td></td>
<td valign="top">[<a href="#publicintegrationstatus">PublicIntegrationStatus</a>!]!</td>
<td></td>
</tr>
</tbody>
</table>

## Mutation
<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>registerWebhookWithApiKey</strong></td><td></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

Register a Webhook Notification Target with an API key as a target for Failed Check findings.
See more at [https://docs.oort.io/integrations/webhooks](https://docs.oort.io/integrations/webhooks)

</td>
</tr>
<tr>
<td></td><td valign="top">input</td>
<td valign="top"><a href="#registerwebhookwithapikey">RegisterWebhookWithApiKey</a>!</td>
<td>

Input data for registering a webhook with an API key.

</td>
</tr>
<tr>
<td valign="top"><strong>registerWebhookWithDuoSecurityClient</strong></td><td></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

Register a Webhook Notification Target with Duo Secret Client as a target for Failed Check findings.

</td>
</tr>
<tr>
<td></td><td valign="top">input</td>
<td valign="top"><a href="#registerwebhookwithduosecurityclient">RegisterWebhookWithDuoSecurityClient</a>!</td>
<td>

Input data for registering a webhook with Duo Security Client.

</td>
</tr>
<tr>
<td valign="top"><strong>unregisterWebhook</strong></td><td></td>
<td valign="top"><a href="#boolean">Boolean</a>!</td>
<td>

Unregister a Webhook Notification Target.

</td>
</tr>
<tr>
<td></td><td valign="top">id</td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

ID of the webhook to unregister.

</td>
</tr>
</tbody>
</table>

## Objects

### AdminLogin

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>login</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>displayName</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>lastSignIn</strong></td><td></td>
<td valign="top"><a href="#publicusersignininfo">PublicUserSignInInfo</a></td>
<td></td>
</tr>
</tbody>
</table>

### ConnectivityStatus

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>statusCode</strong></td><td></td>
<td valign="top"><a href="#int">Int</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>payload</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>reason</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td></td>
</tr>
</tbody>
</table>

### DailyCheckCount

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>day</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>total</strong></td><td></td>
<td valign="top"><a href="#int">Int</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### DailySchedule

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>hour</strong></td><td></td>
<td valign="top"><a href="#int">Int</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>minute</strong></td><td></td>
<td valign="top"><a href="#int">Int</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### EndUserRef

Represents a reference to an end-user.

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>id</strong></td><td></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

The end-user ID in Cisco Identity Intelligence.

</td>
</tr>
<tr>
<td valign="top"><strong>displayName</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The end-user's display name.

</td>
</tr>
<tr>
<td valign="top"><strong>login</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

End-user's email address.

</td>
</tr>
<tr>
<td valign="top"><strong>referenceUrl</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

End-user's URL in Cisco Identity Intelligence.

</td>
</tr>
</tbody>
</table>

### EndUserState

Represents a concise summary of end-user information, including key fields and relevant details.

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>id</strong></td><td></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

The end-user ID in Cisco Identity Intelligence.

</td>
</tr>
<tr>
<td valign="top"><strong>displayName</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The end-user's display name.

</td>
</tr>
<tr>
<td valign="top"><strong>login</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

End-user's email address.

</td>
</tr>
<tr>
<td valign="top"><strong>employeeId</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

List of employee IDs associated with the end-user in the Identity Provider and HR systems.

</td>
</tr>
<tr>
<td valign="top"><strong>status</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The aggregated end-user status in the identity providers.

</td>
</tr>
<tr>
<td valign="top"><strong>userTypeClassification</strong></td><td></td>
<td valign="top"><a href="#usertypeclassification">UserTypeClassification</a></td>
<td>

The end-user classification in Cisco Identity Intelligence.

</td>
</tr>
<tr>
<td valign="top"><strong>managerLogin</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

End-user's manager email address.

</td>
</tr>
<tr>
<td valign="top"><strong>ipAddresses</strong></td><td></td>
<td valign="top">[<a href="#ipaddressinfo">IpAddressInfo</a>!]</td>
<td>

List of IP Addresses used by the end-user.

</td>
</tr>
<tr>
<td valign="top"><strong>lastSignInLocation</strong></td><td></td>
<td valign="top"><a href="#geolocation">GeoLocation</a></td>
<td>

Deprecated. Do not use!

</td>
</tr>
<tr>
<td valign="top"><strong>phoneNumber</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

End-user's phone number.

</td>
</tr>
<tr>
<td valign="top"><strong>unusedApplications</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

Names of applications the end-user has access and did not access in the past 30 days.

</td>
</tr>
<tr>
<td valign="top"><strong>usedApplications</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

Names of applications the end-user has access and accessed in the past 30 days.

</td>
</tr>
<tr>
<td valign="top"><strong>usedFactors</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

Authentication factors used by the end-user.

</td>
</tr>
<tr>
<td valign="top"><strong>referenceUrl</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

End-user's URL in Cisco Identity Intelligence.

</td>
</tr>
<tr>
<td valign="top"><strong>registeredLocationDetails</strong></td><td></td>
<td valign="top"><a href="#geolocation">GeoLocation</a></td>
<td>

The end-user's registered location

</td>
</tr>
<tr>
<td valign="top"><strong>workingLocationDetails</strong></td><td></td>
<td valign="top">[<a href="#locationwithprevalence">LocationWithPrevalence</a>!]</td>
<td>

List of the locations the end-user works in.

</td>
</tr>
</tbody>
</table>

### FeatureExplainabilityItem

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>featureId</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>details</strong></td><td></td>
<td valign="top">[<a href="#keyvaluepair">KeyValuePair</a>!]</td>
<td></td>
</tr>
</tbody>
</table>

### GeoCoordinates

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>latitude</strong></td><td></td>
<td valign="top"><a href="#float">Float</a></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>longitude</strong></td><td></td>
<td valign="top"><a href="#float">Float</a></td>
<td></td>
</tr>
</tbody>
</table>

### GeoLocation

IP Address geolocation information.

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>city</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The city name.

</td>
</tr>
<tr>
<td valign="top"><strong>state</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The state name.

</td>
</tr>
<tr>
<td valign="top"><strong>country</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

two-letter country code defined in ISO 3166-1.

</td>
</tr>
</tbody>
</table>

### GetEndUserOutput

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>endUserDetails</strong></td><td></td>
<td valign="top"><a href="#publicenduserdetails">PublicEndUserDetails</a>!</td>
<td>

The unified end-user details across all providers.

</td>
</tr>
<tr>
<td valign="top"><strong>providerEndUserDetails</strong></td><td></td>
<td valign="top">[<a href="#publicproviderenduserdetails">PublicProviderEndUserDetails</a>!]!</td>
<td>

The array of end-user details by provider.

</td>
</tr>
</tbody>
</table>

### GetEndUsersByIpConnection

End-users associated with a specified IP address.

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>items</strong></td><td></td>
<td valign="top">[<a href="#enduserref">EndUserRef</a>!]!</td>
<td>

Itemized list of end-users associated with a specified IP address.

</td>
</tr>
<tr>
<td valign="top"><strong>pageToken</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

Token for paginating through the result set. If pageToken is undefined, there are no more results to fetch.

</td>
</tr>
</tbody>
</table>

### GroupExplainabilityItem

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>groupId</strong></td><td></td>
<td valign="top"><a href="#trustscoregroupid">TrustScoreGroupId</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>severity</strong></td><td></td>
<td valign="top"><a href="#int">Int</a></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>weight</strong></td><td></td>
<td valign="top"><a href="#trustscoreweight">TrustScoreWeight</a></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>details</strong></td><td></td>
<td valign="top">[<a href="#featureexplainabilityitem">FeatureExplainabilityItem</a>!]</td>
<td></td>
</tr>
</tbody>
</table>

### IpAddressInfo

IP Address information.

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>ipAddress</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

IP Address.

</td>
</tr>
<tr>
<td valign="top"><strong>location</strong></td><td></td>
<td valign="top"><a href="#geolocation">GeoLocation</a></td>
<td>

IP Address geolocation information.

</td>
</tr>
</tbody>
</table>

### ItemList

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>listType</strong></td><td></td>
<td valign="top"><a href="#listtype">ListType</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>items</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]!</td>
<td></td>
</tr>
</tbody>
</table>

### KeyValuePair

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>key</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>value</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### LabelCount

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>value</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>count</strong></td><td></td>
<td valign="top"><a href="#int">Int</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### ListAdminLoginsConnection

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>items</strong></td><td></td>
<td valign="top">[<a href="#adminlogin">AdminLogin</a>!]!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>pageToken</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td></td>
</tr>
</tbody>
</table>

### ListEndUsersConnection

End-users list.

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>items</strong></td><td></td>
<td valign="top">[<a href="#publicenduser">PublicEndUser</a>!]!</td>
<td>

Itemized list of end-users.

</td>
</tr>
<tr>
<td valign="top"><strong>pageToken</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

Token for paginating through the result set. If pageToken is undefined, there are no more results to fetch.

</td>
</tr>
</tbody>
</table>

### LocationWithPrevalence

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>location</strong></td><td></td>
<td valign="top"><a href="#geolocation">GeoLocation</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>userLocationPrevalence</strong></td><td></td>
<td valign="top"><a href="#float">Float</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### PublicEndUser

Represents end-user basic data.

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>id</strong></td><td></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

The end-user ID in Cisco Identity Intelligence.

</td>
</tr>
<tr>
<td valign="top"><strong>displayName</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The end-user's display name.

</td>
</tr>
<tr>
<td valign="top"><strong>login</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

End-user's login.

</td>
</tr>
<tr>
<td valign="top"><strong>emails</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

List of end-user emails associated with the end-user in the Identity Provider and HR systems.

</td>
</tr>
<tr>
<td valign="top"><strong>status</strong></td><td></td>
<td valign="top"><a href="#enduserstatus">EndUserStatus</a></td>
<td>

The unified status of the end-user across all providers.

</td>
</tr>
<tr>
<td valign="top"><strong>company</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The company the end-user belongs to.

</td>
</tr>
<tr>
<td valign="top"><strong>department</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The department the end-user belongs to.

</td>
</tr>
<tr>
<td valign="top"><strong>title</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The end-user's title.

</td>
</tr>
<tr>
<td valign="top"><strong>userTypeClassification</strong></td><td></td>
<td valign="top"><a href="#usertypeclassification">UserTypeClassification</a></td>
<td>

The unified classification of the end-user type across all providers.

</td>
</tr>
<tr>
<td valign="top"><strong>employeeIds</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

List of employee IDs associated with the end-user in the Identity Provider and HR systems.

</td>
</tr>
<tr>
<td valign="top"><strong>linkedEndUserLogins</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

List of linked end-users' logins.

</td>
</tr>
<tr>
<td valign="top"><strong>groupNames</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

List of names of the groups the end-user is a member of. Maximum 10 items.

</td>
</tr>
<tr>
<td valign="top"><strong>hasMoreGroups</strong></td><td></td>
<td valign="top"><a href="#boolean">Boolean</a>!</td>
<td>

The indication if more groups exist for the end-user.

</td>
</tr>
<tr>
<td valign="top"><strong>phoneNumbers</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

The end-user's phone numbers used for authentication.

</td>
</tr>
<tr>
<td valign="top"><strong>managerLogin</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The end-user's manager login.

</td>
</tr>
<tr>
<td valign="top"><strong>devices</strong></td><td></td>
<td valign="top">[<a href="#publicuserdevice">PublicUserDevice</a>!]</td>
<td>

List of devices the end-user uses.

</td>
</tr>
<tr>
<td valign="top"><strong>mfaEnabled</strong></td><td></td>
<td valign="top"><a href="#boolean">Boolean</a></td>
<td>

Indicates if the MFA is enabled for the end-user.

</td>
</tr>
<tr>
<td valign="top"><strong>lastSignIn</strong></td><td></td>
<td valign="top"><a href="#publicusersignininfo">PublicUserSignInInfo</a></td>
<td>

The last sign details for the end-user.

</td>
</tr>
<tr>
<td valign="top"><strong>lastActive</strong></td><td></td>
<td valign="top"><a href="#awsdatetime">AWSDateTime</a></td>
<td>

The last active timestamp for the end-user.

</td>
</tr>
<tr>
<td valign="top"><strong>failingChecks</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

The checks that the end-user has failed.

</td>
</tr>
<tr>
<td valign="top"><strong>firstCreatedDate</strong></td><td></td>
<td valign="top"><a href="#awsdatetime">AWSDateTime</a></td>
<td>

The first created date of the account across all providers.

</td>
</tr>
<tr>
<td valign="top"><strong>providers</strong></td><td></td>
<td valign="top">[<a href="#provider">Provider</a>!]!</td>
<td>

List of provider types for the integrations the end-user data is collected from.

</td>
</tr>
<tr>
<td valign="top"><strong>referenceUrl</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

End-user's URL in Cisco Identity Intelligence.

</td>
</tr>
<tr>
<td valign="top"><strong>endUserTrustScore</strong></td><td></td>
<td valign="top"><a href="#publicendusertrustscore">PublicEndUserTrustScore</a></td>
<td>

The end user trust score

</td>
</tr>
</tbody>
</table>

### PublicEndUserDetails

Represents end-user data.

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>id</strong></td><td></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

The end-user ID in Cisco Identity Intelligence.

</td>
</tr>
<tr>
<td valign="top"><strong>displayName</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The end-user's display name.

</td>
</tr>
<tr>
<td valign="top"><strong>login</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

End-user's email address.

</td>
</tr>
<tr>
<td valign="top"><strong>status</strong></td><td></td>
<td valign="top"><a href="#enduserstatus">EndUserStatus</a>!</td>
<td>

The unified status of the end-user across all providers.

</td>
</tr>
<tr>
<td valign="top"><strong>userIds</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

List of end-user IDs associated with the end-user in the Identity Provider and HR systems.

</td>
</tr>
<tr>
<td valign="top"><strong>emails</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

List of end-user emails associated with the end-user in the Identity Provider and HR systems.

</td>
</tr>
<tr>
<td valign="top"><strong>company</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The company the end-user belongs to.

</td>
</tr>
<tr>
<td valign="top"><strong>department</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The department the end-user belongs to.

</td>
</tr>
<tr>
<td valign="top"><strong>title</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The end-user's title.

</td>
</tr>
<tr>
<td valign="top"><strong>userTypeClassification</strong></td><td></td>
<td valign="top"><a href="#usertypeclassification">UserTypeClassification</a></td>
<td>

The unified classification of the end-user type across all providers.

</td>
</tr>
<tr>
<td valign="top"><strong>employeeIds</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

List of employee IDs associated with the end-user in the Identity Provider and HR systems.

</td>
</tr>
<tr>
<td valign="top"><strong>linkedEndUserLogins</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

List of linked end-users' logins.

</td>
</tr>
<tr>
<td valign="top"><strong>groupNames</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

List of names of the groups the end-user is a member of.

</td>
</tr>
<tr>
<td valign="top"><strong>phoneNumbers</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

The end-user's phone numbers used for authentication.

</td>
</tr>
<tr>
<td valign="top"><strong>managerLogin</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The end-user's manager login.

</td>
</tr>
<tr>
<td valign="top"><strong>devices</strong></td><td></td>
<td valign="top">[<a href="#publicuserdevice">PublicUserDevice</a>!]</td>
<td>

List of devices the end-user uses.

</td>
</tr>
<tr>
<td valign="top"><strong>mfaEnabled</strong></td><td></td>
<td valign="top"><a href="#boolean">Boolean</a></td>
<td>

Indicates if the MFA is enabled for the end-user.

</td>
</tr>
<tr>
<td valign="top"><strong>lastSignIn</strong></td><td></td>
<td valign="top"><a href="#publicusersignininfo">PublicUserSignInInfo</a></td>
<td>

The last sign details for the end-user.

</td>
</tr>
<tr>
<td valign="top"><strong>lastActive</strong></td><td></td>
<td valign="top"><a href="#awsdatetime">AWSDateTime</a></td>
<td>

The last active timestamp for the end-user.

</td>
</tr>
<tr>
<td valign="top"><strong>firstCreatedDate</strong></td><td></td>
<td valign="top"><a href="#awsdatetime">AWSDateTime</a></td>
<td>

The first created date of the account across all providers.

</td>
</tr>
<tr>
<td valign="top"><strong>failingChecks</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

The checks that the end-user has failed.

</td>
</tr>
<tr>
<td valign="top"><strong>referenceUrl</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

End-user's URL in Cisco Identity Intelligence.

</td>
</tr>
</tbody>
</table>

### PublicEndUserTrustScore

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>levelOfTrust</strong></td><td></td>
<td valign="top"><a href="#leveloftrust">LevelOfTrust</a>!</td>
<td>

The end user's level of trust

</td>
</tr>
<tr>
<td valign="top"><strong>scoreExplainabilitySummary</strong></td><td></td>
<td valign="top"><a href="#publicscoreexplainabilitysummary">PublicScoreExplainabilitySummary</a></td>
<td>

Score explainability summary

</td>
</tr>
</tbody>
</table>

### PublicIntegrationStatus

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>integrationId</strong></td><td></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>integrationName</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>status</strong></td><td></td>
<td valign="top"><a href="#activityresulttype">ActivityResultType</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>date</strong></td><td></td>
<td valign="top"><a href="#awsdatetime">AWSDateTime</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>error</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td></td>
</tr>
</tbody>
</table>

### PublicProviderEndUserDetails

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>userId</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The end-user userId.

</td>
</tr>
<tr>
<td valign="top"><strong>provider</strong></td><td></td>
<td valign="top"><a href="#provider">Provider</a>!</td>
<td>

The type of the provider.

</td>
</tr>
<tr>
<td valign="top"><strong>firstName</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The end-user's first name.

</td>
</tr>
<tr>
<td valign="top"><strong>lastName</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The end-user's last name.

</td>
</tr>
<tr>
<td valign="top"><strong>displayName</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The end-user's display name.

</td>
</tr>
<tr>
<td valign="top"><strong>login</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

End-user's email address.

</td>
</tr>
<tr>
<td valign="top"><strong>email</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

End-user primary email address.

</td>
</tr>
<tr>
<td valign="top"><strong>status</strong></td><td></td>
<td valign="top"><a href="#enduserstatus">EndUserStatus</a>!</td>
<td>

The unified status of the end-user across all providers.

</td>
</tr>
<tr>
<td valign="top"><strong>company</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The company the end-user belongs to.

</td>
</tr>
<tr>
<td valign="top"><strong>department</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The department the end-user belongs to.

</td>
</tr>
<tr>
<td valign="top"><strong>title</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The end-user's title.

</td>
</tr>
<tr>
<td valign="top"><strong>userTypeClassification</strong></td><td></td>
<td valign="top"><a href="#usertypeclassification">UserTypeClassification</a></td>
<td>

The unified classification of the end-user type across all providers.

</td>
</tr>
<tr>
<td valign="top"><strong>employeeId</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

Employee ID associated with the end-user in the Identity Provider and HR systems.

</td>
</tr>
<tr>
<td valign="top"><strong>managerLogin</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The end-user's manager login.

</td>
</tr>
<tr>
<td valign="top"><strong>mfaEnabled</strong></td><td></td>
<td valign="top"><a href="#boolean">Boolean</a></td>
<td>

Indicates if the MFA is enabled for the end-user.

</td>
</tr>
<tr>
<td valign="top"><strong>lastSignIn</strong></td><td></td>
<td valign="top"><a href="#publicusersignininfo">PublicUserSignInInfo</a></td>
<td>

The last sign details for the end-user.

</td>
</tr>
<tr>
<td valign="top"><strong>creationDate</strong></td><td></td>
<td valign="top"><a href="#awsdatetime">AWSDateTime</a></td>
<td>

The creation date of the account across.

</td>
</tr>
<tr>
<td valign="top"><strong>lastUpdated</strong></td><td></td>
<td valign="top"><a href="#awsdatetime">AWSDateTime</a></td>
<td>

The last updated date of the account.

</td>
</tr>
</tbody>
</table>

### PublicRiskyActivityCounts

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>total</strong></td><td></td>
<td valign="top"><a href="#int">Int</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>levelOfTrust</strong></td><td></td>
<td valign="top">[<a href="#labelcount">LabelCount</a>!]</td>
<td></td>
</tr>
</tbody>
</table>

### PublicScoreExplainabilitySummary

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>riskyActivityCounts</strong></td><td></td>
<td valign="top"><a href="#publicriskyactivitycounts">PublicRiskyActivityCounts</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>combinedScoreExplainability</strong></td><td></td>
<td valign="top">[<a href="#groupexplainabilityitem">GroupExplainabilityItem</a>!]</td>
<td></td>
</tr>
</tbody>
</table>

### PublicUserDevice

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>deviceId</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The device ID.

</td>
</tr>
<tr>
<td valign="top"><strong>displayName</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The device display name.

</td>
</tr>
<tr>
<td valign="top"><strong>os</strong></td><td></td>
<td valign="top"><a href="#ostype">OsType</a></td>
<td>

The device OS type.

</td>
</tr>
<tr>
<td valign="top"><strong>lastSeen</strong></td><td></td>
<td valign="top"><a href="#awsdatetime">AWSDateTime</a></td>
<td>

The last time the end-user used the device.

</td>
</tr>
<tr>
<td valign="top"><strong>deviceType</strong></td><td></td>
<td valign="top"><a href="#devicetype">DeviceType</a></td>
<td>

The device type: access or authentication.

</td>
</tr>
<tr>
<td valign="top"><strong>provider</strong></td><td></td>
<td valign="top"><a href="#provider">Provider</a>!</td>
<td>

The provider type.

</td>
</tr>
</tbody>
</table>

### PublicUserSignInInfo

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>timestamp</strong></td><td></td>
<td valign="top"><a href="#awsdatetime">AWSDateTime</a>!</td>
<td>

The end-user's sign-in timestamp.

</td>
</tr>
<tr>
<td valign="top"><strong>result</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The end-user's sign-in result.

</td>
</tr>
<tr>
<td valign="top"><strong>reason</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The end-user's sign-in failure reason.

</td>
</tr>
<tr>
<td valign="top"><strong>ipAddress</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The end-user's sign-in IP address.

</td>
</tr>
<tr>
<td valign="top"><strong>location</strong></td><td></td>
<td valign="top"><a href="#geolocation">GeoLocation</a></td>
<td>

The end-user's sign-in location.

</td>
</tr>
</tbody>
</table>

### TotalHits

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>count</strong></td><td></td>
<td valign="top"><a href="#int">Int</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>relation</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### TotalWithMedian

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>total</strong></td><td></td>
<td valign="top"><a href="#int">Int</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>median</strong></td><td></td>
<td valign="top"><a href="#float">Float</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### TypedKeyValuePair

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>key</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>value</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>type</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>minValue</strong></td><td></td>
<td valign="top"><a href="#int">Int</a></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>maxValue</strong></td><td></td>
<td valign="top"><a href="#int">Int</a></td>
<td></td>
</tr>
</tbody>
</table>

## Inputs

### DailyScheduleInput

<table>
<thead>
<tr>
<th colspan="2" align="left">Field</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>hour</strong></td><td></td>
<td valign="top"><a href="#int">Int</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>minute</strong></td><td></td>
<td valign="top"><a href="#int">Int</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### ItemListInput

<table>
<thead>
<tr>
<th colspan="2" align="left">Field</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>listType</strong></td><td></td>
<td valign="top"><a href="#listtype">ListType</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>items</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]!</td>
<td></td>
</tr>
</tbody>
</table>

### KeyValuePairInput

<table>
<thead>
<tr>
<th colspan="2" align="left">Field</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>key</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>value</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### ListEndUsersInput

<table>
<thead>
<tr>
<th colspan="2" align="left">Field</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>orderBy</strong></td><td></td>
<td valign="top">[<a href="#orderby">OrderBy</a>!]</td>
<td></td>
</tr>
</tbody>
</table>

### OrderBy

<table>
<thead>
<tr>
<th colspan="2" align="left">Field</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>name</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>order</strong></td><td></td>
<td valign="top"><a href="#order">Order</a></td>
<td></td>
</tr>
</tbody>
</table>

### RegisterWebhookWithApiKey

Input for registering a webhook with an API key.

<table>
<thead>
<tr>
<th colspan="2" align="left">Field</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>name</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

Part of the name of the webhook. The webhook name is a combination of the name and a random suffix for uniqueness.

</td>
</tr>
<tr>
<td valign="top"><strong>endpoint</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The URL of the webhook endpoint.

</td>
</tr>
<tr>
<td valign="top"><strong>apiKeyName</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The name of the API key to use for the webhook. Sent in the webhook payload headers as the header name.

</td>
</tr>
<tr>
<td valign="top"><strong>apiKey</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The value of the API secret key to use for the webhook. Sent in the webhook payload headers as the header value.

</td>
</tr>
<tr>
<td valign="top"><strong>checkIds</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]!</td>
<td>

The list of Cisco Identity Intelligence check IDs to subscribe to.

</td>
</tr>
</tbody>
</table>

### RegisterWebhookWithDuoSecurityClient

Input for registering a webhook with Duo Security Client.

<table>
<thead>
<tr>
<th colspan="2" align="left">Field</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>name</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

Part of the name of the webhook. The webhook name is a combination of the name and a Webhook prefix.

</td>
</tr>
<tr>
<td valign="top"><strong>duoIntegrationInstanceId</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The ID of the existing Duo integration instance.

</td>
</tr>
<tr>
<td valign="top"><strong>checkIds</strong></td><td></td>
<td valign="top">[<a href="#string">String</a>!]!</td>
<td>

The list of Cisco Identity Intelligence check IDs to subscribe to.

</td>
</tr>
</tbody>
</table>

### TimestampRange

<table>
<thead>
<tr>
<th colspan="2" align="left">Field</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td valign="top"><strong>startTimestamp</strong></td><td></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>endTimestamp</strong></td><td></td>
<td valign="top"><a href="#string">String</a></td>
<td></td>
</tr>
</tbody>
</table>

## Enums

### ActivityResultType

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>SUCCESS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>PARTIAL_SUCCESS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>FAILURE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>TIMEOUT</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>INFO</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>STARTED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>BLOCKED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>NONE</strong></td>
<td></td>
</tr>
</tbody>
</table>

### DataType

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>ADMINISTRATORS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>APPS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>APPS_TO_GROUPS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>APPS_TO_USERS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>EVENT_LOGS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>AUDIT_LOGS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ACTIVITY_LOGS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ADDITIONAL_LOGS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>FACTORS_TO_USERS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>GROUPS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>GROUP_OWNERS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>GROUPS_TO_USERS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>DIRECT_REPORTS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>DIRECTORY_ROLES</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>IDP</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>USERS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>DEVICES</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ORGANIZATION_DEVICES</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>NETWORK_DEVICES</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>NETWORK_DEVICE_GROUPS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>REGISTERED_DEVICES</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>OWNED_DEVICES</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>RISKY_USERS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>RISKY_USER_EVENTS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>NAMED_LOCATIONS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>IP_CIDR_LIST</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>IP_THREAT_INSIGHTS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>POLICIES</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>POLICY_RULES</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>POLICY_SUMMARY</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>SERVICE_PRINCIPAL</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>API_TOKEN</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>EVENT_HUB</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>AUTHENTICATORS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>AUTHENTICATORS_TO_USERS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>SIGNIN_LOGS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>LOGIN_HISTORY</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>LOGIN_GEO</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>AUTH_CONFIG</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>USER_LOGIN</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>END_USER_LOGINS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>PROFILES</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>CONDITIONAL_ACCESS_POLICY</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>PROVISIONING_EVENTS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ORGANIZATIONS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>USER_EMAILS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>USER_ENTERPRISE_EMAILS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>COLLABORATORS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>MEMBER_INVITATIONS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>COLLABORATOR_INVITATIONS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>PERMISSION_SETS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>USER_SCHEMA</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>MAILBOX_SETTINGS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>MESSAGE_RULES</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>DEVICE_AUDIT_EVENTS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>AUTH_API</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ENDPOINTS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>TOKENS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>WEBAUTHNCREDENTIALS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>BYPASS_CODES</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>SIGNIN_ACTIVITY</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>SESSIONS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ROLES_TO_USERS</strong></td>
<td></td>
</tr>
</tbody>
</table>

### DeviceType

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>ACCESS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>AUTHENTICATION</strong></td>
<td></td>
</tr>
</tbody>
</table>

### EndUserStatus

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>ACTIVE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>INACTIVE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>DEPROVISIONED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>LOCKED_OUT</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>PASSWORD_EXPIRED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>PROVISIONED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>RECOVERY</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>STAGED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>SUSPENDED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>INCONSISTENT</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>DELETED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>DISABLED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>BLOCKED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>TRANSIENT</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>UNKNOWN</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ENABLED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>DEACTIVATED</strong></td>
<td></td>
</tr>
</tbody>
</table>

### HttpMethod

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>GET</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>POST</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>PUT</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>HEAD</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>OPTIONS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>PATCH</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>DELETE</strong></td>
<td></td>
</tr>
</tbody>
</table>

### LevelOfTrust

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>TRUSTED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>FAVORABLE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>NEUTRAL</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>QUESTIONABLE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>UNTRUSTED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>UNKNOWN</strong></td>
<td></td>
</tr>
</tbody>
</table>

### ListType

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>allow</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>block</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ignore</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>include</strong></td>
<td></td>
</tr>
</tbody>
</table>

### Order

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>asc</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>desc</strong></td>
<td></td>
</tr>
</tbody>
</table>

### OsType

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>WINDOWS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>WINDOWS_MOBILE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>MACOS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>IOS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ANDROID</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>LINUX</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>CHROME_OS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>UNKNOWN</strong></td>
<td></td>
</tr>
</tbody>
</table>

### Provider

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>AUTH0</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>AWS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>AZURE_AD</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>OKTA</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>HRIS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>SLACK</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>DUO</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>G_SUITE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>WORKDAY</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>SALESFORCE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>GIT_HUB</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ISE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>WEBEX_CI</strong></td>
<td></td>
</tr>
</tbody>
</table>

### TrustScoreGroupId

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>ACCOUNT_LOGIN_BEHAVIOR</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ACTIONS_IN_SESSION</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>APPLICATION</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>DEVICE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>EXTERNAL_THREAT</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>FIRST_FACTOR</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>SECOND_FACTOR</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>NETWORK</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>PERMISSION</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>SESSION</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ACCOUNT_VALIDITY</strong></td>
<td></td>
</tr>
</tbody>
</table>

### TrustScoreModelType

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>NEW_USER</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>KNOWN_USER</strong></td>
<td></td>
</tr>
</tbody>
</table>

### TrustScoreVersion

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>V1</strong></td>
<td></td>
</tr>
</tbody>
</table>

### TrustScoreWeight

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>NO_RISK</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>LOW_RISK</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>MEDIUM_RISK</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>HIGH_RISK</strong></td>
<td></td>
</tr>
</tbody>
</table>

### UserTypeClassification

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>INTERNAL</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>EXTERNAL</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>MISSING</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>UNCLASSIFIED</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>INCONSISTENT</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>SERVICE_ACCOUNT</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>SHARED_MAILBOX</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>LINKED_USER_ACCOUNT</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>CONFERENCE_ROOM</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>EQUIPMENT_MAILBOX</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>OTHER_MAILBOX</strong></td>
<td></td>
</tr>
</tbody>
</table>

### WorkflowState

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>SUCCESS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ERROR</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>UNKNOWN</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>RUNNING</strong></td>
<td></td>
</tr>
</tbody>
</table>

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

Maps like {\"upvotes\": 10}, lists like [1,2,3], and scalar values like \"AWSJSON example string\", 1, and true are accepted as valid JSON. They will automatically be parsed and loaded in the resolver mapping templates as Maps, Lists, or Scalar values rather than as the literal input strings. Invalid JSON strings like {a: 1}, {'a': 1} and Unquoted string will throw GraphQL validation errors.

### AWSPhone

The AWSPhone scalar type represents a valid Phone Number. Phone numbers are serialized and deserialized as Strings. Phone numbers provided may be whitespace delimited or hyphenated. The number can specify a country code at the beginning but this is not required.

### AWSTime

The AWSTime scalar type represents a valid extended ISO 8601 Time string. In other words, this scalar type accepts time strings of the form hh:mm:ss.sss. The field after the seconds field is a nanoseconds field. It can accept between 1 and 9 digits. The seconds and nanoseconds fields are optional (the seconds field must be specified if the nanoseconds field is to be used). This scalar type can also accept time zone offsets.

For example, 12:30Z, 12:30:24-07:00 and 12:30:24.500+05:30 are all valid time strings.

The time zone offset must either be Z (representing the UTC time zone) or be in the format hh:mm:ss. The seconds field in the timezone offset will be considered valid even though it is not part of the ISO 8601 standard.

### AWSTimestamp

The AWSTimestamp scalar type represents the number of seconds that have elapsed since 1970-01-01T00:00Z. Timestamps are serialized and deserialized as numbers. Negative values are also accepted and these represent the number of seconds till 1970-01-01T00:00Z.

### AWSURL

The AWSURL scalar type represents a valid URL string. The URL may use any scheme and may also be a local URL (Ex: <http://localhost/>). URLs without schemes are considered invalid. URLs which contain double slashes are also considered invalid.

### Boolean

The `Boolean` scalar type represents `true` or `false`.

### Float

The `Float` scalar type represents signed double-precision fractional values as specified by [IEEE 754](https://en.wikipedia.org/wiki/IEEE_floating_point).

### ID

The `ID` scalar type represents a unique identifier, often used to refetch an object or as key for a cache. The ID type appears in a JSON response as a String; however, it is not intended to be human-readable. When expected as an input type, any string (such as `"4"`) or integer (such as `4`) input value will be accepted as an ID.

### Int

The `Int` scalar type represents non-fractional signed whole numeric values. Int can represent values between -(2^31) and 2^31 - 1.

### String

The `String` scalar type represents textual data, represented as UTF-8 character sequences. The String type is most often used by GraphQL to represent free-form human-readable text.

