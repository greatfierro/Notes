
A long URL will be converted into a smaller url.

We will be using the following technologies:
- C#
- NET WEB API 
- EF Core
- MS SQL Server
- Angular (frontend)
- Redis (Caching)


Application architecture

**UrlShorterAPI**
- Convert long urls to their shortened format
- Will resolve and redirect shortened urls back to their original url

**URLShorter Client**
- Provides users with a web client 
- Calls the UrlShorterAPI

**Key Generating Service**
- A background service the will generate keys for use by the URLShorterAPI

