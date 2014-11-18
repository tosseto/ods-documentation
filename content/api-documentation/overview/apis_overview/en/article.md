OpenDataSoft datasets can be accessed by developers through HTTP REST APIs. 

The domain <http://public.opendatasoft.com> will be use to illustrate examples given in this forum.

### Available APIs

The available APIs are listed below.


API Name | API Short Description
-------- | ---------------------
Dataset search API | Search datasets
Dataset lookup API | Find a dataset based on its identifier
Records search API | Search records within a specific dataset
Analysis API | Build advanced aggregations using records of a specific dataset
Download API | Efficiently download a large number of records from a specific dataset
Geo clustering API | Build geo clusters using records of a specific dataset
Real Time Push API | Real time data integration
Multimedia Download API | Download multimedia content attached with datasets or records

All these APIs (except the Multimedia download API) return JSON by default. Some of them can return alternate content. 

### Finding the dataset identifier

You are looking for specific data to build your application but you don't know yet in which dataset you can find these data ?

You can simply use the exploration console by clicking on the "Explore" link in the top page menu. Once you have identified the dataset you need, just go to this dataset's "Information" tab where you'll find the dataset id.

### HTTP Methods

Except for the real time push API which respects moer stricly RESTfullness concepts, all the APIs endpoints accept GET and POST HTTP methods. GET methods shall be prefered of course. The POST can be used to workaround browsers / libraries / proxies limitations regarding the size of the HTTP URL.

### Security

All the APIs are secured using the same authentication et authorization model.

Users can only see what they are allowed to see:

 * Datasets in a domain
 * Records in a dataset
 
APIs link are available both in HTTP and HTTPS. We advise API users to always use the HTTPS endpoint.

The available authentication modes are listed below.

Authentication Mode | Description
------------------- | -----------
Basic HTTP authentication | Provide your account's login and password: (<http://en.wikipedia.org/wiki/Basic_access_authentication>)
Simple key authentication | Provide an API key you generated for your account (API keys work on any domain an OpenDataSoft user has access to)

Note that when you are connected with a Browser session, API calls triggered from that browser will reuse your current credentials.

### Quotas

APIs endpoints are subject to quotas based limitations. Contact the domain administrator or the dataset owner when you reach a limit.

### Errors handling

When an error occurs, a JSON object describing the error is returned by the API.

Example of an error occuring when you reach a quota limit:

    HTTP return code: 
    	403
    HTTP response body:
	    {
	    	"errorcode": 10001,
			"error"": "License Violation Exception : You have exceeded your quotas."
		}



