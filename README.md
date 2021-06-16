# Introduction to Web Services
A Web service is a standardized way of establishing communication between two Web-based applications by using open standards over an internet protocol backbone. It’s the best way to communicate with different applications who are developed on different platform.
<img width="401" alt="Screenshot 2021-06-17 at 1 56 53 AM" src="https://user-images.githubusercontent.com/76476308/122288150-5b690380-cf0f-11eb-9c68-224f2a7dbd77.png">

As you can see in the figure, java, .net or PHP applications can communicate with other applications through web service over the network. For example, java application can interact with Java, .Net and PHP applications. So, web service is a language independent way of communication.
# Difference between Web applications and Web services
A web application is an application that is accessed through a web browser running on a client’s machine whereas a web service is a system of software that allows different machines to interact with each other through a network. Most of the times, web services do not necessarily have a user interface since it’s used as a component in an application, while a web application is a complete application with a GUI. Furthermore, web services will take a web application to the next level because it’s used to communicate or transfer data between web applications that run on different platforms allowing it to support a heterogeneous environment.
# Why we use web services?
A web service is a unit of managed code that can be remotely invoked using HTTP, that is, it can be activated using HTTP requests. Web services allows you to expose the functionality of your existing code over the network. Once it is exposed on the network, other application can use the functionality of your program.

# Web services have some added advantages, some of them are listed below:
            1.Language Independent
            2.Platform Independent (Hardware and OS)
            3.Function Reusability
            4.Stateless communication

# Type of web services
            1. SOAP web services
            2. RESTful web services
           
# SOAP
SOAP is a protocol which was designed before REST and came into the picture. The main idea behind designing SOAP was to ensure that programs built on different platforms and programming languages could exchange data in an easy manner.

# Components of SOAP web services
            1.XML (Extensible Markup Language)
            2. SOAP (Simple Object Access Protocol)
            3.WSDL (Web Services Description Language)
            4.UDDI (Universal Description, Discovery and Integration)
            
# XML (Extensible Markup Language)
 It is used to encode data and form the SOAP message. 
 
 # SOAP (Simple Object Access Protocol)
 It is a XML-based protocol that lets applications exchange information over HTTP. Web services use a SOAP format to send XML requests. A SOAP client sends a SOAP message to the server. The server responds back again with a SOAP message along with the requested service. The entire SOAP message is packed in a SOAP Envelope as shown below:
 
 
<img width="397" alt="Screenshot 2021-06-17 at 2 08 46 AM" src="https://user-images.githubusercontent.com/76476308/122290045-fca48980-cf10-11eb-8ab8-f0614081f48c.png">


# Sample SOAP Request

POST /ws/ws.asmx HTTP/1.1
Host: www.example.com
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: http://www.example.com/ws/IsValidUser

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
<soap:Body>
<IsValidUser xmlns="http://www.example.com/ws/">
<UserId>string</UserId>
</IsValidUser>
</soap:Body>
</soap:Envelope>

# SOAP Response

HTTP/1.1 200 OK
Content-Type: text/xml; charset=utf-8
Content-Length: length

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
<soap:Body>
<IsValidUserResponse xmlns="http://www.example.com/ws/">
<IsValidUserResult>boolean</IsValidUserResult>
</IsValidUserResponse>
</soap:Body>
</soap:Envelope>

# WSDL (Web Services Description Language)
It is really an XML formatted language used by UDDI. It describes the capabilities of the web service as the collection of communication end points with the ability of exchanging messages. Or in simple words “Web Services Description Language is an XML-based language for describing Web services and how to access them.

            1.WSDL is used to describe Web services
            2.WSDL is used to locate Web services.
            3.WSDL describes the set of operations the web service provides.
            4.WSDL is a set of rules to describe your web service & how you can communicate with my web services, how & what messages will be sent in SOAP envelope.

# Structure of WSDL

<img width="395" alt="Screenshot 2021-06-17 at 2 15 03 AM" src="https://user-images.githubusercontent.com/76476308/122290904-d9c6a500-cf11-11eb-986f-e201eb26d833.png">

A WSDL document has a definitions element that contains the other five elements, types, message, portType, binding and service. The following sections describe the features of the generated client code.

# Contains the definition of one or more services. JDeveloper generates the following attribute declarations for this section:
            1.targetNamespace is the logical namespace for information about this service. WSDL documents can import other WSDL documents, and setting targetNamespace to a unique value ensures that the namespaces do not clash.
            2.xmlns is the default namespace of the WSDL document, and it is set to http://schemas.xmlsoap.org/wsdl/.
            3.All the WSDL elements, such as <definitions>, <types> and <message> reside in this namespace.
            4.xmlns:xsd and xmlns:soap are standard namespace definitions that are used for specifying SOAP-specific information as well as data types.
            5.xmlns:tns stands for this namespace.
            6.xmlns:ns1 is set to the value of the schema targetNamespace, in the <types> section.
      

# Types
All the schema types or data types defined here.
# message
This is a dependent element. Message is specified according to the data types defined in types element and used in side operation element later.
# operation
Collection of input, output, fault and other messages as specified in message element.
# input message
These are the parameters of the method used in SOAP request.
# output message
These are the parameters of the method used in SOAP response.
# binding
Describes how the operation is invoked by specifying concrete protocol and data format specifications for the operations and messages.
# port
It provides the physical path or location of web server so that service consumer can connect with service provider.
# service
Contains name of all the services provided by the service provider.

# Sample WSDL file

<img width="400" alt="Screenshot 2021-06-17 at 2 22 48 AM" src="https://user-images.githubusercontent.com/76476308/122291849-ef889a00-cf12-11eb-865a-4a22a3dacdf6.png">


# UDDI (Universal Description Discovery and Integration)
UDDI is an XML-based standard for describing, publishing, and finding Web services. UDDI is a set of specifications defining a registry service for Web services and for other electronic and non-electronic services.

A UDDI registry service is a Web service managing information about service providers, service implementations and service metadata. Providers list their Web services on the UDDI registry. Consumers then use UDDI to discover Web services suiting their requirements and obtain the service metadata needed to consume those services.

<img width="397" alt="Screenshot 2021-06-17 at 2 25 26 AM" src="https://user-images.githubusercontent.com/76476308/122292164-4e4e1380-cf13-11eb-807b-de83f5d2fe12.png">

In the above image as you can see how service consumer is requesting for WSDL to consume services which was available or listed by service provider named as service registry (UDDI).
Let’s take a simple scenario here- if a service consumer wants to use some sort of web service, then it must know the service provider. If a service provider validates a service consumer it will provide the WSDL file directly and then the service consumer creates a XML message to request for a required service in the form of a SOAP message and the service provider returns a service response.
Other scenario- if a service consumer is not aware of the service provider, then it will go for UDDI and search for the required service. The UDDI returns with the list of service providers offering that service.
Now choosing one service provider again the service consumer generates a XML message to request for a required service in the form of a SOAP message, as specified in the WSDL file of that service provider. The service provider then returns a service response. This is how a service consumer avail the required services which are available over the web.

# Security Testing of SOAP Web Services - Setting up the testing environment
The testing approach of web services is very much similar to the testing used in web applications. Web service security testing has been categorized in three types:

            1.Black Box Testing
            2.Grey Box Testing
            3.White Box Testing
            
            
# Black box testing
For a Black box assessment, at the very least, the penetration tester will need the Web Service Description Language (WSDL) file to begin with the testing.

Let’s say that you need to test web services associated with some application like (http://www.test.com). It’s a black box testing and you don’t have any details related to web services.

Now you can start with fingerprinting of web services. We can use google to fingerprint the WSDL file of that web application using special notations such as filetype as shown in below screenshot.

<img width="392" alt="Screenshot 2021-06-17 at 2 30 05 AM" src="https://user-images.githubusercontent.com/76476308/122292770-f7950980-cf13-11eb-9d47-e010312bf34b.png">

Google result

<img width="401" alt="Screenshot 2021-06-17 at 2 30 14 AM" src="https://user-images.githubusercontent.com/76476308/122292835-0c719d00-cf14-11eb-81e0-d8adec87e582.png">

We have the WSDL file of that web application. Now we can proceed with testing of web services, for that we require some tools as mentioned below:
            
            1.SOAP UI -  with this tool, we can load WSDL file and see all methods consists by Web service and proceed with testing of all those methods.
            2.Burp Suite- It’s a proxy tool and you can configure SOAP UI with this tool to play with web services request/response.
          
# Grey box testing
For a Grey Box assessment, the penetration tester will need sample requests for each method employed by the web service along with the Web Service Description Language (WSDL) file.

            1.Require WSDL file/SOAP UI project.
            2.Sample request/response.
            3.Types of information being requested/consumed.
            4.Authentication Information – if authentication is implemented in WS.
            
# White box testing
In this, you will have every information related to WS which is going to be tested.

# Let’s begin with SOAP UI tool
# Case: 
Consider it’s a black box testing and you do not have any details.
1.Start fingerprinting to find associated WSDL file. Like (use google dork to find wsdl)

<img width="401" alt="Screenshot 2021-06-17 at 2 30 14 AM" src="https://user-images.githubusercontent.com/76476308/122293447-a0dbff80-cf14-11eb-9057-fd091a04c604.png">

2.Extract the WSDL file, once you have the WSDL file then you need to open with SOAP UI tool.

<img width="397" alt="Screenshot 2021-06-17 at 2 35 49 AM" src="https://user-images.githubusercontent.com/76476308/122293553-c10bbe80-cf14-11eb-9be5-d57cdd50af33.png">

3.Web service has been loaded with all its services and methods inside it.

<img width="373" alt="Screenshot 2021-06-17 at 2 36 43 AM" src="https://user-images.githubusercontent.com/76476308/122293720-ee586c80-cf14-11eb-83f8-5b729a73ee94.png">

4.Click on “+” button to see all the methods exist in WS.

<img width="284" alt="Screenshot 2021-06-17 at 2 37 07 AM" src="https://user-images.githubusercontent.com/76476308/122293743-f57f7a80-cf14-11eb-8415-6e78bd882f95.png">

5.Now expand methods and click on request button, you will see xml request in form of SOAP message which you can send with your test data and observe the response. Based on that you can start you with testing.

<img width="398" alt="Screenshot 2021-06-17 at 2 38 00 AM" src="https://user-images.githubusercontent.com/76476308/122293923-265faf80-cf15-11eb-96d5-8ecb08e6d5dc.png">

Note:  As of now we don’t have valid data with us, because of that I’m getting status error- 500 Internal server error.Also, you can set up SOAP UI with Burp Suite. For that you need to configure proxy tab like below:

<img width="514" alt="Screenshot 2021-06-17 at 2 39 17 AM" src="https://user-images.githubusercontent.com/76476308/122294018-4000f700-cf15-11eb-84d4-879174741a6a.png">

Same address you need to add in your burp proxy as shown below then you will be able to capture the request in burp and can do manipulation with data.

<img width="485" alt="Screenshot 2021-06-17 at 2 39 54 AM" src="https://user-images.githubusercontent.com/76476308/122294092-5444f400-cf15-11eb-8ab7-1d5be2432a89.png">

Now capture the request and start testing-

<img width="530" alt="Screenshot 2021-06-17 at 2 40 39 AM" src="https://user-images.githubusercontent.com/76476308/122294182-6e7ed200-cf15-11eb-84be-1cc217fe9081.png">

# Grey box testing
# Case:
In Grey box testing – you will have following information to begin with the testing.
If SOAP UI project file is shared with you then directly you can import that file with SAOP UI tool. It will give you all related information to begin with the testing and proceed for the same.

<img width="400" alt="Screenshot 2021-06-17 at 2 42 14 AM" src="https://user-images.githubusercontent.com/76476308/122294441-ad148c80-cf15-11eb-8456-946c993aca0e.png">

And project file will be loaded into SOAP UI tool and you can access WS and its associated services.

<img width="280" alt="Screenshot 2021-06-17 at 2 42 59 AM" src="https://user-images.githubusercontent.com/76476308/122294522-c1f12000-cf15-11eb-81bc-625e9861f1ce.png">

a)If you have WSDL file and sample request/response with you. You can proceed with the testing as I already explain in black box testing tab.

b)If web service is using any kind of authentication to receive the successful response. We can configure the authentication process in SOAP UI as shown below




         



  
       
