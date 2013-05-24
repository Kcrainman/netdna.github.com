
# NetDNA API Docs

[NetDNA](http://www.netdna.com) is a content delivery network ("CDN") provider.

## Index

* [Overview](#overview)
* [Support](#support)
* [Changelog](#changelog)
* [Account API](#account-api)
* [Users API](#users-api)
* [Zones API](#zones-api)
* [Reports API](#reports-by-zone-api)
* [Clients API](#reports-by-file-name-api)


## Overview

1. Sign up for a free NetDNA [developer account](http://www.netdna.com/netdna-free-trial/).

2. Create a [new application](https://cp.netdna.com/account/api/create).

3. Integrate with our RESTful API using your language wrapper:
  - Node (NPM) <https://github.com/niftylettuce/node-netdna>
  - .NET <https://github.com/netdna/netdnarws-net>
  - Ruby <https://github.com/netdna/netdnarws-ruby>
  - Python <https://github.com/netdna/netdnarws>
  - PHP <https://github.com/netdna/netdnarws-php>
  - Perl <https://github.com/netdna/netdnarws-perl>

Follow the documentation for our API below!


## Support

Have a question? Check out our [Knowledge base](http://support.netdna.com/) to see if your question has already been answered.

Still need help?  Visit our [Contact](http://www.netdna.com/contact/) page to get in touch.

Feel free to tweet and follow us [@netdna](https://twitter.com/netdna) and [@netdnasupport](https://twitter.com/netdnasupport).


## Changelog

Reference to [History.md](https://github.com/netdna/netdna-apidocs/blob/master/History.md#changelog) for a complete log of API changes and improvements.

---

# Key: Path Parameters

Parameter | Description |
--- | ---
{companyalias} | The alias you used when creating your account |
{zone_type} | The type of zone you are making a request on - one of push,pull, vod, or live |
{report_type} | The format you want the reports summarized by - one of hourly,daily, or monthly. This value can be left blank to receive thetotals ungrouped. |

---

# Account API

## Get Account

Gets account information

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/account.json</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Account ID | 1.0 |
`name` | The name of your account | 1.0 |
`address_id` | Address ID | 1.0 |
`alias` | Company Alias | 1.0 |
`ssl_credits` | SSL Credits | 1.0 |
`flex_credits` | Flex Location Credits | 1.0 |
`date_created` | Date Created | 1.0 |
`date_updated` | Date Updated | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab1">
  <li class="active"><a href="#ruby1" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python1" data-toggle='tab'>Python</a></li>
  <li><a href="#php1" data-toggle='tab'>PHP</a></li>
  <li><a href="#node1" data-toggle='tab'>Node</a></li>
  <li><a href="#response1" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby1">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python1">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php1">
  	<pre>
$api->get('/account.json');</pre>
  </div>
  <div class="tab-pane" id="node1">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response1">
		<pre>
{
    "code": 200,
    "data": {
        "account": {
            "alias": "aliasname",
            "date_created": "2013-05-15 17:32:30",
            "date_updated": "2013-05-15 19:43:36",
            "edgerules_credits": "0",
            "flex_credits": "-1",
            "id": "#####",
            "name": "NetDNA sampleCode",
            "secure_token_pull_credits": "0",
            "server_id": "18",
            "ssl_credits": "-1",
            "status": "2",
            "storage_quota": "107374182400",
            "storage_server_id": "11",
            "zone_credits": "-1"
        }
    }
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab1 a:last').tab('show');
  })
</script>

---

## Update Account

Updates account information

<div class="heading">
<div class="url PUT"><span class="http_method">PUT</span>
<span class="path">https://rws.netdna.com/{companyalias}/account.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`name` | - | <span class="label important">required</span><br />length: 1-30 chars | The name of your account | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Account ID | 1.0 |
`name` | The name of your account | 1.0 |
`address_id` | Address ID | 1.0 |
`alias` | Company Alias | 1.0 |
`ssl_credits` | SSL Credits | 1.0 |
`flex_credits` | Flex Location Credits | 1.0 |
`date_created` | Date Created | 1.0 |
`date_updated` | Date Updated | 1.0 |


### Code Samples

<ul class="nav nav-tabs" id="myTab2">
  <li class="active"><a href="#ruby2" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python2" data-toggle='tab'>Python</a></li>
  <li><a href="#php2" data-toggle='tab'>PHP</a></li>
  <li><a href="#node2" data-toggle='tab'>Node</a></li>
  <li><a href="#response2" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby2">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python2">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php2">
  	<pre>
$api->put('/account.json',array("name"=>"newName"));</pre>
  </div>
  <div class="tab-pane" id="node2">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response2">
		<pre>
{"code":200,"data":
	{"account":
		{"id":"#####","name":"newName","alias":"aliasname","date_created":"2013-05-15 17:32:30","date_updated":"2013-05-23 17:58:27","server_id":"18","status":"2","storage_quota":"107374182400","storage_server_id":"11","ssl_credits":"-1","flex_credits":"-1","zone_credits":"-1","secure_token_pull_credits":"0","edgerules_credits":"0"}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab2 a:last').tab('show');
  })
</script>

---

## Get Account Address

Gets account address information

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/account.json/address</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Address ID | 1.0 |
`street1` | Street Address Line 1 | 1.0 |
`street2` | Street Address Line 2 | 1.0 |
`city` | City | 1.0 |
`state` | State | 1.0 |
`zip` | ZIP | 1.0 |
`country` | Country Code | 1.0 |
`date_created` | Date Created | 1.0 |
`date_updated` | Date Updated | 1.0 |


### Code Samples

<ul class="nav nav-tabs" id="myTab3">
  <li class="active"><a href="#ruby3" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python3" data-toggle='tab'>Python</a></li>
  <li><a href="#php3" data-toggle='tab'>PHP</a></li>
  <li><a href="#node3" data-toggle='tab'>Node</a></li>
  <li><a href="#response3" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby3">
		<pre>
		</pre>
  </div>
  <div class="tab-pane" id="python3">
		<pre>
		</pre>
	</div>
  <div class="tab-pane" id="php3">
  	<pre>
$api->get('/account.json/address')</pre>
  </div>
  <div class="tab-pane" id="node3">
		<pre>
		</pre>
  </div>
  <div class="tab-pane" id="response3">
		<pre>
{"code":200,"data":
	{"address":
		{"id":"#####","street1":"123 Main Street","street2":"apt 42","city":"los angeles","state":"CA","zip":"90068","country":"US","date_created":"0000-00-00 00:00:00","date_updated":"2013-05-15 19:54:40"}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab3 a:last').tab('show');
  })
</script>

---

## Update Account Address

Updates account address information

<div class="heading">
<div class="url PUT"><span class="http_method">PUT</span>
<span class="path">https://rws.netdna.com/{companyalias}/account.json/address</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`street1` | - | length: 1-200 chars | Street Address Line 1 | 1.0 |
`street2` | - | length: 1-200 chars | Street Address Line 2 | 1.0 |
`city` | - | length: 1-50 chars | City | 1.0 |
`state` | - | length: 1-50 chars | State | 1.0 |
`zip` | - | length: 3-5 chars; only digits accepted | ZIP | 1.0 |
`country` | - | length: 2 chars | Country Code | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Address ID | 1.0 |
`street1` | Street Address Line 1 | 1.0 |
`street2` | Street Address Line 2 | 1.0 |
`city` | City | 1.0 |
`state` | State | 1.0 |
`zip` | ZIP | 1.0 |
`country` | Country Code | 1.0 |
`date_created` | Date Created | 1.0 |
`date_updated` | Date Updated | 1.0 |


### Code Samples

<ul class="nav nav-tabs" id="myTab4">
  <li class="active"><a href="#ruby4" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python4" data-toggle='tab'>Python</a></li>
  <li><a href="#php4" data-toggle='tab'>PHP</a></li>
  <li><a href="#node4" data-toggle='tab'>Node</a></li>
  <li><a href="#response4" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby4">
		<pre>
		</pre>
  </div>
  <div class="tab-pane" id="python4">
		<pre>
		</pre>
	</div>
  <div class="tab-pane" id="php4">
  	<pre>
$params = array("street1"=>"123 Main Street", "street2"=>"apt 42", "state"=>"CA");
$api->put('/account.json/address',$params);</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
		</pre>
  </div>
  <div class="tab-pane" id="response4">
		<pre>
{"code":200,"data":
	{"address":
		{"id":"#####","street1":"1234 Main Street","street2":"apt 42","city":"los angeles","state":"CA","zip":"90068","country":"US","date_created":"0000-00-00 00:00:00","date_updated":"2013-05-23 18:01:29"}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab4 a:last').tab('show');
  })
</script>

---

# Users API

## List Users

Returns a list of all users on the specified account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/users.json</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | User ID | 1.0 |
`email` | Email Address | 1.0 |
`firstname` | First Name | 1.0 |
`lastname` | Last Name | 1.0 |
`phone` | Phone Number | 1.0 |
`timezone` | User's Timezone | 1.0 |
`date_last_login` | The date and time the user last logged into the system | 1.0 |
`ip_last_login` | The IP for the user at the last login | 1.0 |
`date_created` | Date Created | 1.0 |
`date_updated` | Date Updated | 1.0 |
`roles` | An array of roles for the given user | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab5">
  <li class="active"><a href="#ruby5" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python5" data-toggle='tab'>Python</a></li>
  <li><a href="#php5" data-toggle='tab'>PHP</a></li>
  <li><a href="#node5" data-toggle='tab'>Node</a></li>
  <li><a href="#response5" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby5">
		<pre>
		</pre>
  </div>
  <div class="tab-pane" id="python5">
		<pre>
		</pre>
	</div>
  <div class="tab-pane" id="php5">
  	<pre>
$api->get('/users.json');</pre>
  </div>
  <div class="tab-pane" id="node5">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response5">
		<pre>
{"code":200,"data":
	{"page":1,"pages":1,"page_size":"50","current_page_size":4,"total":4,"users":
		[
			{"id":"33706","email":"name@domain.com","firstname":"Given","lastname":"Family","phone":"3235551400","isadmin":"0","isdisabled":"0","default_company_id":"#####","brand_id":"1","timezone":"Europe\/London","date_last_login":"2013-05-23 17:54:18","ip_last_login":"12.13.90.183","date_created":"2013-05-15 17:32:30","date_updated":"2013-05-15 17:33:09","roles":["User","Account Owner"]},
			{"id":"33714","email":"caphammer1@hamcave.com","firstname":"Captain","lastname":"Hammer","phone":null,"isadmin":"0","isdisabled":"0","default_company_id":"19538","brand_id":"1","timezone":"Europe\/London","date_last_login":null,"ip_last_login":null,"date_created":"2013-05-15 20:16:34","date_updated":"0000-00-00 00:00:00","roles":["User"]},
			{"id":"33716","email":"drhorrible3@ele.net","firstname":"Billy","lastname":"Horrible","phone":null,"isadmin":"0","isdisabled":"0","default_company_id":"19538","brand_id":"1","timezone":"Europe\/London","date_last_login":null,"ip_last_login":null,"date_created":"2013-05-15 20:20:03","date_updated":"2013-05-15 20:31:05","roles":["User"]}
		]
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab5 a:last').tab('show');
  })
</script>

---


## Create User

Creates a new user on the specified account

<div class="heading">
<div class="url POST"><span class="http_method">POST</span>
<span class="path">https://rws.netdna.com/{companyalias}/users.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`email` | - | <span class="label important">required</span><br />length: 6-200 chars; valid email address | Email Address | 1.0 |
`password` | - | <span class="label important">required</span><br />length: 5-30 chars | Password | 1.0 |
`firstname` | - | <span class="label important">required</span><br />length: 1-32 chars | First Name | 1.0 |
`lastname` | - | <span class="label important">required</span><br />length: 1-32 chars | Last Name | 1.0 |
`phone` | - | length: 7, 10, 11, or 14 chars; only digits considered | Phone Number | 1.0 |
`timezone` | - | valid::timezone | Valid timezone (see [List ofSupported Timezones](http://php.net/manual/en/timezones.php)) | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | User ID | 1.0 |
`email` | Email Address | 1.0 |
`firstname` | First Name | 1.0 |
`lastname` | Last Name | 1.0 |
`phone` | Phone Number | 1.0 |
`timezone` | User's Timezone | 1.0 |
`date_last_login` | The date and time the user last logged into the system | 1.0 |
`ip_last_login` | The IP for the user at the last login | 1.0 |
`date_created` | Date Created | 1.0 |
`date_updated` | Date Updated | 1.0 |
`roles` | An array of roles for the given user | 1.0 |


### Code Samples

<ul class="nav nav-tabs" id="myTab6">
  <li class="active"><a href="#ruby6" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python6" data-toggle='tab'>Python</a></li>
  <li><a href="#php6" data-toggle='tab'>PHP</a></li>
  <li><a href="#node6" data-toggle='tab'>Node</a></li>
  <li><a href="#response6" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby6">
		<pre>
		</pre>
  </div>
  <div class="tab-pane" id="python6">
		<pre>
		</pre>
	</div>
  <div class="tab-pane" id="php6">
  	<pre>
$params = array("email"=>"name@domain.com","password"=>"password","firstname"=>"Given","lastname"=>"Family");
$api->post('/users.json',$params );</pre>
  </div>
  <div class="tab-pane" id="node6">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response6">
		<pre>
{"code":201,"data":
	{"user":
		{"id":33941,"email":"name@domain.com","firstname":"Given","lastname":"Family","phone":null,"isadmin":0,"isdisabled":0,"default_company_id":"19538","brand_id":null,"timezone":"America\/Los_Angeles","date_last_login":null,"ip_last_login":null,"date_created":"2013-05-23 18:22:11","date_updated":null,"roles":["User"]}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab6 a:last').tab('show');
  })
</script>

---

## Get User

Gets a user specified by the {user_id} parameter

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/users.json/{user_id}</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | User ID | 1.0 |
`email` | Email Address | 1.0 |
`firstname` | First Name | 1.0 |
`lastname` | Last Name | 1.0 |
`phone` | Phone Number | 1.0 |
`timezone` | User's Timezone | 1.0 |


### Code Samples

<ul class="nav nav-tabs" id="myTab7">
  <li class="active"><a href="#ruby7" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python7" data-toggle='tab'>Python</a></li>
  <li><a href="#php7" data-toggle='tab'>PHP</a></li>
  <li><a href="#node7" data-toggle='tab'>Node</a></li>
  <li><a href="#response7" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby7">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python7">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php7">
  	<pre>
$id = '33941';
$api->get('/users.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node7">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response7">
		<pre>
{"code":200,"data":
	{"user":
		{"id":"33941","email":"name@domain.com","firstname":"Given","lastname":"Family","phone":null,"isadmin":"0","isdisabled":"0","default_company_id":"19538","brand_id":"1","timezone":"Europe\/London","date_last_login":null,"ip_last_login":null,"date_created":"2013-05-23 18:22:11","date_updated":"0000-00-00 00:00:00","roles":["User"]}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab7 a:last').tab('show');
  })
</script>

---

## Update User

Updates a user specified by the {user_id} parameter

<div class="heading">
<div class="url PUT"><span class="http_method">PUT</span>
<span class="path">https://rws.netdna.com/{companyalias}/users.json/{user_id}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`email` | - | length: 6-200 chars; valid email address | Email Address | 1.0 |
`firstname` | - | length: 1-32 chars | First Name | 1.0 |
`lastname` | - | length: 1-32 chars | Last Name | 1.0 |
`phone` | - | length: 7, 10, 11, or 14 chars; only digits considered | Phone Number | 1.0 |
`timezone` | - | valid::timezone | Valid timezone (see [List ofSupported Timezones](http://php.net/manual/en/timezones.php)) | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | User ID | 1.0 |
`email` | Email Address | 1.0 |
`firstname` | First Name | 1.0 |
`lastname` | Last Name | 1.0 |
`phone` | Phone Number | 1.0 |
`timezone` | User's Timezone | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab8">
  <li class="active"><a href="#ruby8" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python8" data-toggle='tab'>Python</a></li>
  <li><a href="#php8" data-toggle='tab'>PHP</a></li>
  <li><a href="#node8" data-toggle='tab'>Node</a></li>
  <li><a href="#response8" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby8">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python8">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php8">
  	<pre>
$id = '33941';
$params =  array("firstname"=>"Billy");
$api->put('/users.json/'.$id,$params);</pre>
</div>
  <div class="tab-pane" id="node8">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response8">
		<pre>
{"code":200,"data":
	{"user":
		{"id":"33941","email":"name@domain.com","firstname":"Billy","lastname":"Family","phone":null,"isadmin":"0","isdisabled":"0","default_company_id":"19538","brand_id":"1","timezone":"Europe\/London","date_last_login":null,"ip_last_login":null,"date_created":"2013-05-23 18:22:11","date_updated":"2013-05-23 19:10:09","roles":["User"]}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab8 a:last').tab('show');
  })
</script>

---


## Delete User

Deletes a user specified by the {user_id} parameter

<div class="heading">
<div class="url DELETE"><span class="http_method">DELETE</span>
<span class="path">https://rws.netdna.com/{companyalias}/users.json/{user_id}</span></div>
</div>


### Code Samples

<ul class="nav nav-tabs" id="myTab9">
  <li class="active"><a href="#ruby9" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python9" data-toggle='tab'>Python</a></li>
  <li><a href="#php9" data-toggle='tab'>PHP</a></li>
  <li><a href="#node9" data-toggle='tab'>Node</a></li>
  <li><a href="#response9" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby9">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python9">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php9">
  	<pre>
$id = '33715';
$api->delete('/users.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node9">
		<pre>
		</pre>
  </div>
  <div class="tab-pane" id="response9">
		<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab9 a:last').tab('show');
  })
</script>

---
---

# Zones API

## List Zones

Returns a list of all zones on the specified account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones.json</span></div>
</div>

### Code Samples

<ul class="nav nav-tabs" id="myTab10">
  <li class="active"><a href="#ruby10" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python10" data-toggle='tab'>Python</a></li>
  <li><a href="#php10" data-toggle='tab'>PHP</a></li>
  <li><a href="#node10" data-toggle='tab'>Node</a></li>
  <li><a href="#response10" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby10">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python10">
		<pre>
		</pre>
	</div>
  <div class="tab-pane" id="php10">
  	<pre>
$api->get('/zones.json');</pre>
  </div>
  <div class="tab-pane" id="node10">
		<pre>
		</pre>
  </div>
  <div class="tab-pane" id="response10">
		<pre>
{"code":200,"data":
	{"page":1,"pages":1,"page_size":"50","current_page_size":4,"total":4,"zones":
		[
			{"id":"#####","name":"zoneName","type":"2","suspend":"0","label":"personal","inactive":"0","locked":"0","creation_date":"2013-05-15 20:45:44","cdn_url":"cdn.somedomain.com","tmp_url":"zone.alias.netdna-cdn.com"},
			{"id":"#####","name":"newpushzone2","type":"3","suspend":"0","label":null,"inactive":"0","locked":"0","creation_date":"2013-05-16 15:25:19","cdn_url":"cdn.somedomain.net","tmp_url":"newpushzone2.alias.netdna-cdn.com"},
			{"id":"#####","name":"newvodzone","type":"4","suspend":"0","label":null,"inactive":"0","locked":"0","creation_date":"2013-05-16 16:02:35","cdn_url":"cdn.somedomain.com","tmp_url":"newvodzone.alias.netdna-cdn.com"},
			{"id":"#####","name":"newlivezone","type":"5","suspend":"0","label":null,"inactive":"0","locked":"0","creation_date":"2013-05-16 16:23:49","cdn_url":"newlivezone.somedomain.netdna-cdn.com","tmp_url":"newlivezone.alias.netdna-cdn.com"}
		]
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab10 a:last').tab('show');
  })
</script>

---

## Get Zone Summary

Gets a summarized count of all zone types on the specified
account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones.json/summary</span></div>
</div>


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`pull` | The number of pull zones for your account | 1.0 |
`push` | The number of push zones for your account | 1.0 |
`vod` | The number of vod zones for your account | 1.0 |
`live` | The number of live zones for your account | 1.0 |


### Code Samples

<ul class="nav nav-tabs" id="myTab11">
  <li class="active"><a href="#ruby11" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python11" data-toggle='tab'>Python</a></li>
  <li><a href="#php11" data-toggle='tab'>PHP</a></li>
  <li><a href="#node11" data-toggle='tab'>Node</a></li>
  <li><a href="#response11" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby11">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python11">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php11">
  	<pre>
$api->get('/zones.json/summary');</pre>
  </div>
  <div class="tab-pane" id="node11">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response11">
		<pre>
{"code":200,"data":
	{"summary":
		{"pull":1,"push":1,"vod":1,"live":1,"garmin":0}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab11 a:last').tab('show');
  })
</script>

---

## Get Zone Count

Counts all zones on the specified account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones.json/count</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`count` | The total number of content zones for your account | 1.0 |



### Code Samples

<ul class="nav nav-tabs" id="myTab12">
  <li class="active"><a href="#ruby12" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python12" data-toggle='tab'>Python</a></li>
  <li><a href="#php12" data-toggle='tab'>PHP</a></li>
  <li><a href="#node12" data-toggle='tab'>Node</a></li>
  <li><a href="#response12" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby12">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python12">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php12">
  	<pre>
$api->get('/zones.json/count');</pre>
  </div>
  <div class="tab-pane" id="node12">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response12">
		<pre>
{"code":200,"data":
	{"count":"4"}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab12 a:last').tab('show');
  })
</script>

---

# Pull Zone API

## List Pull Zones

Returns a list of all pull zones on the specified account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull.json</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Pull Zone ID | 1.0 |
`name` | Pull Zone name | 1.0 |
`url` | Origin URL | 1.0 |
`port` | Port | 1.0 |
`ip` | IP address of the Origin URL | 1.0 |
`compress` | On the fly compression of your files served from our edges.GZip compression for the following file types: text/plain,text/html, text/javascript, text/css, text/xml,application/javascript, application/x-javascript, application/xml,text/x-component, application/json, application/xhtml+xml,application/rss+xml, application/atom+xml, app/vnd.ms-fontobject,image/svg+xml, application/x-font-ttf, font/opentype | 1.0 |
`backend_compress` | Allow us to cache compressed versions of your files from theorigin. GZip compression for the following file types: text/plain,text/html, text/javascript, text/css, text/xml,application/javascript, application/x-javascript, application/xml,text/x-component, application/json, application/xhtml+xml,application/rss+xml, application/atom+xml, app/vnd.ms-fontobject,image/svg+xml, application/x-font-ttf, font/opentype | 1.0 |
`queries` | Treat Query Strings as a separate cacheable item | 1.0 |
`set_host_header` | The URL sent as the Host in all HTTP Response Headers | 1.0 |
`cache_valid` | Ignore the origin Cache-Control Header and set every request tohave a Max-Age of 1d, 7d, 1M or 12M | 1.0 |
`ignore_setcookie_header` | Ignore any cookies set by the origin in order to make thecontent consistently cacheable | 1.0 |
`ignore_cache_control` | Ignore any max age values set by the origin and use the CDN setvalue instead | 1.0 |
`use_stale` | Serve expired content while fetching new content. This willalso cause the CDN to serve expired content in cases where theorigin is down or the file is not found | 1.0 |
`proxy_cache_lock` | When multiple requests for an uncached file are received, theywill wait until the first response is received rather than sendingeach request back to the origin | 1.0 |
`label` | Something that describes your zone | 1.0 |
`valid_referers` | List of domains for http referrer protection (separated byspace). Only the domains in the list will be treated as validreferrers | 1.0 |
`expires` | Set any request with a no "Cache-Control header" from theorigin to stay on the server. Possible values are 1d, 7d, 1M,12M | 1.0 |
`disallow_robots` | Enable robots.txt | 1.0 |
`disallow_robots_txt` | Use custom robots.txt | 1.0 |
`canonical_link_headers` | Pass the canonical URL in the Link HTTP Header | 1.0 |
`content_disposition` | Force files to download | 1.0 |
`pseudo_streaming` | Enable the zone for pseudo streaming content | 1.0 |
`sslshared` | Enable Shared SSL. This feature allows you use your zone inHTTPS mode. You don't need your own SSL certificate, our servernetdna-ssl.com will be used. | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab13">
  <li class="active"><a href="#ruby13" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python13" data-toggle='tab'>Python</a></li>
  <li><a href="#php13" data-toggle='tab'>PHP</a></li>
  <li><a href="#node13" data-toggle='tab'>Node</a></li>
  <li><a href="#response13" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby13">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python13">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php13">
  	<pre>
$api->get('/zones/pull.json');</pre>
  </div>
  <div class="tab-pane" id="node13">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response13">
		<pre>
{"code":200,"data":
	{"page":1,"pages":1,"page_size":"50","current_page_size":1,"total":1,"pullzones":
		[
			{"id":"#####","name":"zoneName","url":"http:\/\/somedomain.net","port":"80","ip":"127.0.0.1","type":"2","compress":"1","backend_compress":"0","queries":"1","suspend":"0","cache_valid":"1d","label":"personal","inactive":"0","valid_referers":null,"expires":null,"disallow_robots":"0","disallow_robots_txt":null,"canonical_link_headers":"0","content_disposition":"0","locked":"0","server_id":"18","sslshared":"0","creation_date":"2013-05-15 20:45:44","set_host_header":null,"dns_check":"1","ignore_setcookie_header":"0","hide_setcookie_header":"0","ignore_cache_control":"0","use_stale":"0","proxy_cache_lock":"0","pseudo_streaming":"0","upstream_enabled":"0","cdn_url":"cdn.somedomain.com","tmp_url":"somedomain.alias.netdna-cdn.com"}
		]
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab13 a:last').tab('show');
  })
</script>

---

## Create Pull Zone

Creates a new pull zone

<div class="heading">
<div class="url POST"><span class="http_method">POST</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`name` | - | <span class="label important">required</span><br />length: 3-32 chars; only letters, digits, and dash (-)accepted | Pull Zone Name | 1.0 |
`url` | - | <span class="label important">required</span><br />length: 4-100 chars; only valid URLs accepted | Origin URL | 1.0 |
`port` | 80 | length: 1-5 chars; only digits accepted | Port | 1.0 |
`ip` | - | length: 1-10 chars, only digits accepted | Valid IP address of the Origin URL. If omitted, the servicewill try to lookup the IP automatically. | 1.0 |
`compress` | 0 | only 0 or 1 accepted | On the fly compression of your files served from our edges.Enable GZip compression for the following file types: text/plain,text/html, text/javascript, text/css, text/xml,application/javascript, application/x-javascript, application/xml,text/x-component, application/json, application/xhtml+xml,application/rss+xml, application/atom+xml, app/vnd.ms-fontobject,image/svg+xml, application/x-font-ttf, font/opentype | 1.0 |
`backend_compress` | 0 | only 0 or 1 accepted | Allow us to cache compressed versions of your files from theorigin. Enable GZip compression for the following file types:text/plain, text/html, text/javascript, text/css, text/xml,application/javascript, application/x-javascript, application/xml,text/x-component, application/json, application/xhtml+xml,application/rss+xml, application/atom+xml, app/vnd.ms-fontobject,image/svg+xml, application/x-font-ttf, font/opentype | 1.0 |
`queries` | 0 | only 0 or 1 accepted | Treat Query Strings as a separate cacheable item | 1.0 |
`set_host_header` | - | length: 4-100 chars; only valid URLs accepted | The URL to send as the Host in all HTTP Response Headers | 1.0 |
`cache_valid` | 1d | length: 1-30 chars; must be a number followed by one of s, m,h, d, M, or Y | Ignore the origin Cache-Control Header and set every request tohave a Max-Age of 1d, 7d, 1M or 12M | 1.0 |
`ignore_setcookie_header` | 0 | only 0 or 1 accepted | Ignore any cookies set by the origin in order to make thecontent consistently cacheable | 1.0 |
`ignore_cache_control` | 0 | only 0 or 1 accepted | Ignore any max age values set by the origin and use the CDN setvalue instead | 1.0 |
`use_stale` | 0 | only 0 or 1 accepted | Serve expired content while fetching new content. This willalso cause the CDN to serve expired content in cases where theorigin is down or the file is not found | 1.0 |
`proxy_cache_lock` | 0 | only 0 or 1 accepted | When multiple requests for an uncached file are received, theywill wait until the first response is received rather than sendingeach request back to the origin | 1.0 |
`label` | - | length: 1-255 chars | Something that describes your zone | 1.0 |
`valid_referers` | - | length: 1-100 chars | List of domains for http referrer protection (separated byspace). Only the domains in the list will be treated as validreferrers | 1.0 |
`expires` | 1d | length: 1-32 chars | Set any request with a no "Cache-Control header" from theorigin to stay on the server. Possible values are 1d, 7d, 1M,12M | 1.0 |
`disallow_robots` | 0 | only 0 or 1 accepted | Enable robots.txt | 1.0 |
`disallow_robots_txt` | - | length 1-255 chars | Use custom robots.txt | 1.0 |
`canonical_link_headers` | 1 | only 0 or 1 accepted | Pass the canonical URL in the Link HTTP Header | 1.0 |
`content_disposition` | 0 | only 0 or 1 accepted | Force files to download | 1.0 |
`pseudo_streaming` | 0 | only 0 or 1 accepted | Enable the zone for pseudo streaming content | 1.0 |
`secret` | - | length: 1 - 32 chars | Use a secret to protect your files from unwanted visitors | 1.0 |
`sslshared` | 0 | only 0 or 1 accepted | Enable Shared SSL. This feature allows you use your zone inHTTPS mode. You don't need your own SSL certificate, our servernetdna-ssl.com will be used. | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Pull Zone ID | 1.0 |
`name` | Pull Zone name | 1.0 |
`url` | Origin URL | 1.0 |
`port` | Port | 1.0 |
`ip` | IP address of the Origin URL | 1.0 |
`compress` | On the fly compression of your files served from our edges.GZip compression for the following file types: text/plain,text/html, text/javascript, text/css, text/xml,application/javascript, application/x-javascript, application/xml,text/x-component, application/json, application/xhtml+xml,application/rss+xml, application/atom+xml, app/vnd.ms-fontobject,image/svg+xml, application/x-font-ttf, font/opentype | 1.0 |
`backend_compress` | Allow us to cache compressed versions of your files from theorigin. GZip compression for the following file types: text/plain,text/html, text/javascript, text/css, text/xml,application/javascript, application/x-javascript, application/xml,text/x-component, application/json, application/xhtml+xml,application/rss+xml, application/atom+xml, app/vnd.ms-fontobject,image/svg+xml, application/x-font-ttf, font/opentype | 1.0 |
`queries` | Treat Query Strings as a separate cacheable item | 1.0 |
`set_host_header` | The URL sent as the Host in all HTTP Response Headers | 1.0 |
`cache_valid` | Ignore the origin Cache-Control Header and set every request tohave a Max-Age of 1d, 7d, 1M or 12M | 1.0 |
`ignore_setcookie_header` | Ignore any cookies set by the origin in order to make thecontent consistently cacheable | 1.0 |
`ignore_cache_control` | Ignore any max age values set by the origin and use the CDN setvalue instead | 1.0 |
`use_stale` | Serve expired content while fetching new content. This willalso cause the CDN to serve expired content in cases where theorigin is down or the file is not found | 1.0 |
`proxy_cache_lock` | When multiple requests for an uncached file are received, theywill wait until the first response is received rather than sendingeach request back to the origin | 1.0 |
`label` | Something that describes your zone | 1.0 |
`valid_referers` | List of domains for http referrer protection (separated byspace). Only the domains in the list will be treated as validreferrers | 1.0 |
`expires` | Set any request with a no "Cache-Control header" from theorigin to stay on the server. Possible values are 1d, 7d, 1M,12M | 1.0 |
`disallow_robots` | Enable robots.txt | 1.0 |
`disallow_robots_txt` | Use custom robots.txt | 1.0 |
`canonical_link_headers` | Pass the canonical URL in the Link HTTP Header | 1.0 |
`content_disposition` | Force files to download | 1.0 |
`pseudo_streaming` | Enable the zone for pseudo streaming content | 1.0 |
`sslshared` | Enable Shared SSL. This feature allows you use your zone inHTTPS mode. You don't need your own SSL certificate, our servernetdna-ssl.com will be used. | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab14">
  <li class="active"><a href="#ruby14" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python14" data-toggle='tab'>Python</a></li>
  <li><a href="#php14" data-toggle='tab'>PHP</a></li>
  <li><a href="#node14" data-toggle='tab'>Node</a></li>
  <li><a href="#response14" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby14">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python14">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php14">
  	<pre>
$params =  array("name"=>"newPullZone2","url"=>"http://somedomain.net");
$api->post('/zones/pull.json',$params);</pre>
  </div>
  <div class="tab-pane" id="node14">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response14">
		<pre>
{"code":201,"data":
	{"pullzone":
		{"id":#####,"name":"newpullzone2","url":"http:\/\/somedomain.net","port":80,"ip":"205.134.255.49","type":2,"compress":0,"backend_compress":0,"queries":"1","suspend":0,"cache_valid":"1d","label":null,"inactive":0,"valid_referers":null,"expires":null,"disallow_robots":0,"disallow_robots_txt":null,"canonical_link_headers":1,"content_disposition":0,"locked":0,"server_id":"18","sslshared":null,"creation_date":"2013-05-23 19:38:29","set_host_header":1,"dns_check":0,"ignore_setcookie_header":0,"hide_setcookie_header":0,"ignore_cache_control":0,"use_stale":0,"proxy_cache_lock":0,"pseudo_streaming":0,"upstream_enabled":0,"cdn_url":"newpullzone2.alias.netdna-cdn.com","tmp_url":"newpullzone2.alias.netdna-cdn.com"}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab14 a:last').tab('show');
  })
</script>

---

## Get Pull Zones Count

Counts all pull zones on the specified account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull.json/count</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`count` | The number of pull zones on the specified account | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab15">
  <li class="active"><a href="#ruby15" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python15" data-toggle='tab'>Python</a></li>
  <li><a href="#php15" data-toggle='tab'>PHP</a></li>
  <li><a href="#node15" data-toggle='tab'>Node</a></li>
  <li><a href="#response15" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby15">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python15">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php15">
  	<pre>
$api->get('/zones/pull.json/count');</pre>
  </div>
  <div class="tab-pane" id="node15">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response15">
		<pre>
{"code":200,"data":
	{"count":"3"}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab15 a:last').tab('show');
  })
</script>

---

## Get Pull Zone

Gets a pull zone specified by the {zone_id} parameter

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull.json/{zone_id}</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The Pull Zone ID | 1.0 |
`name` | Pull Zone name | 1.0 |
`url` | Origin URL | 1.0 |
`port` | Port | 1.0 |
`ip` | Valid IP address of the Origin URL. If omitted, the servicewill try to lookup the IP automatically. | 1.0 |
`compress` | On the fly compression of your files served from our edges.GZip compression for the following file types: text/plain,text/html, text/javascript, text/css, text/xml,application/javascript, application/x-javascript, application/xml,text/x-component, application/json, application/xhtml+xml,application/rss+xml, application/atom+xml, app/vnd.ms-fontobject,image/svg+xml, application/x-font-ttf, font/opentype | 1.0 |
`backend_compress` | Allow us to cache compressed versions of your files from theorigin. GZip compression for the following file types: text/plain,text/html, text/javascript, text/css, text/xml,application/javascript, application/x-javascript, application/xml,text/x-component, application/json, application/xhtml+xml,application/rss+xml, application/atom+xml, app/vnd.ms-fontobject,image/svg+xml, application/x-font-ttf, font/opentype | 1.0 |
`queries` | Treat Query Strings as a separate cacheable item | 1.0 |
`set_host_header` | The URL sent as the Host in all HTTP Response Headers | 1.0 |
`cache_valid` | Ignore the origin Cache-Control Header and set every request tohave a Max-Age of 1d, 7d, 1M or 12M | 1.0 |
`ignore_setcookie_header` | Ignore any cookies set by the origin in order to make thecontent consistently cacheable | 1.0 |
`ignore_cache_control` | Ignore any max age values set by the origin and use the CDN setvalue instead | 1.0 |
`use_stale` | Serve expired content while fetching new content. This willalso cause the CDN to serve expired content in cases where theorigin is down or the file is not found | 1.0 |
`proxy_cache_lock` | When multiple requests for an uncached file are received, theywill wait until the first response is received rather than sendingeach request back to the origin | 1.0 |
`label` | Something that describes your zone | 1.0 |
`valid_referers` | List of domains for http referrer protection (separated byspace). Only the domains in the list will be treated as validreferrers | 1.0 |
`expires` | Set any request with a no "Cache-Control header" from theorigin to stay on the server. Possible values are 1d, 7d, 1M,12M | 1.0 |
`disallow_robots` | Enable robots.txt | 1.0 |
`disallow_robots_txt` | Use custom robots.txt | 1.0 |
`canonical_link_headers` | Pass the canonical URL in the Link HTTP Header | 1.0 |
`content_disposition` | Force files to download | 1.0 |
`pseudo_streaming` | Enable the zone for pseudo streaming content | 1.0 |
`sslshared` | Enable Shared SSL. This feature allows you use your zone inHTTPS mode. You don't need your own SSL certificate, our servernetdna-ssl.com will be used. | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab16">
  <li class="active"><a href="#ruby16" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python16" data-toggle='tab'>Python</a></li>
  <li><a href="#php16" data-toggle='tab'>PHP</a></li>
  <li><a href="#node16" data-toggle='tab'>Node</a></li>
  <li><a href="#response16" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby16">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python16">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php16">
  	<pre>
$id = '96076';
$api->get('/zones/pull.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node16">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response16">
		<pre>
{"code":200,"data":
	{"pullzone":
		{"id":"96076","name":"newpullzone","url":"http:\/\/somedomain.net","port":"80","ip":"127.0.0.1","type":"2","compress":"0","backend_compress":"0","queries":"1","suspend":"0","cache_valid":"1d","label":"Some other description","inactive":"1","valid_referers":null,"expires":null,"disallow_robots":"0","disallow_robots_txt":null,"canonical_link_headers":"0","content_disposition":"0","locked":"0","server_id":"18","sslshared":"0","creation_date":"2013-05-15 23:01:18","set_host_header":null,"dns_check":"1","ignore_setcookie_header":"0","hide_setcookie_header":"0","ignore_cache_control":"0","use_stale":"0","proxy_cache_lock":"0","pseudo_streaming":"0","upstream_enabled":"0","cdn_url":"newpullzone.alias.netdna-cdn.com","tmp_url":"newpullzone.alias.netdna-cdn.com"}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab16 a:last').tab('show');
  })
</script>

---

## Update Pull Zone

Updates a pull zone specified by the {zone_id} parameter

<div class="heading">
<div class="url PUT"><span class="http_method">PUT</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull.json/{zone_id}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`url` | - | length: 4-100 chars; only valid URLs accepted | Origin URL | 1.0 |
`port` | 80 | length: 1-5 chars; only digits accepted | Port | 1.0 |
`compress` | 0 | only 0 or 1 accepted | On the fly compression of your files served from our edges.Enable GZip compression for the following file types: text/plain,text/html, text/javascript, text/css, text/xml,application/javascript, application/x-javascript, application/xml,text/x-component, application/json, application/xhtml+xml,application/rss+xml, application/atom+xml, app/vnd.ms-fontobject,image/svg+xml, application/x-font-ttf, font/opentype | 1.0 |
`backend_compress` | 0 | only 0 or 1 accepted | Allow us to cache compressed versions of your files from theorigin. Enable GZip compression for the following file types:text/plain, text/html, text/javascript, text/css, text/xml,application/javascript, application/x-javascript, application/xml,text/x-component, application/json, application/xhtml+xml,application/rss+xml, application/atom+xml, app/vnd.ms-fontobject,image/svg+xml, application/x-font-ttf, font/opentype | 1.0 |
`queries` | 0 | only 0 or 1 accepted | Treat Query Strings as a separate cacheable item | 1.0 |
`set_host_header` | - | length: 4-100 chars; only valid URLs accepted | The URL to send as the Host in all HTTP Response Headers | 1.0 |
`cache_valid` | - | length: 1-30 chars; must be a number followed by one of s, m,h, d, M, or Y | Ignore the origin Cache-Control Header and set every request tohave a Max-Age of 1d, 7d, 1M or 12M | 1.0 |
`ignore_setcookie_header` | 0 | only 0 or 1 accepted | Ignore any cookies set by the origin in order to make thecontent consistently cacheable | 1.0 |
`ignore_cache_control` | 0 | only 0 or 1 accepted | Ignore any max age values set by the origin and use the CDN setvalue instead | 1.0 |
`use_stale` | 0 | only 0 or 1 accepted | Serve expired content while fetching new content. This willalso cause the CDN to serve expired content in cases where theorigin is down or the file is not found | 1.0 |
`proxy_cache_lock` | 0 | only 0 or 1 accepted | When multiple requests for an uncached file are received, theywill wait until the first response is received rather than sendingeach request back to the origin | 1.0 |
`label` | - | length: 1-255 chars | Something that describes your zone | 1.0 |
`valid_referers` | - | length: 1-100 chars | List of domains for http referrer protection (separated byspace). Only the domains in the list will be treated as validreferrers | 1.0 |
`expires` | 1d | length: 1-32 chars | Set any request with a no "Cache-Control header" from theorigin to stay on the server. Possible values are 1d, 7d, 1M,12M | 1.0 |
`disallow_robots` | 0 | only 0 or 1 accepted | Enable robots.txt | 1.0 |
`disallow_robots_txt` | - | length: 1-255 chars | Use custom robots.txt | 1.0 |
`canonical_link_headers` | 1 | only 0 or 1 accepted | Pass the canonical URL in the Link HTTP Header | 1.0 |
`content_disposition` | 0 | only 0 or 1 accepted | Force files to download | 1.0 |
`pseudo_streaming` | 0 | only 0 or 1 accepted | Enable the zone for pseudo streaming content | 1.0 |
`secret` | - | length: 1 - 32 chars | Use a secret to protect your files from unwanted visitors | 1.0 |
`sslshared` | 0 | only 0 or 1 accepted | Enable Shared SSL. This feature allows you use your zone inHTTPS mode. You don't need your own SSL certificate, our servernetdna-ssl.com will be used. | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Pull Zone ID | 1.0 |
`name` | Pull Zone name | 1.0 |
`url` | Origin URL | 1.0 |
`port` | Port | 1.0 |
`ip` | Valid IP address of the Origin URL. If omitted, the servicewill try to lookup the IP automatically. | 1.0 |
`compress` | On the fly compression of your files served from our edges.GZip compression for the following file types: text/plain,text/html, text/javascript, text/css, text/xml,application/javascript, application/x-javascript, application/xml,text/x-component, application/json, application/xhtml+xml,application/rss+xml, application/atom+xml, app/vnd.ms-fontobject,image/svg+xml, application/x-font-ttf, font/opentype | 1.0 |
`backend_compress` | Allow us to cache compressed versions of your files from theorigin. GZip compression for the following file types: text/plain,text/html, text/javascript, text/css, text/xml,application/javascript, application/x-javascript, application/xml,text/x-component, application/json, application/xhtml+xml,application/rss+xml, application/atom+xml, app/vnd.ms-fontobject,image/svg+xml, application/x-font-ttf, font/opentype | 1.0 |
`queries` | Treat Query Strings as a separate cacheable item | 1.0 |
`set_host_header` | The URL sent as the Host in all HTTP Response Headers | 1.0 |
`cache_valid` | Ignore the origin Cache-Control Header and set every request tohave a Max-Age of 1d, 7d, 1M or 12M | 1.0 |
`ignore_setcookie_header` | Ignore any cookies set by the origin in order to make thecontent consistently cacheable | 1.0 |
`ignore_cache_control` | Ignore any max age values set by the origin and use the CDN setvalue instead | 1.0 |
`use_stale` | Serve expired content while fetching new content. This willalso cause the CDN to serve expired content in cases where theorigin is down or the file is not found | 1.0 |
`proxy_cache_lock` | When multiple requests for an uncached file are received, theywill wait until the first response is received rather than sendingeach request back to the origin | 1.0 |
`label` | Something that describes your zone | 1.0 |
`valid_referers` | List of domains for http referrer protection (separated byspace). Only the domains in the list will be treated as validreferrers | 1.0 |
`expires` | Set any request with a no "Cache-Control header" from theorigin to stay on the server. Possible values are 1d, 7d, 1M,12M | 1.0 |
`disallow_robots` | Enable robots.txt | 1.0 |
`disallow_robots_txt` | Use custom robots.txt | 1.0 |
`canonical_link_headers` | Pass the canonical URL in the Link HTTP Header | 1.0 |
`content_disposition` | Force files to download | 1.0 |
`pseudo_streaming` | Enable the zone for pseudo streaming content | 1.0 |
`sslshared` | Enable Shared SSL. This feature allows you use your zone inHTTPS mode. You don't need your own SSL certificate, our servernetdna-ssl.com will be used. | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |


### Code Samples

<ul class="nav nav-tabs" id="myTab17">
  <li class="active"><a href="#ruby17" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python17" data-toggle='tab'>Python</a></li>
  <li><a href="#php17" data-toggle='tab'>PHP</a></li>
  <li><a href="#node17" data-toggle='tab'>Node</a></li>
  <li><a href="#response17" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby17">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python17">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php17">
  	<pre>
$id = '96167';
$params = array("label"=>"Some other description");
$api->put('/zones/pull.json/'.$id, $params);</pre>
  </div>
  <div class="tab-pane" id="node17">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response17">
		<pre>
{"code":200,"data":
	{"pullzone":
		{"id":"97167","name":"newpullzone","url":"http:\/\/somedomain.net","port":"80","ip":"127.0.0.1","type":"2","compress":"0","backend_compress":"0","queries":"1","suspend":"0","cache_valid":"1d","label":"Some other description","inactive":"0","valid_referers":null,"expires":null,"disallow_robots":"0","disallow_robots_txt":null,"canonical_link_headers":"0","content_disposition":"0","locked":"0","server_id":"18","sslshared":"0","creation_date":"2013-05-23 19:38:30","set_host_header":null,"dns_check":"1","ignore_setcookie_header":"0","hide_setcookie_header":"0","ignore_cache_control":"0","use_stale":"0","proxy_cache_lock":"0","pseudo_streaming":"0","upstream_enabled":"0","cdn_url":"newpullzone2.alias.netdna-cdn.com","tmp_url":"newpullzone2.alias.netdna-cdn.com"}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab17 a:last').tab('show');
  })
</script>

---


## Delete Pull Zone

Deletes a pull zone specified by the {zone_id} parameter

<div class="heading">
<div class="url DELETE"><span class="http_method">DELETE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull.json/{zone_id}</span></div>
</div>


### Code Samples

<ul class="nav nav-tabs" id="myTab18">
  <li class="active"><a href="#ruby18" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python18" data-toggle='tab'>Python</a></li>
  <li><a href="#php18" data-toggle='tab'>PHP</a></li>
  <li><a href="#node18" data-toggle='tab'>Node</a></li>
  <li><a href="#response18" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby18">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python18">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php18">
  	<pre>
$id = '97167';
$api->delete('/zones/pull.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node18">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response18">
		<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab18 a:last').tab('show');
  })
</script>

---


## Enable Pull Zone

Enables a pull zone specified by the {zone_id} parameter

<div class="heading">
<div class="url ENABLE"><span class="http_method">ENABLE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull.json/{zone_id}</span></div>
</div>


### Code Samples

<ul class="nav nav-tabs" id="myTab19">
  <li class="active"><a href="#ruby19" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python19" data-toggle='tab'>Python</a></li>
  <li><a href="#php19" data-toggle='tab'>PHP</a></li>
  <li><a href="#node19" data-toggle='tab'>Node</a></li>
  <li><a href="#response19" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby19">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python19">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php19">
  	<pre>
$id = '97167';
$api->enable('/zones/pull.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node19">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response19">
		<pre>
</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab19 a:last').tab('show');
  })
</script>

---


## Disable Pull Zone

Disables a pull zone specified by the {zone_id} parameter

<div class="heading">
<div class="url DISABLE"><span class="http_method">DISABLE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull.json/{zone_id}</span></div>
</div>


### Code Samples

<ul class="nav nav-tabs" id="myTab20">
  <li class="active"><a href="#ruby20" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python20" data-toggle='tab'>Python</a></li>
  <li><a href="#php20" data-toggle='tab'>PHP</a></li>
  <li><a href="#node20" data-toggle='tab'>Node</a></li>
  <li><a href="#response20" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby20">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python20">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php20">
  	<pre>
$id = '97167';
$api->disable('/zones/pull.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node20">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response20">
		<pre>
</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab20 a:last').tab('show');
  })
</script>

---


## Purge Cache

Purges pull zone cache

<div class="heading">
<div class="url DELETE"><span class="http_method">DELETE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull.json/{zone_id}/cache</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`files` | - | An array containing relative paths of the files to purge (i.e./favicon.ico) | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab21">
  <li class="active"><a href="#ruby21" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python21" data-toggle='tab'>Python</a></li>
  <li><a href="#php21" data-toggle='tab'>PHP</a></li>
  <li><a href="#node21" data-toggle='tab'>Node</a></li>
  <li><a href="#response21" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby21">
	<pre>
api.purge(zone_id)
api.purge(zone_id, '/some_file')
api.purge(zone_id, ['/some_file', '/another_file'])</pre>
  </div>
  <div class="tab-pane" id="python21">
	<pre>
from netdnarws import NetDNA
api = NetDNA("myalias", "consumer_key", "consumer_secret")
api.delete("/zones/pull.json/zone_id/cache")
api.delete("/zones/pull.json/zone_id/cache", data={'file': '/my-file.png'})</pre>
	</div>
  <div class="tab-pane" id="php21">
  	<pre>
$id = '97167';
$params = array('file' => '/robots.txt');
$api->delete('/zones/pull.json/'.$id.'/cache', $params);</pre>
  </div>
  <div class="tab-pane" id="node21">
	<pre>
var netdna = require('netdna')({
	companyAlias: 'alias'
	, consumerKey: 'key'
	, consumerSecret: 'secret'
})
netdna.del('/zones/pull.json/zone_id', callback)
function callback(err, response) {
  if (err) return console.log(err)
  console.log(response)
}</pre>
  </div>
  <div class="tab-pane" id="response21">
	<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab21 a:last').tab('show');
  })
</script>

---

# Pull Zone Custom Domains API

## List Custom Domains

Returns a list of all custom domains on the zone specified by
{zone_id}

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull/{zone_id}/customdomains.json</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The id of the custom domain | 1.0 |
`bucket_id` | The id of the zone the custom domain belongs to | 1.0 |
`custom_domain` | A valid custom domain | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab22">
  <li class="active"><a href="#ruby22" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python22" data-toggle='tab'>Python</a></li>
  <li><a href="#php22" data-toggle='tab'>PHP</a></li>
  <li><a href="#node22" data-toggle='tab'>Node</a></li>
  <li><a href="#response22" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby22">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python22">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php22">
  	<pre>
$id = '96061';
$api->get('/zones/pull/'.$id.'/customdomains.json');</pre>
  </div>
  <div class="tab-pane" id="node22">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response22">
		<pre>
{"code":200,"data":
	{"total":1,"customdomains":
		[
			{"id":"79182","bucket_id":"97167","custom_domain":"cdn.somedomain3.com","type":null}
		]
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab22 a:last').tab('show');
  })
</script>

---


## Create Custom Domain

Adds a new custom domain to {zone_id}

<div class="heading">
<div class="url POST"><span class="http_method">POST</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull/{zone_id}/customdomains.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`custom_domain` | - | <span class="label important">required</span><br />length: 1-255 chars, valid::custom_domain, !valid::full_domain | A valid custom domain | 1.0 |
`type` | - | Applies only to Vod Zones and must be either 'vod-rtmp','vod-pseudo', 'vod-direct', or 'vod-ftp' | The type of custom domain being created | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The id of the custom domain | 1.0 |
`bucket_id` | The id of the zone the custom domain belongs to | 1.0 |
`custom_domain` | The valid custom domain | 1.0 |


### Code Samples

<ul class="nav nav-tabs" id="myTab23">
  <li class="active"><a href="#ruby23" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python23" data-toggle='tab'>Python</a></li>
  <li><a href="#php23" data-toggle='tab'>PHP</a></li>
  <li><a href="#node23" data-toggle='tab'>Node</a></li>
  <li><a href="#response23" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby23">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python23">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php23">
  	<pre>
$id = '97167';
$params = array("custom_domain"=>"cdn.somedomain3.com");
$api->post('/zones/pull/'.$id.'/customdomains.json', $params);</pre>
  </div>
  <div class="tab-pane" id="node23">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response23">
		<pre>
{"code":201,"data":
	{"customdomain":
		{"id":79182,"bucket_id":"97167","custom_domain":"cdn.somedomain3.com","type":null}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab23 a:last').tab('show');
  })
</script>

---

## Get Custom Domain

Gets a custom domain specified by the {zone_id} and
{customdomain_id} parameters

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull/{zone_id}/customdomains.json/{customdomain_id}</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The id of the custom domain | 1.0 |
`bucket_id` | The id of the zone the custom domain belongs to | 1.0 |
`custom_domain` | The valid custom domain | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab24">
  <li class="active"><a href="#ruby24" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python24" data-toggle='tab'>Python</a></li>
  <li><a href="#php24" data-toggle='tab'>PHP</a></li>
  <li><a href="#node24" data-toggle='tab'>Node</a></li>
  <li><a href="#response24" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby24">
		<pre>
		</pre>
  </div>
  <div class="tab-pane" id="python24">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php24">
  	<pre>
$zoneId = '97167';
$domainId = '79182';
$api->get('/zones/pull/'.$zoneId.'/customdomains.json/'.$domainId);</pre>
  </div>
  <div class="tab-pane" id="node24">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response24">
		<pre>
{"code":200,"data":
	{"customdomain":
		{"id":"79182","bucket_id":"97167","custom_domain":"cdn.somedomain3.com","type":null}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab24 a:last').tab('show');
  })
</script>

---


## Update Custom Domain

Updates a custom domain specified by the id parameter

<div class="heading">
<div class="url PUT"><span class="http_method">PUT</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull/{zone_id}/customdomains.json/{customdomain_id}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`custom_domain` | - | <span class="label important">required</span><br />length: 1-255 chars, valid::custom_domain, !valid::full_domain | A new valid custom domain | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The id of the custom domain | 1.0 |
`bucket_id` | The id of the zone the custom domain belongs to | 1.0 |
`custom_domain` | The new valid custom domain | 1.0 |


### Code Samples

<ul class="nav nav-tabs" id="myTab25">
  <li class="active"><a href="#ruby25" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python25" data-toggle='tab'>Python</a></li>
  <li><a href="#php25" data-toggle='tab'>PHP</a></li>
  <li><a href="#node25" data-toggle='tab'>Node</a></li>
  <li><a href="#response25" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby25">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python25">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php25">
  	<pre>
$zoneId = '97167';
$domainId = '79182';
$params = array("custom_domain"=>"cdn.somenewdomain.com");
$response =  $api->put('/zones/pull/'.$zoneId.'/customdomains.json/'.$domainId, $params);</pre>
  </div>
  <div class="tab-pane" id="node25">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response25">
		<pre>
{"code":200,"data":
	{"customdomain":
		{"id":"79182","bucket_id":"97167","custom_domain":"cdn.somenewdomain.com","type":null}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab25 a:last').tab('show');
  })
</script>

---


## Delete Custom Domain

Deletes a custom domain specified by the {zone_id} and
{customdomain_id} parameters

<div class="heading">
<div class="url DELETE"><span class="http_method">DELETE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/pull/{zone_id}/customdomains.json/{customdomain_id}</span></div>
</div>


### Code Samples

<ul class="nav nav-tabs" id="myTab26">
  <li class="active"><a href="#ruby26" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python26" data-toggle='tab'>Python</a></li>
  <li><a href="#php26" data-toggle='tab'>PHP</a></li>
  <li><a href="#node26" data-toggle='tab'>Node</a></li>
  <li><a href="#response26" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby26">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python26">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php26">
  	<pre>
$zoneId = '97167';
$domainId = '79182';
$api->delete('/zones/pull/'.$zoneId.'/customdomains.json/'.$domainId);</pre>
  </div>
  <div class="tab-pane" id="node26">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response26">
		<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab26 a:last').tab('show');
  })
</script>

---

# Push Zone API

## List Push Zones

Returns a list of all push zones on the specified account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/push.json</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Push Zone ID | 1.0 |
`name` | Push Zone name | 1.0 |
`label` | Something that describes your zone | 1.0 |
`valid_referers` | List of domains for http referrer protection (separated byspace). Only the domains in the list will be treated as validreferrers | 1.0 |
`content_disposition` | Force files to download | 1.0 |
`sslshared` | Enable Shared SSL. This feature allows you use your zone inHTTPS mode. You don't need your own SSL certificate, our servernetdna-ssl.com will be used. | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab27">
  <li class="active"><a href="#ruby27" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python27" data-toggle='tab'>Python</a></li>
  <li><a href="#php27" data-toggle='tab'>PHP</a></li>
  <li><a href="#node27" data-toggle='tab'>Node</a></li>
  <li><a href="#response27" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby27">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python27">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php27">
  	<pre>
$api->get('/zones/push.json');</pre>
  </div>
  <div class="tab-pane" id="node27">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response27">
		<pre>
{"code":200,"data":
	{"page":1,"pages":1,"page_size":"50","current_page_size":1,"total":1,"pushzones":
		[
			{"id":"96182","name":"newpushzone2","type":"3","compress":"0","suspend":"0","label":null,"inactive":"0","valid_referers":null,"expires":null,"content_disposition":"0","locked":"0","server_id":"11","sslshared":"0","creation_date":"2013-05-16 15:25:19","cdn_url":"cdn.somedomain.net","tmp_url":"newpushzone2.alias.netdna-cdn.com","ftp_url":"ftp.newpushzone2.alias.netdna-cdn.com","storage_used":"20480","storage_updated":"2013-05-23 18:31:54"}
		]
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab27 a:last').tab('show');
  })
</script>

---


## Create Push Zone

Creates a new push zone

<div class="heading">
<div class="url POST"><span class="http_method">POST</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/push.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`name` | - | <span class="label important">required</span><br />length: 3-30 chars; only letters, digits, and dash (-)accepted | Push Zone name | 1.0 |
`password` | - | <span class="label important">required</span><br />length: 5-30 chars; | Push Zone FTP password | 1.0 |
`label` | - | length: 1-255 chars | Something that describes your zone | 1.0 |
`valid_referers` | - | length: 1-200 chars | List of domains for http referrer protection (separated byspace). Only the domains in the list will be treated as validreferrers | 1.0 |
`content_disposition` | 0 | only 0 or 1 accepted | Force files to download | 1.0 |
`sslshared` | 0 | only 0 or 1 accepted | Enable Shared SSL. This feature allows you use your zone inHTTPS mode. You don't need your own SSL certificate, our servernetdna-ssl.com will be used. | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Push Zone ID | 1.0 |
`name` | Push Zone name | 1.0 |
`label` | Something that describes your zone | 1.0 |
`valid_referers` | List of domains for http referrer protection (separated byspace). Only the domains in the list will be treated as validreferrers | 1.0 |
`content_disposition` | Force files to download | 1.0 |
`sslshared` | Enable Shared SSL. This feature allows you use your zone inHTTPS mode. You don't need your own SSL certificate, our servernetdna-ssl.com will be used. | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab28">
  <li class="active"><a href="#ruby28" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python28" data-toggle='tab'>Python</a></li>
  <li><a href="#php28" data-toggle='tab'>PHP</a></li>
  <li><a href="#node28" data-toggle='tab'>Node</a></li>
  <li><a href="#response28" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby28">
		<pre>
		</pre>
  </div>
  <div class="tab-pane" id="python28">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php28">
  	<pre>
$params = array("name"=>"newPushZone","password"=>"password");
$api->post('/zones/push.json', $params);</pre>
  </div>
  <div class="tab-pane" id="node28">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response28">
		<pre>
{"code":201,"data":
	{"pushzone":
		{"id":97181,"name":"newpushzone","type":3,"compress":0,"suspend":0,"label":null,"inactive":0,"valid_referers":null,"expires":null,"content_disposition":0,"locked":0,"server_id":"11","sslshared":null,"creation_date":"2013-05-23 21:01:39","cdn_url":"newpushzone.alias.netdna-cdn.com","tmp_url":"newpushzone.alias.netdna-cdn.com","ftp_url":"ftp.newpushzone.alias.netdna-cdn.com","storage_used":null,"storage_updated":null}
	}
}
</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab28 a:last').tab('show');
  })
</script>

---


## Get Push Zones Count

Counts all push zones on the specified account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/push.json/count</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`count` | The number of push zones on the specified account | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab29">
  <li class="active"><a href="#ruby29" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python29" data-toggle='tab'>Python</a></li>
  <li><a href="#php29" data-toggle='tab'>PHP</a></li>
  <li><a href="#node29" data-toggle='tab'>Node</a></li>
  <li><a href="#response29" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby29">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python29">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php29">
  	<pre>
$api->get('/zones/push.json/count');</pre>
  </div>
  <div class="tab-pane" id="node29">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response29">
		<pre>
{"code":200,"data":
	{"count":"3"}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab29 a:last').tab('show');
  })
</script>

---


## Get Push Zone

Gets a push zone specified by the {zone_id} parameter

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/push.json/{zone_id}</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Push Zone ID | 1.0 |
`name` | Push Zone name | 1.0 |
`label` | Something that describes your zone | 1.0 |
`valid_referers` | List of domains for http referrer protection (separated byspace). Only the domains in the list will be treated as validreferrers | 1.0 |
`content_disposition` | Force files to download | 1.0 |
`sslshared` | Enable Shared SSL. This feature allows you use your zone inHTTPS mode. You don't need your own SSL certificate, our servernetdna-ssl.com will be used. | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab30">
  <li class="active"><a href="#ruby30" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python30" data-toggle='tab'>Python</a></li>
  <li><a href="#php30" data-toggle='tab'>PHP</a></li>
  <li><a href="#node30" data-toggle='tab'>Node</a></li>
  <li><a href="#response30" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby30">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python30">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php30">
  	<pre>
$id = '97181';
$api->get('/zones/push.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node30">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response30">
		<pre>
{"code":200,"data":
	{"pushzone":
		{"id":"97181","name":"newpushzone3","type":"3","compress":"0","suspend":"0","label":null,"inactive":"0","valid_referers":null,"expires":null,"content_disposition":"0","locked":"0","server_id":"11","sslshared":"0","creation_date":"2013-05-23 21:01:39","cdn_url":"newpushzone3.alias.netdna-cdn.com","tmp_url":"newpushzone3.alias.netdna-cdn.com","ftp_url":"ftp.newpushzone3.alias.netdna-cdn.com","storage_used":null,"storage_updated":null}
	}
}
</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab30 a:last').tab('show');
  })
</script>

---


## Update Push Zone

Updates a push zone specified by the {zone_id} parameter

<div class="heading">
<div class="url PUT"><span class="http_method">PUT</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/push.json/{zone_id}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`label` | - | length: 1-255 chars | Something that describes your zone | 1.0 |
`valid_referers` | - | length: 1-100 chars | List of domains for http referrer protection (separated byspace). Only the domains in the list will be treated as validreferrers | 1.0 |
`content_disposition` | 0 | only 0 or 1 accepted | Force files to download | 1.0 |
`sslshared` | 0 | only 0 or 1 accepted | Enable Shared SSL. This feature allows you use your zone inHTTPS mode. You don't need your own SSL certificate, our servernetdna-ssl.com will be used. | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Push Zone ID | 1.0 |
`name` | Push Zone name | 1.0 |
`label` | Something that describes your zone | 1.0 |
`valid_referers` | List of domains for http referrer protection (separated byspace). Only the domains in the list will be treated as validreferrers | 1.0 |
`content_disposition` | Force files to download | 1.0 |
`sslshared` | Enable Shared SSL. This feature allows you use your zone inHTTPS mode. You don't need your own SSL certificate, our servernetdna-ssl.com will be used. | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab31">
  <li class="active"><a href="#ruby31" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python31" data-toggle='tab'>Python</a></li>
  <li><a href="#php31" data-toggle='tab'>PHP</a></li>
  <li><a href="#node31" data-toggle='tab'>Node</a></li>
  <li><a href="#response31" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby31">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python31">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php31">
  	<pre>
$id = '97181';
$params = array("label"=>"Some other description");
$api->put('/zones/push.json/'.$id, $params);</pre>
  </div>
  <div class="tab-pane" id="node31">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response31">
		<pre>
{"code":200,"data":
	{"pushzone":
		{"id":"97181","name":"newpushzone3","type":"3","compress":"0","suspend":"0","label":"Some other description","inactive":"0","valid_referers":null,"expires":null,"content_disposition":"0","locked":"0","server_id":"11","sslshared":"0","creation_date":"2013-05-23 21:01:39","cdn_url":"newpushzone3.alias.netdna-cdn.com","tmp_url":"newpushzone3.alias.netdna-cdn.com","ftp_url":"ftp.newpushzone3.alias.netdna-cdn.com","storage_used":null,"storage_updated":null}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab31 a:last').tab('show');
  })
</script>

---


## Delete Push Zone

Deletes a push zone specified by the {zone_id} parameter

<div class="heading">
<div class="url DELETE"><span class="http_method">DELETE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/push.json/{zone_id}</span></div>
</div>

### Code Samples

<ul class="nav nav-tabs" id="myTab32">
  <li class="active"><a href="#ruby32" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python32" data-toggle='tab'>Python</a></li>
  <li><a href="#php32" data-toggle='tab'>PHP</a></li>
  <li><a href="#node32" data-toggle='tab'>Node</a></li>
  <li><a href="#response32" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby32">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python32">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php32">
  	<pre>
$id = '97181';
$api->delete('/zones/push.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node32">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response32">
		<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab32 a:last').tab('show');
  })
</script>

---


## Enable Push Zone

Enables a push zone specified by the {zone_id} parameter

<div class="heading">
<div class="url ENABLE"><span class="http_method">ENABLE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/push.json/{zone_id}</span></div>
</div>

### Code Samples

<ul class="nav nav-tabs" id="myTab33">
  <li class="active"><a href="#ruby33" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python33" data-toggle='tab'>Python</a></li>
  <li><a href="#php33" data-toggle='tab'>PHP</a></li>
  <li><a href="#node33" data-toggle='tab'>Node</a></li>
  <li><a href="#response33" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby33">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python33">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php33">
  	<pre>
$id = '97181';
$api->enable('/zones/push.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node33">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response33">
		<pre>
No response</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab33 a:last').tab('show');
  })
</script>

---


## Disable Push Zone

Disables a push zone specified by the {zone_id} parameter

<div class="heading">
<div class="url DISABLE"><span class="http_method">DISABLE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/push.json/{zone_id}</span></div>
</div>


### Code Samples

<ul class="nav nav-tabs" id="myTab34">
  <li class="active"><a href="#ruby34" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python34" data-toggle='tab'>Python</a></li>
  <li><a href="#php34" data-toggle='tab'>PHP</a></li>
  <li><a href="#node34" data-toggle='tab'>Node</a></li>
  <li><a href="#response34" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby34">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python34">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php34">
  	<pre>
$id = '97181';
$api->disable('/zones/push.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node34">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response34">
		<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab34 a:last').tab('show');
  })
</script>


---

# Push Zone Custom Domains API

## List Custom Domains

Returns a list of all custom domains on the zone specified by
{zone_id}

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/push/{zone_id}/customdomains.json</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The id of the custom domain | 1.0 |
`bucket_id` | The id of the zone the custom domain belongs to | 1.0 |
`custom_domain` | A valid custom domain | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab35">
  <li class="active"><a href="#ruby35" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python35" data-toggle='tab'>Python</a></li>
  <li><a href="#php35" data-toggle='tab'>PHP</a></li>
  <li><a href="#node35" data-toggle='tab'>Node</a></li>
  <li><a href="#response35" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby35">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python35">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php35">
  	<pre>
$id = '96061';
$api->get('/zones/push/'.$id.'/customdomains.json');</pre>
  </div>
  <div class="tab-pane" id="node35">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response35">
		<pre>
{"code":200,"data":
	{"total":1,"customdomains":
		[
			{"id":"78330","bucket_id":"96061","custom_domain":"cdn.somedomain.com","type":null}
		]
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab35 a:last').tab('show');
  })
</script>

---


## Create Custom Domain

Adds a new custom domain to {zone_id}

<div class="heading">
<div class="url POST"><span class="http_method">POST</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/push/{zone_id}/customdomains.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`custom_domain` | - | <span class="label important">required</span><br />length: 1-255 chars, valid::custom_domain, !valid::full_domain | A valid custom domain | 1.0 |
`type` | - | Applies only to Vod Zones and must be either 'vod-rtmp','vod-pseudo', 'vod-direct', or 'vod-ftp' | The type of custom domain being created | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The id of the custom domain | 1.0 |
`bucket_id` | The id of the zone the custom domain belongs to | 1.0 |
`custom_domain` | The valid custom domain | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab36">
  <li class="active"><a href="#ruby36" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python36" data-toggle='tab'>Python</a></li>
  <li><a href="#php36" data-toggle='tab'>PHP</a></li>
  <li><a href="#node36" data-toggle='tab'>Node</a></li>
  <li><a href="#response36" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby36">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python36">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php36">
  	<pre>
$id = '97181';
$params = array("custom_domain"=>"cdn.somedomain2.net");
$api->post('/zones/push/'.$id.'/customdomains.json', $params);</pre>
  </div>
  <div class="tab-pane" id="node36">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response36">
		<pre>
{"code":201,"data":
	{"customdomain":
		{"id":79188,"bucket_id":"97181","custom_domain":"cdn.somedomain3.net","type":null}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab36 a:last').tab('show');
  })
</script>

---


## Get Custom Domain

Gets a custom domain specified by the {zone_id} and
{customdomain_id} parameters

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/push/{zone_id}/customdomains.json/{customdomain_id}</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The id of the custom domain | 1.0 |
`bucket_id` | The id of the zone the custom domain belongs to | 1.0 |
`custom_domain` | The valid custom domain | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab37">
  <li class="active"><a href="#ruby37" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python37" data-toggle='tab'>Python</a></li>
  <li><a href="#php37" data-toggle='tab'>PHP</a></li>
  <li><a href="#node37" data-toggle='tab'>Node</a></li>
  <li><a href="#response37" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby37">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python37">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php37">
  	<pre>
$zoneId = '97181';
$domainId = '79188';
$api->get('/zones/push/'.$zoneId.'/customdomains.json/'.$domainId);</pre>
  </div>
  <div class="tab-pane" id="node37">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response37">
		<pre>
{"code":200,"data":
	{"customdomain":
		{"id":"79188","bucket_id":"97181","custom_domain":"cdn.somedomain3.net","type":null}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab37 a:last').tab('show');
  })
</script>

---


## Update Custom Domain

Updates a custom domain specified by the id parameter

<div class="heading">
<div class="url PUT"><span class="http_method">PUT</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/push/{zone_id}/customdomains.json/{customdomain_id}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`custom_domain` | - | <span class="label important">required</span><br />length: 1-255 chars, valid::custom_domain, !valid::full_domain | A new valid custom domain | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The id of the custom domain | 1.0 |
`bucket_id` | The id of the zone the custom domain belongs to | 1.0 |
`custom_domain` | The new valid custom domain | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab38">
  <li class="active"><a href="#ruby38" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python38" data-toggle='tab'>Python</a></li>
  <li><a href="#php38" data-toggle='tab'>PHP</a></li>
  <li><a href="#node38" data-toggle='tab'>Node</a></li>
  <li><a href="#response38" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby38">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python38">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php38">
  	<pre>
$zoneId = '97181';
$domainId = '79188';
$params = array("custom_domain"=>"cdn.somenewdomain2.com");
$api->put('/zones/push/'.$zoneId.'/customdomains.json/'.$domainId, $params);
</pre>
  </div>
  <div class="tab-pane" id="node38">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response38">
		<pre>
{"code":200,"data":
	{"customdomain":
		{"id":"79188","bucket_id":"97181","custom_domain":"cdn.somenewdomain2.com","type":null}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab38 a:last').tab('show');
  })
</script>

---


## Delete Custom Domain

Deletes a custom domain specified by the {zone_id} and
{customdomain_id} parameters

<div class="heading">
<div class="url DELETE"><span class="http_method">DELETE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/push/{zone_id}/customdomains.json/{customdomain_id}</span></div>
</div>


### Code Samples

<ul class="nav nav-tabs" id="myTab39">
  <li class="active"><a href="#ruby39" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python39" data-toggle='tab'>Python</a></li>
  <li><a href="#php39" data-toggle='tab'>PHP</a></li>
  <li><a href="#node39" data-toggle='tab'>Node</a></li>
  <li><a href="#response39" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby39">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python39">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php39">
  	<pre>
$zoneId = '97181';
$domainId = '79188';
$api->delete('/zones/push/'.$zoneId.'/customdomains.json/'.$domainId);</pre>
  </div>
  <div class="tab-pane" id="node39">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response39">
		<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab39 a:last').tab('show');
  })
</script>


---

# VOD Zone API

## List VOD Zones

Returns a list of all VOD zones on the specified account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/vod.json</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | VOD Zone ID | 1.0 |
`name` | VOD Zone name | 1.0 |
`label` | The zone's description | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab40">
  <li class="active"><a href="#ruby40" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python40" data-toggle='tab'>Python</a></li>
  <li><a href="#php40" data-toggle='tab'>PHP</a></li>
  <li><a href="#node40" data-toggle='tab'>Node</a></li>
  <li><a href="#response40" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby40">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python40">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php40">
  	<pre>
$api->get('/zones/vod.json');</pre>
  </div>
  <div class="tab-pane" id="node40">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response40">
		<pre>
{"code":200,"data":
	{"page":1,"pages":1,"page_size":"50","current_page_size":1,"total":1,"vodzones":
		[
			{"id":"96187","name":"newvodzone","type":"4","suspend":"0","label":null,"inactive":"0","token":null,"locked":"0","server_id":"30","creation_date":"2013-05-16 16:02:35","cdn_url":"cdn.somedomain.com","tmp_url":"newvodzone.alias.netdna-cdn.com","rtmp_url":"r.newvodzone.alias.netdna-cdn.com","pseudo_url":"p.newvodzone.alias.netdna-cdn.com","direct_url":"d.newvodzone.alias.netdna-cdn.com","ftp_url":"ftp.newvodzone.alias.netdna-cdn.com","storage_used":"4096","storage_updated":"2013-05-23 18:52:08"}
		]
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab40 a:last').tab('show');
  })
</script>

---


## Create VOD Zone

Creates a new VOD zone

<div class="heading">
<div class="url POST"><span class="http_method">POST</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/vod.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`name` | - | <span class="label important">required</span><br />length: 3-30 chars; only letters, digits, and dash (-)accepted | VOD Zone user name | 1.0 |
`password` | - | <span class="label important">required</span><br />length: 5-30 chars | Your desired password | 1.0 |
`token` | - | length: 1-64 chars | The token value (shared secret) for secure streaming | 1.0 |
`label` | - | length: 1-255 chars | Something that describes your zone | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | VOD Zone ID | 1.0 |
`name` | VOD Zone name | 1.0 |
`label` | The zone's description | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab41">
  <li class="active"><a href="#ruby41" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python41" data-toggle='tab'>Python</a></li>
  <li><a href="#php41" data-toggle='tab'>PHP</a></li>
  <li><a href="#node41" data-toggle='tab'>Node</a></li>
  <li><a href="#response41" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby41">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python41">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php41">
  	<pre>
$params = array("name"=>"newVODZone3","password"=>"password");
$response = $api->post('/zones/vod.json',$params);</pre>
  </div>
  <div class="tab-pane" id="node41">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response41">
		<pre>
{"code":201,"data":
	{"vodzone":
		{"id":97183,"name":"newvodzone3","type":4,"suspend":0,"label":null,"inactive":0,"token":null,"locked":0,"server_id":"30","creation_date":"2013-05-23 21:25:43","cdn_url":"newvodzone3.alias.netdna-cdn.com","tmp_url":"newvodzone3.alias.netdna-cdn.com","rtmp_url":"r.newvodzone3.alias.netdna-cdn.com","pseudo_url":"p.newvodzone3.alias.netdna-cdn.com","direct_url":"d.newvodzone3.alias.netdna-cdn.com","ftp_url":"ftp.newvodzone3.alias.netdna-cdn.com","storage_used":null,"storage_updated":null}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab41 a:last').tab('show');
  })
</script>

---


## Get VOD Zones Count

Counts all vod zones on the specified account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/vod.json/count</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`count` | The number of vod zones on the specified account | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab42">
  <li class="active"><a href="#ruby42" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python42" data-toggle='tab'>Python</a></li>
  <li><a href="#php42" data-toggle='tab'>PHP</a></li>
  <li><a href="#node42" data-toggle='tab'>Node</a></li>
  <li><a href="#response42" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby42">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python42">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php42">
  	<pre>
$api->get('/zones/vod.json/count');</pre>
  </div>
  <div class="tab-pane" id="node42">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response42">
		<pre>
{"code":200,"data":
	{"count":"3"}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab42 a:last').tab('show');
  })
</script>

---


## Get VOD Zone

Gets a VOD zone specified by the {zone_id} parameter

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/vod.json/{zone_id}</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | VOD Zone ID | 1.0 |
`name` | VOD Zone name | 1.0 |
`label` | The zone's description | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab43">
  <li class="active"><a href="#ruby43" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python43" data-toggle='tab'>Python</a></li>
  <li><a href="#php43" data-toggle='tab'>PHP</a></li>
  <li><a href="#node43" data-toggle='tab'>Node</a></li>
  <li><a href="#response43" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby43">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python43">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php43">
  	<pre>
$id = '97183';
$api->get('/zones/vod.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node43">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response43">
		<pre>
{"code":200,"data":
	{"vodzone":
		{"id":"97183","name":"newvodzone3","type":"4","suspend":"0","label":null,"inactive":"0","token":null,"locked":"0","server_id":"30","creation_date":"2013-05-23 21:25:44","cdn_url":"newvodzone3.alias.netdna-cdn.com","tmp_url":"newvodzone3.alias.netdna-cdn.com","rtmp_url":"r.newvodzone3.alias.netdna-cdn.com","pseudo_url":"p.newvodzone3.alias.netdna-cdn.com","direct_url":"d.newvodzone3.alias.netdna-cdn.com","ftp_url":"ftp.newvodzone3.alias.netdna-cdn.com","storage_used":null,"storage_updated":null}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab43 a:last').tab('show');
  })
</script>

---


## Update VOD Zone

Updates a VOD zone specified by the {zone_id} parameter

<div class="heading">
<div class="url PUT"><span class="http_method">PUT</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/vod.json/{zone_id}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`password` | - | length: 5-30 chars | Your desired password | 1.0 |
`token` | - | length: 1-64 chars | The token value (shared secret) for secure streaming | 1.0 |
`label` | - | length: 1-255 chars | Something that describes your zone | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | VOD Zone ID | 1.0 |
`name` | VOD Zone name | 1.0 |
`label` | The zone's description | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab44">
  <li class="active"><a href="#ruby44" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python44" data-toggle='tab'>Python</a></li>
  <li><a href="#php44" data-toggle='tab'>PHP</a></li>
  <li><a href="#node44" data-toggle='tab'>Node</a></li>
  <li><a href="#response44" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby44">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python44">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php44">
  	<pre>
$id = '97183';
$params =  array("label"=>"Some other description");
$api->put('/zones/vod.json/'.$id,$params);</pre>
  </div>
  <div class="tab-pane" id="node44">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response44">
		<pre>
{"code":200,"data":
	{"vodzone":
		{"id":"97183","name":"newvodzone3","type":"4","suspend":"0","label":"Some other description","inactive":"0","token":null,"locked":"0","server_id":"30","creation_date":"2013-05-23 21:25:44","cdn_url":"newvodzone3.alias.netdna-cdn.com","tmp_url":"newvodzone3.alias.netdna-cdn.com","rtmp_url":"r.newvodzone3.alias.netdna-cdn.com","pseudo_url":"p.newvodzone3.alias.netdna-cdn.com","direct_url":"d.newvodzone3.alias.netdna-cdn.com","ftp_url":"ftp.newvodzone3.alias.netdna-cdn.com","storage_used":null,"storage_updated":null}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab44 a:last').tab('show');
  })
</script>

---


## Delete VOD Zone

Deletes a VOD zone specified by the {zone_id} parameter

<div class="heading">
<div class="url DELETE"><span class="http_method">DELETE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/vod.json/{zone_id}</span></div>
</div>

### Code Samples

<ul class="nav nav-tabs" id="myTab45">
  <li class="active"><a href="#ruby45" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python45" data-toggle='tab'>Python</a></li>
  <li><a href="#php45" data-toggle='tab'>PHP</a></li>
  <li><a href="#node45" data-toggle='tab'>Node</a></li>
  <li><a href="#response45" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby45">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python45">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php45">
  	<pre>
$id = '97183';
$api->delete('/zones/vod.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node45">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response45">
		<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Enable VOD Zone

Enables a VOD zone specified by the {zone_id} parameter

<div class="heading">
<div class="url ENABLE"><span class="http_method">ENABLE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/vod.json/{zone_id}</span></div>
</div>

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$id = '96187';
$api->enable('/zones/vod.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Disable VOD Zone

Disables a VOD zone specified by the {zone_id} parameter

<div class="heading">
<div class="url DISABLE"><span class="http_method">DISABLE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/vod.json/{zone_id}</span></div>
</div>

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$id = '96187';
$api->disable('/zones/vod.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


# VOD Zone Custom Domains API

## List Custom Domains

Returns a list of all custom domains on the zone specified by
{zone_id}

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/vod/{zone_id}/customdomains.json</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The id of the custom domain | 1.0 |
`bucket_id` | The id of the zone the custom domain belongs to | 1.0 |
`custom_domain` | A valid custom domain | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$id = '97183';
$api->get('/zones/vod/'.$id.'/customdomains.json');</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":200,"data":
	{"total":1,"customdomains":
		[
			{"id":"79191","bucket_id":"97183","custom_domain":"cdn.somedomain2.com","type":"vod-rtmp"}
		]
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Create Custom Domain

Adds a new custom domain to {zone_id}

<div class="heading">
<div class="url POST"><span class="http_method">POST</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/vod/{zone_id}/customdomains.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`custom_domain` | - | <span class="label important">required</span><br />length: 1-255 chars, valid::custom_domain, !valid::full_domain | A valid custom domain | 1.0 |
`type` | - | Applies only to Vod Zones and must be either 'vod-rtmp','vod-pseudo', 'vod-direct', or 'vod-ftp' | The type of custom domain being created | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The id of the custom domain | 1.0 |
`bucket_id` | The id of the zone the custom domain belongs to | 1.0 |
`custom_domain` | The valid custom domain | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$id = '97183';
$params = array("custom_domain"=>"cdn.somedomain2.com","type"=>"vod-rtmp");
$api->post('/zones/vod/'.$id.'/customdomains.json', $params);</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":201,"data":
	{"customdomain":
		{"id":79191,"bucket_id":"97183","custom_domain":"cdn.somedomain2.com","type":"vod-rtmp"}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Get Custom Domain

Gets a custom domain specified by the {zone_id} and
{customdomain_id} parameters

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/vod/{zone_id}/customdomains.json/{customdomain_id}</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The id of the custom domain | 1.0 |
`bucket_id` | The id of the zone the custom domain belongs to | 1.0 |
`custom_domain` | The valid custom domain | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$zoneId = '97183';
$domainId = '79191';
$response =  $api->get('/zones/vod/'.$zoneId.'/customdomains.json/'.$domainId);</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":200,"data":
	{"customdomain":
		{"id":"79191","bucket_id":"97183","custom_domain":"cdn.somedomain2.com","type":"vod-rtmp"}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Update Custom Domain

Updates a custom domain specified by the id parameter

<div class="heading">
<div class="url PUT"><span class="http_method">PUT</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/vod/{zone_id}/customdomains.json/{customdomain_id}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`custom_domain` | - | <span class="label important">required</span><br />length: 1-255 chars, valid::custom_domain, !valid::full_domain | A new valid custom domain | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The id of the custom domain | 1.0 |
`bucket_id` | The id of the zone the custom domain belongs to | 1.0 |
`custom_domain` | The new valid custom domain | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$zoneId = '97183';
$domainId = '79191';
$params = array("custom_domain"=>"cdn.somenewdomain3.com");
$api->put('/zones/vod/'.$zoneId.'/customdomains.json/'.$domainId, $params);</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":200,"data":
	{"customdomain":
		{"id":"79191","bucket_id":"97183","custom_domain":"cdn.somenewdomain3.com","type":"vod-rtmp"}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Delete Custom Domain

Deletes a custom domain specified by the {zone_id} and
{customdomain_id} parameters

<div class="heading">
<div class="url DELETE"><span class="http_method">DELETE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/vod/{zone_id}/customdomains.json/{customdomain_id}</span></div>
</div>


### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$zoneId = '97183';
$domainId = '79191';
$api->delete('/zones/vod/'.$zoneId.'/customdomains.json/'.$domainId);</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


# Live Zone API

## List Live Zones

Returns a list of all live zones on the specified account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/live.json</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Live Zone ID | 1.0 |
`name` | Live Zone name | 1.0 |
`label` | The zone's description | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$api->get('/zones/live.json');</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":200,"data":
	{"page":1,"pages":1,"page_size":"50","current_page_size":1,"total":1,"livezones":
		[
			{"id":"96193","name":"newlivezone","type":"5","suspend":"0","label":null,"inactive":"0","locked":"0","server_id":"3","creation_date":"2013-05-16 16:23:49","cdn_url":"newlivezone.alias.netdna-cdn.com","tmp_url":"newlivezone.alias.netdna-cdn.com","pub_url":"publish.newlivezone.alias.netdna-cdn.com\/live\/96193","view_url":"newlivezone.alias.netdna-cdn.com\/live\/96193"}
		]
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Create Live Zone

Creates a new live zone

<div class="heading">
<div class="url POST"><span class="http_method">POST</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/live.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`name` | - | <span class="label important">required</span><br />length: 3-30 chars; only letters, digits, and dash (-)accepted | Your desired zone name | 1.0 |
`password` | - | length: 5-30 chars | Your desired password | 1.0 |
`label` | - | length: 1-255 chars | Something that describes your zone | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Live Zone ID | 1.0 |
`name` | Live Zone name | 1.0 |
`label` | The zone's description | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$api->post('/zones/live.json', array("name"=>"newLiveZone3","password"=>"password"));</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":201,"data":
	{"livezone":
		{"id":97185,"name":"newlivezone3","type":5,"suspend":0,"label":null,"inactive":0,"locked":0,"server_id":3,"creation_date":"2013-05-23 21:50:00","cdn_url":"newlivezone3.alias.netdna-cdn.com","tmp_url":"newlivezone3.alias.netdna-cdn.com","pub_url":"publish.newlivezone3.alias.netdna-cdn.com\/live\/97185","view_url":"newlivezone3.alias.netdna-cdn.com\/live\/97185"}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Get Live Zones Count

Counts all live zones on the specified account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/live.json/count</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`count` | The number of live zones on the specified account | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$api->get('/zones/live.json/count');</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":200,"data":
	{"count":"3"}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Get Live Zone

Gets a live zone specified by the {zone_id} parameter

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/live.json/{zone_id}</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Live Zone ID | 1.0 |
`name` | Live Zone name | 1.0 |
`label` | The zone's description | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$id = '97185';
$api->get('/zones/live.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":200,"data":
	{"livezone":
		{"id":"96194","name":"newlivezone2","type":"5","suspend":"0","label":"Some other description","inactive":"1","locked":"0","server_id":"3","creation_date":"2013-05-16 16:23:59","cdn_url":"newlivezone2.alias.netdna-cdn.com","tmp_url":"newlivezone2.alias.netdna-cdn.com","pub_url":"publish.newlivezone2.alias.netdna-cdn.com\/live\/96194","view_url":"newlivezone2.alias.netdna-cdn.com\/live\/96194"}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Update Live Zone

Updates a live zone specified by the {zone_id} parameter

<div class="heading">
<div class="url PUT"><span class="http_method">PUT</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/live.json/{zone_id}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`password` | - | length: 5-30 chars | Your desired password | 1.0 |
`token` | - | length: 1-64 chars | The token value (shared secret) for secure streaming | 1.0 |
`label` | - | length: 1-255 chars | Something that describes your zone | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Live Zone ID | 1.0 |
`name` | Live Zone name | 1.0 |
`label` | The zone's description | 1.0 |
`suspend` | Flag denoting if the zone has been suspended | 1.0 |
`locked` | Flag denoting if the zone has been locked | 1.0 |
`inactive` | Flag denoting if the zone has been deleted | 1.0 |
`creation_date` | Date Created | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$id = '97185';
$params =  array("label"=>"Some other description");
$response =  $api->put('/zones/live.json/'.$id,$params);
</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":200,"data":
	{"livezone":
		{"id":"97185","name":"newlivezone3","type":"5","suspend":"0","label":"Some other description","inactive":"0","locked":"0","server_id":"3","creation_date":"2013-05-23 21:50:00","cdn_url":"newlivezone3.alias.netdna-cdn.com","tmp_url":"newlivezone3.alias.netdna-cdn.com","pub_url":"publish.newlivezone3.alias.netdna-cdn.com\/live\/97185","view_url":"newlivezone3.alias.netdna-cdn.com\/live\/97185"}
	}
}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Delete Live Zone

Deletes a live zone specified by the {zone_id} parameter

<div class="heading">
<div class="url DELETE"><span class="http_method">DELETE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/live.json/{zone_id}</span></div>
</div>

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$id = '97185';
$api->delete('/zones/live.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Enable Live Zone

Enables a live zone specified by the {zone_id} parameter

<div class="heading">
<div class="url ENABLE"><span class="http_method">ENABLE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/live.json/{zone_id}</span></div>
</div>

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$id = '96061';
$api->enable('/zones/live.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Disable Live Zone

Disables a live zone specified by the {zone_id} parameter

<div class="heading">
<div class="url DISABLE"><span class="http_method">DISABLE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/live.json/{zone_id}</span></div>
</div>


### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$id = '96061';
api->disable('/zones/live.json/'.$id);</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
{"code":200}</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


# Zones SSL API

## Get Zone's SSL Information

Get the SSL certificate for the specified {zone_type} and
{zone_id}.

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/{zone_type}/{zone_id}/ssl.json</span></div>
</div>

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$id = '96061';
$type = 'pull';
$api->get('/zones/'.$type.'/'.$id.'/ssl.json');</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Install SSL on Zone

Upload an SSL certificate for the specified {zone_type} and
{zone_id}.

<div class="heading">
<div class="url POST"><span class="http_method">POST</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/{zone_type}/{zone_id}/ssl.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`ssl_crt` | - | <span class="label important">required</span><br /> | The SSL certificate you are installing. | 1.0 |
`ssl_key` | - | <span class="label important">required</span><br /> | The key for the SSL certificate you are installing. | 1.0 |
`ssl_cabundle` | - | The CA Bundle for the SSL Certificate you are installing. | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The SSL Certificate ID. | 1.0 |
`ssl_crt` | The SSL certificate. | 1.0 |
`ssl_key` | The SSL Private Key. | 1.0 |
`ssl_cabundle` | The CA Bundle for the cert. | 1.0 |
`domain` | The domain applicable to this certificate. | 1.0 |
`date_expiration` | The date of expiration for the certificate. | 1.0 |
`wildcard` | Flag to signify whether this is a wildcard certificate. | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$id = '96061';
$type = 'pull';
$ssl_crt = " ... ";
$params = array("ssl_crt"=>$ssl_crt,"ssl_key"=>"somesslkey");
$api->post('/zones/'.$type.'/'.$id.'/ssl.json',$params);</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Update Zone's SSL Information

Update the SSL certificate for the specified {zone_type} and
{zone_id}.

<div class="heading">
<div class="url PUT"><span class="http_method">PUT</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/{zone_type}/{zone_id}/ssl.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`ssl_crt` | - | <span class="label important">required</span><br /> | The SSL certificate you are installing. | 1.0 |
`ssl_key` | - | <span class="label important">required</span><br /> | The key for the SSL certificate you are installing. | 1.0 |
`ssl_cabundle` | - | The CABundle for the SSL Certificate you are installing. | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The SSL Certificate ID. | 1.0 |
`ssl_crt` | The SSL certificate. | 1.0 |
`ssl_key` | The SSL Private Key. | 1.0 |
`ssl_cabundle` | The CA Bundle for the cert. | 1.0 |
`domain` | The domain applicable to this certificate. | 1.0 |
`date_expiration` | The date of expiration for the certificate. | 1.0 |
`wildcard` | Flag to signify whether this is a wildcard certificate. | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$id = '96061';
$type = 'pull';
$ssl_crt = " ... ";
$params = array("ssl_crt"=>$ssl_crt,"ssl_key"=>"somesslkey");
$api->put('/zones/'.$type.'/'.$id.'/ssl.json',$params);</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Remove Zone's SSL Information

Remove the SSL certificate for the specified {zone_type} and
{zone_id}.

<div class="heading">
<div class="url DELETE"><span class="http_method">DELETE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/{zone_type}/{zone_id}/ssl.json</span></div>
</div>


### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$id = '96061';
$type = 'pull';
$api->post('/zones/'.$type.'/'.$id.'/ssl.json');</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


# Zones Upstream API

## Get Upstream information for the current zone

Get the upstream information for the specified {zone_id}.

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/{zone_type}/{zone_id}/upstream.json</span></div>
</div>

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$type = 'pull';
$id = '96061';
$api->post('/zones/'.$type.'/'.$id.'/upstream.json');</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Enable Upstream on Zone

Create and enable Upstream for a specific {zone_id}.

<div class="heading">
<div class="url POST"><span class="http_method">POST</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/{zone_type}/{zone_id}/upstream.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`server_url` | - | <span class="label important">required</span><br /> | The server url or ip to provide the streaming resources | 1.0.1 |
`port` | - | <span class="label important">required</span><br /> | The port where server is to be called | 1.0.1 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The Upstream ID. | 1.0.1 |
`bucket_id` | The bucket_id it belongs to | 1.0.1 |
`server_url` | The server url or ip | 1.0.1 |
`port` | The port it uses to call the server | 1.0.1 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$type = 'pull';
$id = '96061';
$params = array("server_url"=>"http://cdn.somedomain.com","server"=>"http://cdn.somedomain.com","port"=>"80");
$api->post('/zones/'.$type.'/'.$id.'/upstream.json');</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Update Zone's Upstream Information

Update the Upstream information for the specified {zone_id}.

<div class="heading">
<div class="url PUT"><span class="http_method">PUT</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/{zone_type}/{zone_id}/upstream.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`upstream_id` | - | <span class="label important">required</span><br /> | The Upstream Information you're modifying. | 1.0.1 |
`server_url` | - | <span class="label important">required</span><br /> | The server url or ip | 1.0.1 |
`port` | - | <span class="label important">required</span><br /> | The port it uses to call the server | 1.0.1 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | The Upstream ID. | 1.0.1 |
`bucket_id` | The bucket_id it belongs to | 1.0.1 |
`server_url` | The server url or ip | 1.0.1 |
`port` | The port it uses to call the server | 1.0.1 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$type = 'pull';
$id = '96061';
$params = array("upsream_id"=>"93013","server_url"=>"http://somedomain.net","port"=>"80");
$api->put('/zones/'.$type.'/'.$id.'/upstream.json');</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Remove Zone's Upstream Information

Remove the Upstream Information for the specified {zone_id}.

<div class="heading">
<div class="url DELETE"><span class="http_method">DELETE</span>
<span class="path">https://rws.netdna.com/{companyalias}/zones/{zone_type}/{zone_id}/upstream.json</span></div>
</div>


### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>
</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>
$type = 'pull';
$id = '96061';
$api->delete('/zones/'.$type.'/'.$id.'/upstream.json');</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>
</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


# Reports by Zone API

## List Zone Stats

Gets all zone usage statistics optionally broken up by
{report_type}. If no {report_type} is given the request will return
the total usage for the zones.

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/stats.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`size` | The amount of bytes transferred | 1.0 |
`hit` | The number of times files were requested | 1.0 |
`noncache_hit` | The number of times a requested file was not in cache | 1.0 |
`cache_hit` | The number of times a requested file was already cached | 1.0 |
`timestamp` | The timestamp for the corresponding {report_type}. | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List Stats per Zone

Gets the {zone_id} usage statistics optionally broken up by
{report_type}. If no {report_type} is given the request will return
the total usage for the zones.

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_id}/stats.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`size` | The amount of bytes transferred | 1.0 |
`hit` | The number of times files were requested | 1.0 |
`noncache_hit` | The number of times a requested file was not in cache | 1.0 |
`cache_hit` | The number of times a requested file was already cached | 1.0 |
`timestamp` | The timestamp for the corresponding {report_type}. | 1.0 |



### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


# Reports by Location API

## List Nodes

Gets a list of all active nodes (locations)

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/nodes.json</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Node Id | 1.0 |
`name` | Node 3 letter code | 1.0 |
`description` | Full node name | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List Nodes by Zone

Gets a list of all active nodes (locations) specified by the
{zone_id} parameter

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_id}/nodes.json</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Node Id | 1.0 |
`name` | Node 3 letter code | 1.0 |
`description` | Full node name | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List Zone Node Stats by Report Type

Get usage statistics broken up by nodes and optionally
{report_type}. If no {report_type} is given the request will return
the total usage broken up by node.

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/nodes.json/stats/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-31) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-31) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`pop_id` | Node Id | 1.0 |
`pop_name` | Node 3 letter code. Only returned when {report_type} is notempty. | 1.0 |
`pop_description` | Full node name. Only returned when {report_type} is notempty. | 1.0 |
`size` | The amount of bytes transferred | 1.0 |
`hit` | The number of times files were requested | 1.0 |
`noncache_hit` | The number of times a requested file was not in cache | 1.0 |
`cache_hit` | The number of times a requested file was already cached | 1.0 |
`timestamp` | A timestamp corresponding to {report_type}. Only returned when{report_type} is not empty. | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List Node Stats by Zone and Report Type

Get usage statistics for a particular {zone_id} broken up by
nodes and optionally {report_type}. If no {report_type} is given
the request will return the total usage broken up by node.

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_id}/nodes.json/stats/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`pop_id` | Node Id | 1.0 |
`pop_name` | Node 3 letter code. Only returned when {report_type} is notempty. | 1.0 |
`pop_description` | Full node name. Only returned when {report_type} is notempty. | 1.0 |
`size` | The amount of bytes transferred | 1.0 |
`hit` | The number of times files were requested | 1.0 |
`noncache_hit` | The number of times a requested file was not in cache | 1.0 |
`cache_hit` | The number of times a requested file was already cached | 1.0 |
`timestamp` | A timestamp corresponding to {report_type}. Only returned when{report_type} is not empty. | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Get Zone Node

Gets the node information for the specified {node_id}

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/nodes.json/{node_id}</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Node Id | 1.0 |
`name` | Node 3 letter code | 1.0 |
`description` | Full node name | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Get Node by Zone

Gets the node information for the specified {node_id} and
{zone_id}

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_id}/nodes.json/{node_id}</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`id` | Node Id | 1.0 |
`name` | Node 3 letter code | 1.0 |
`description` | Full node name | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Get Zone Node Stats by Report Type

Get usage statistics for a particular {node_id} optionally
broken up by {report_type}. If no {report_type} is given the
request will return the total usage for the node.

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/nodes.json/{node_id}/stats/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date. | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date. | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`size` | The amount of bytes transferred | 1.0 |
`hit` | The number of times files were requested | 1.0 |
`noncache_hit` | The number of times a requested file was not in cache | 1.0 |
`cache_hit` | The number of times a requested file was already cached | 1.0 |
`timestamp` | A timestamp corresponding to {report_type}. Only returned when{report_type} is not empty. | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## Get Node Stats by Zone and Report Type

Get usage statistics for a particular {node_id} and {zone_id},
optionally broken up by {report_type}. If no {report_type} is given
the request will return the total usage for the node.

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_id}/nodes.json/{node_id}/stats/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`size` | The amount of bytes transferred | 1.0 |
`hit` | The number of times files were requested | 1.0 |
`noncache_hit` | The number of times a requested file was not in cache | 1.0 |
`cache_hit` | The number of times a requested file was already cached | 1.0 |
`timestamp` | A timestamp corresponding to {report_type}. Only returned when{report_type} is not empty. | 1.0 |



### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---



# Reports by Popular Files API

## List Popular Files

Gets the most popularly requested files for your account,
grouped into daily statistics

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/popularfiles.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01). | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01). | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`bucket_id` | The Zone ID for the popular file | 1.0 |
`uri` | The URI for the requested popular file | 1.0 |
`hit` | The number of times the file was requested | 1.0 |
`size` | The amount of bytes transferred for the given file | 1.0 |
`vhost` | The CDN URL for the corresponding zone | 1.0 |
`timestamp` | The amount of bytes transferred | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List Popular Files

Gets the most popularly requested files for your account,
filtered by {zone_type} and grouped into daily statistics

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_type}/popularfiles.json</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`bucket_id` | The Zone ID for the popular file | 1.0 |
`uri` | The URI for the requested popular file | 1.0 |
`hit` | The number of times the file was requested | 1.0 |
`size` | The amount of bytes transferred for the given file | 1.0 |
`vhost` | The CDN URL for the corresponding zone | 1.0 |
`timestamp` | The amount of bytes transferred | 1.0 |



### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


# Reports by Status Codes API

## List Status Code Responses

Gets HTTP status code response statistics for your account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/statuscodes.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`status_code` | The HTTP status code for the response | 1.0 |
`hit` | The number of responses with this status code | 1.0 |
`definition` | The definition for the status code | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List Status Code Responses by Zone Id

Gets HTTP status code response statistics for a specific
{zone_id}

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_id}/statuscodes.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`status_code` | The HTTP status code for the response | 1.0 |
`hit` | The number of responses with this status code | 1.0 |
`definition` | The definition for the status code | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List Status Codes by Zone Type

Gets HTTP status code response statistics for a specific
{zone_type}

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_type}/statuscodes.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`status_code` | The HTTP status code for the response | 1.0 |
`hit` | The number of responses with this status code | 1.0 |
`definition` | The definition for the status code | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List Status Codes by Zone Id

Gets HTTP status code response statistics for a specific
{zone_type} and {zone_id}

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_type}/{zone_id}/statuscodes.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`status_code` | The HTTP status code for the response | 1.0 |
`hit` | The number of responses with this status code | 1.0 |
`definition` | The definition for the status code | 1.0 |



### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


# Reports by File Types API

## List File Types

Gets file type statistics for your account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/filetypes.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`file_type` | The file type requested | 1.0 |
`hit` | The number of times a file of this type has been requested | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List File Types by Zone Id

Gets file type statistics for a specific {zone_id}

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_id}/filetypes.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d e.g. 2012-01-01 | Start date | 1.0 |
`date_to` | now() | Y-m-d e.g. 2012-01-01 | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`file_type` | The file type requested | 1.0 |
`hit` | The number of times a file of this type has been requested | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List File Types by Zone Type

Gets file type statistics for a specific {zone_type}

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_type}/filetypes.json/{report_type}</span></div>
</div>

### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`file_type` | The file type requested | 1.0 |
`hit` | The number of times a file of this type has been requested | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List File Types by Zone Id

Gets file type statistics for a specific {zone_type} and
{zone_id}

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_type}/{zone_id}/filetypes.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`file_type` | The file type requested | 1.0 |
`hit` | The number of times a file of this type has been requested | 1.0 |


### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---



# Reports by File Size Ranges API

## List File Sizes

Gets request statistics for your account based on file size
ranges

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/filesizes.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`le_10k_hits` | The number of requests for files &lt;= 10KB | 1.0 |
`le_50k_hits` | The number of requests for files &lt;= 50KB | 1.0 |
`le_100k_hits` | The number of requests for files &lt;= 100KB | 1.0 |
`le_500k_hits` | The number of requests for files &lt;= 500KB | 1.0 |
`le_1m_hits` | The number of requests for files &lt;= 1MB | 1.0 |
`le_10m_hits` | The number of requests for files &lt;= 10MB | 1.0 |
`le_100m_hits` | The number of requests for files &lt;= 100MB | 1.0 |
`gt_100m_hits` | The number of requests for files &gt; 100MB | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List File Sizes by Zone Id

Gets request statistics for the specified {zone_id} based on
file size ranges

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_id}/filesizes.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d e.g. 2012-01-01 | Start date | 1.0 |
`date_to` | now() | Y-m-d e.g. 2012-01-01 | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`le_10k_hits` | The number of requests for files &lt;= 10KB | 1.0 |
`le_50k_hits` | The number of requests for files &lt;= 50KB | 1.0 |
`le_100k_hits` | The number of requests for files &lt;= 100KB | 1.0 |
`le_500k_hits` | The number of requests for files &lt;= 500KB | 1.0 |
`le_1m_hits` | The number of requests for files &lt;= 1MB | 1.0 |
`le_10m_hits` | The number of requests for files &lt;= 10MB | 1.0 |
`le_100m_hits` | The number of requests for files &lt;= 100MB | 1.0 |
`gt_100m_hits` | The number of requests for files &gt; 100MB | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List File Sizes by Zone Type

Gets request statistics for the specified {zone_type} based on
file size ranges

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_type}/filesizes.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d e.g. 2012-01-01 | Start date | 1.0 |
`date_to` | now() | Y-m-d e.g. 2012-01-01 | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`le_10k_hits` | The number of requests for files &lt;= 10KB | 1.0 |
`le_50k_hits` | The number of requests for files &lt;= 50KB | 1.0 |
`le_100k_hits` | The number of requests for files &lt;= 100KB | 1.0 |
`le_500k_hits` | The number of requests for files &lt;= 500KB | 1.0 |
`le_1m_hits` | The number of requests for files &lt;= 1MB | 1.0 |
`le_10m_hits` | The number of requests for files &lt;= 10MB | 1.0 |
`le_100m_hits` | The number of requests for files &lt;= 100MB | 1.0 |
`gt_100m_hits` | The number of requests for files &gt; 100MB | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List File Sizes by Zone Id

Gets request statistics for the specified {zone_type} and
{zone_id} based on file size ranges

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_type}/{zone_id}/filesizes.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`le_10k_hits` | The number of requests for files &lt;= 10KB | 1.0 |
`le_50k_hits` | The number of requests for files &lt;= 50KB | 1.0 |
`le_100k_hits` | The number of requests for files &lt;= 100KB | 1.0 |
`le_500k_hits` | The number of requests for files &lt;= 500KB | 1.0 |
`le_1m_hits` | The number of requests for files &lt;= 1MB | 1.0 |
`le_10m_hits` | The number of requests for files &lt;= 10MB | 1.0 |
`le_100m_hits` | The number of requests for files &lt;= 100MB | 1.0 |
`gt_100m_hits` | The number of requests for files &gt; 100MB | 1.0 |


### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---



# Reports By Directory API

## List Stats By Directory

Gets usage statistics by directory for your account. (This
report has to be enabled by Sales).

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/statsbydir.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`bucket_id` | The Zone ID for the top level directory | 1.0 |
`dir` | The name of the directory | 1.0 |
`hit` | The number of requests made to files within this directory | 1.0 |
`size` | The amount of bytes transferred from within this directory | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List Stats By Directory and Zone Id

Gets usage statistics by directory for the specified {zone_id}.
(This report has to be enabled by Sales).

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/{zone_id}/statsbydir.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`bucket_id` | The Zone ID for the top level directory | 1.0 |
`dir` | The name of the directory | 1.0 |
`hit` | The number of requests made to files within this directory | 1.0 |
`size` | The amount of bytes transferred from within this directory | 1.0 |


### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---



# Reports By File Name API

## List Stats By File Name

Gets usage statistics by file name for your account

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/clients/{client_id}/reports/statsbyfilename.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |
`file_names` | A JSON Encoded file names list | 1.0 |
`filter` | Matching expression for file names | 1.0 |
`sort_by` | Field to sort by | 1.0 |
`sort_dir` | Directory to sort files by | 1.0 |
`page_size` | - | The number of records returned in the result set | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`bucket_id` | The Zone ID for the top level directory | 1.0 |
`hit` | The number of requests made to files within this directory | 1.0 |
`size` | The amount of bytes transferred from within this directory | 1.0 |
`200` | The amount of 200 hits | 1.0 |
`206` | The amount of 206 hits | 1.0 |
`2xx` | The amount of 2xx hits | 1.0 |
`3xx` | The amount of 3xx hits | 1.0 |
`404` | The amount of 404 hits | 1.0 |
`4xx` | The amount of 4xx hits | 1.0 |
`5xx` | The amount of 206 hits | 1.0 |
`5xx` | The amount of 206 hits | 1.0 |
`timestampf` | Timestamp | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List Stats By File Name and Zone Id

Gets usage statistics by file name for the specified
{zone_id}

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/clients/{client_id}/reports/{zone_id}/statsbyfilename.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |
`file_names` | A JSON Encoded file names list | 1.0 |
`filter` | Matching expression for file names | 1.0 |
`sort_by` | Field to sort by | 1.0 |
`sort_dir` | Directory to sort files by | 1.0 |
`page_size` | - | The number of records returned in the result set | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`bucket_id` | The Zone ID for the top level directory | 1.0 |
`hit` | The number of requests made to files within this directory | 1.0 |
`size` | The amount of bytes transferred from within this directory | 1.0 |
`200` | The amount of 200 hits | 1.0 |
`206` | The amount of 206 hits | 1.0 |
`2xx` | The amount of 2xx hits | 1.0 |
`3xx` | The amount of 3xx hits | 1.0 |
`404` | The amount of 404 hits | 1.0 |
`4xx` | The amount of 4xx hits | 1.0 |
`5xx` | The amount of 206 hits | 1.0 |
`5xx` | The amount of 206 hits | 1.0 |
`timestampf` | Timestamp | 1.0 |


### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---



# Reports By Custom Domain API

## List Stats By Directory

Gets usage statistics by custom domain for your account. (This
report has to be enabled by Sales).

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/clients/{client_id}/reports/statsbycustomdomain.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`bucket_id` | The Zone ID for the custom domain | 1.0 |
`custom_domain_id` | The ID of your custom domain | 1.0 |
`hit` | The number of requests made to this custom domain | 1.0 |
`size` | The amount of bytes transferred to/from this custom domain | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---


## List Stats By Custom Domain and Zone Id

Gets usage statistics by custom domain for the specified
{zone_id}. (This report has to be enabled by Sales).

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/clients/{client_id}/reports/{zone_id}/statsbycustomdomain.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | now() - 1 month | Y-m-d (e.g. 2012-01-01) | Start date | 1.0 |
`date_to` | now() | Y-m-d (e.g. 2012-01-01) | End date | 1.0 |


### Response Parameters

Parameter | Description | Since |
--- | --- | ---
`bucket_id` | The Zone ID for the top level directory | 1.0 |
`custom_domain_id` | The ID of the Custom Domain | 1.0 |
`hit` | The number of requests made to this custom domain | 1.0 |
`size` | The amount of bytes transferred to/from this custom domain | 1.0 |



### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---



# Reports for Live Zones API

## List Connection Stats

Gets zone stats in hourly, daily, or monthly summaries

<div class="heading">
<div class="url GET"><span class="http_method">GET</span>
<span class="path">https://rws.netdna.com/{companyalias}/reports/live/connectionstats.json/{report_type}</span></div>
</div>

### Accepted Request Parameters

Parameter | Default Value | Validation | Description | Since |
--- | --- | --- | --- | ---
`date_from` | - | Y-m-d e.g. 2012-01-01 | Start date | 1.0 |
`date_to` | - | Y-m-d e.g. 2012-01-01 | End date | 1.0 |

### Code Samples

<ul class="nav nav-tabs" id="myTab">
  <li class="active"><a href="#ruby" data-toggle='tab'>Ruby</a></li>
  <li><a href="#python" data-toggle='tab'>Python</a></li>
  <li><a href="#php" data-toggle='tab'>PHP</a></li>
  <li><a href="#node" data-toggle='tab'>Node</a></li>
  <li><a href="#response" data-toggle='tab'>Response</a></li>
</ul>
 
<div class="tab-content">
  <div class="tab-pane active" id="ruby">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="python">
		<pre>

		</pre>
	</div>
  <div class="tab-pane" id="php">
  	<pre>

  	</pre>
  </div>
  <div class="tab-pane" id="node">
		<pre>

		</pre>
  </div>
  <div class="tab-pane" id="response">
		<pre>
		
		</pre>
  </div>
</div>
 
<script>
  $(function () {
    $('#myTab a:last').tab('show');
  })
</script>

---



