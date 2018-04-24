---
layout: page
title:  "Basics: Data Infrastructure"
date:   2018-04-08 13:31:31 +0530
categories: data, database, warehousing, sql, nosql
permalink: /basics-how-data-flows-over-the-internet/
---

## How Data Flows Over the Internet

### What is a web server and why is it needed?

A web server is a computer which hosts a web application which serves web pages. Two major models of server architecture: client-server and peer-to-peer


  - Client-Server — a system where there is a central server (or several data centres) which serve requests of all the clients, e.g., amazon.com, google.com, facebook.com
  - Peer-to-Peer — a system where there is no central server and the architecture allows information exchange between two nodes over the internet. e.g., BitTorrent, Tor, Skype and so on.

How do servers communicate? List of protocols (there are more, but these are the most basic ones)


- TCP — data flows in packets, TCP breaks and reassembles data packets from one device to another over the Internet
- IP — when the data packets are flowing over the Internet, they are appended with the IP address of the destination so that every packet knows where to reach
- HTTP — used to transfer hypertext over the internet. Basically, serving web pages or text
- FTP — used for uploading and downloading files from the Internet

### Types of Devices using the Internet

Broadly, there are three major kinds of devices that communicate over the internet


- Web — a laptop or a desktop system which connects to the internet via various applications like GMail, YouTube so on and so forth.
- Mobile — quite similar to web devices but differs in a couple of things
  - in most devices there is a SIM card
  - there’s continuous location tracking possibilities
  - mobile devices are usually always powered on
- IoT or Internet of Things — smart lights, smart lock, wearable health monitor, location tracking devices for vehicles, couriers etc.

#### On a mobile or web device, this happens when you open google.com

##### A device has an application (browser or app). You log onto google.com. Your request goes to the ISP and the ISP does a DNS lookup and finds the IP address of google.com. The server is identified by the domain name, e.g., google.com. Your request reaches the server and the server responds with a page and the page is transferred as HTML to your computer. Your browser or app converts that HTML into readable/formatted hypertext.

#### When you Sign up on a website

##### The same process goes on when you open the signup page of a website but then after a while you start providing information on that page to create your account. This is different from just asking the web server for a page. You are sending the data to the server. The de facto standard for sending the data between servers is JSON. It used to be XML earlier. Essentially once you fill out your data, your data gets converted into a specific format and sent inside a HTTP request to the server. The server responds in a specific format inside a HTTP response.

#### The Nature of Data

Structured — databases, spreadsheets, .csv, .tsv

  - MySQL, SQL Server, PostgreSQL, Oracle, Spreadsheets

Semi-Structured — email, user forums, chat records, XML, JSON

  - Document-oriented databases — MongoDB

Unstructured — audio/video, images, books

API — application programming interface. A piece of code which creates requests and responses in certain prescribed format.

Most of the data (~95 percent) is unstructured. Although, metadata about the unstructured data might be structured in some cases.

— Download Postman application and see how basic HTTP requests work.

Types of Databases


- Flat files, spreadsheets — problematic when data becomes too large, also support only a particular kind of data, e.g., Lotus 123, Microsoft Excel etc.
- Relational databases — breakdown large data sets into different tables and map their relationships.
- Document databases — used when flexible schemas are required, relational databases are constrained by fixed schemas. Documents usually stored in a key-value JSON format.
- Graph databases — used to represent graphical structures like relationships between people, e.g., each person you know knows hundred other people and each one of them know hundred other people. Representing this in a relational database is very inefficient. e.g., neo4j, Orient-DB

A lot of other types of databases available based on the use-case.



[sql-fiddle]: http://www.sqlfiddle.com/#!9/9eecb/26319
