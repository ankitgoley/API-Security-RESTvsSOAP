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
         



  
       
