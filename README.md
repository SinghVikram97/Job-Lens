# Job Lens
Microservices driven platform for companies to post their job listings and employees to leave reviews for companies they have worked for

## Tech Stack 
Developed using:
Java, Spring Boot, Spring Data JPA, PostgreSQL, Spring Cloud Gateway, Spring Cloud Netflix - Eureka Server, Zipkin, Spring Cloud OpenFeign, Micrometer

## Services Involved
* [API Gateway](https://github.com/SinghVikram97/api-gateway): Serves as the single entrypoint for the client and routes request to different services
* [Eureka Server](https://github.com/SinghVikram97/service-registry): Provides service registry and load balancing capabilities
* [Company Microservice](https://github.com/SinghVikram97/company-service): Manages the creation, modification, and retrieval of Company related data
* [Job Microservice](https://github.com/SinghVikram97/job-service): Manages the creation, modification, and retrieval of Jobs related data
* [Review Microservice](https://github.com/SinghVikram97/review-service): Manages the creation, modification, and retrieval of Reviews related data

## High Level Design
![Job Lens Zoomed](https://github.com/SinghVikram97/Job-Lens/assets/18444000/07a3454b-5d7c-4cb0-9ecd-c16120e97630)

## LLD
### Company Service

* Create Company POST (/api/companies) 

![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/a7cd6a5c-e786-40b8-bb02-c5bc2245e52a)

* Update Company PUT (/api/companies/{companyId})
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/a40ff51d-adc7-4443-a568-c2f5c025f3e6)

* Get Company GET (/api/companies/{companyId})
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/0bdfb3ed-6633-4642-b676-90f963234f9d)

* Delete Company DELETE (/api/companies/{companyId})
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/b4a6ba08-2d9a-4fe8-8482-2d3cce9dade4)

* Get all Jobs Posted by a Company GET (/api/companies/{companyId}/jobs)
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/347f5cbe-a57f-4cce-9916-58f82123f9db)

* Get all Reviews for a Company GET (/api/companies/{companyId}/reviews)
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/a7972014-4b46-45b3-9c44-e5cfc59f947e)

### Job Service

* Create Job Posting POST (/api/jobs)
  
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/77400e74-0c3c-4730-b7fc-3d4660ff189f)


* Update Job Posting PUT (/api/jobs/{jobId})
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/8e2df3d0-c69d-41ab-9ac6-bd52791da225)

* Get Job Posting GET (/api/jobs/{jobId})

![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/a5e3f165-84aa-498a-a515-c255b09d2b49)

* Delete Job Posting DELETE (/api/jobs/{jobId})

![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/a46ccb79-8d3f-4295-b247-6ddde98f2d9d)

* Get all Jobs Postings by a Company GET (/api/jobs/company?company_id={companyId})

![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/47aeb303-fc78-4bba-896a-4e70d612ae27)
