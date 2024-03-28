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

# Table of Contents
- [High Level Design](#high-level-design)
- [LLD](#lld)
  - [Company Service](#company-service)
    - [Create Company](#create-company-post-api-companies)
    - [Update Company](#update-company-put-api-companies-companyid)
    - [Get Company](#get-company-get-api-companies-companyid)
    - [Delete Company](#delete-company-delete-api-companies-companyid)
    - [Get all Jobs Posted by a Company](#get-all-jobs-posted-by-a-company-get-api-companies-companyid-jobs)
    - [Get all Reviews for a Company](#get-all-reviews-for-a-company-get-api-companies-companyid-reviews)
  - [Job Service](#job-service)
    - [Create Job Posting](#create-job-posting-post-api-jobs)
    - [Update Job Posting](#update-job-posting-put-api-jobs-jobid)
    - [Get Job Posting](#get-job-posting-get-api-jobs-jobid)
    - [Delete Job Posting](#delete-job-posting-delete-api-jobs-jobid)
    - [Get all Jobs Postings by a Company](#get-all-jobs-postings-by-a-company-get-api-jobs-companycompany_idcompanyid)
  - [Review Service](#review-service)
    - [Post a Review](#post-a-review-post-api-reviews)
    - [Update a Review](#update-a-review-put-api-reviews-reviewid)
    - [Get Review](#get-review-get-api-reviews-reviewid)
    - [Delete Review](#delete-review-delete-api-reviews-reviewid)
    - [Get all Reviews for a Company](#get-all-reviews-for-a-company-get-api-reviews-companycompany_idcompanyid)

## High Level Design <a name="high-level-design"></a>
![Job Lens Zoomed](https://github.com/SinghVikram97/Job-Lens/assets/18444000/07a3454b-5d7c-4cb0-9ecd-c16120e97630)

<a name="lld"></a>
## LLD
<a name="company-service"></a>
### Company Service 

<a name="create-company-post-api-companies"></a>
#### Create Company POST (/api/companies)
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/a7cd6a5c-e786-40b8-bb02-c5bc2245e52a)

<a name="update-company-put-api-companies-companyid"></a>
#### Update Company PUT (/api/companies/{companyId})
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/a40ff51d-adc7-4443-a568-c2f5c025f3e6)

<a name="get-company-get-api-companies-companyid"></a>
#### Get Company GET (/api/companies/{companyId})
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/0bdfb3ed-6633-4642-b676-90f963234f9d)

<a name="delete-company-delete-api-companies-companyid"></a>
#### Delete Company DELETE (/api/companies/{companyId}) 
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/b4a6ba08-2d9a-4fe8-8482-2d3cce9dade4)

<a name="get-all-jobs-posted-by-a-company-get-api-companies-companyid-jobs"></a>
#### Get all Jobs Posted by a Company GET (/api/companies/{companyId}/jobs) 
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/347f5cbe-a57f-4cce-9916-58f82123f9db)

<a name="get-all-reviews-for-a-company-get-api-companies-companyid-reviews"></a>
#### Get all Reviews for a Company GET (/api/companies/{companyId}/reviews) 
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/a7972014-4b46-45b3-9c44-e5cfc59f947e)

<a name="job-service"></a>
### Job Service 

<a name="create-job-posting-post-api-jobs"></a>
#### Create Job Posting POST (/api/jobs) 
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/77400e74-0c3c-4730-b7fc-3d4660ff189f)

<a name="update-job-posting-put-api-jobs-jobid"></a>
#### Update Job Posting PUT (/api/jobs/{jobId}) 
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/8e2df3d0-c69d-41ab-9ac6-bd52791da225)

<a name="get-job-posting-get-api-jobs-jobid"></a>
#### Get Job Posting GET (/api/jobs/{jobId}) 
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/a5e3f165-84aa-498a-a515-c255b09d2b49)

<a name="delete-job-posting-delete-api-jobs-jobid"></a>
#### Delete Job Posting DELETE (/api/jobs/{jobId}) 
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/a46ccb79-8d3f-4295-b247-6ddde98f2d9d)

<a name="get-all-jobs-postings-by-a-company-get-api-jobs-companycompany_idcompanyid"></a>
#### Get all Jobs Postings by a Company GET (/api/jobs/company?company_id={companyId}) 
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/47aeb303-fc78-4bba-896a-4e70d612ae27)

<a name="review-service"></a>
### Review Service 

<a name="post-a-review-post-api-reviews"></a>
#### Post a Review POST (/api/reviews) 
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/dc556acf-03ae-4b4e-b0e4-25618ba18017)

<a name="update-a-review-put-api-reviews-reviewid"></a>
#### Update a Review PUT (/api/reviews/{reviewId}) 
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/545fd3b4-e257-4cb1-8e79-fc54eba50aee)

<a name="get-review-get-api-reviews-reviewid"></a>
#### Get Review GET (/api/reviews/{reviewId}) 
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/5819658c-5ead-4b28-a2cc-07ba8d0d1841)

<a name="delete-review-delete-api-reviews-reviewid"></a>
#### Delete Review DELETE (/api/reviews/{reviewId}) 
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/9c793a32-df72-4e3c-80f9-3a6097585d61)

<a name="get-all-reviews-for-a-company-get-api-reviews-companycompany_idcompanyid"></a>
#### Get all Reviews for a Company GET (/api/reviews/company?company_id={companyId}) 
![Seq](https://github.com/SinghVikram97/Job-Lens/assets/18444000/739d330b-cba4-4659-b983-eb41f1685cc4)
