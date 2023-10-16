![RealMatter](https://firebasestorage.googleapis.com/v0/b/json-5638c.appspot.com/o/Images%2Fdid-resume-profile.png?alt=media&token=7fa2181f-b92e-4476-a12f-71fa0f6e7837&_gl=1*1evo50x*_ga*MTAyOTgyNzAyNS4xNjgxMzYwNjE3*_ga_CW55HF8NVT*MTY5NzM3ODI0NC4xNjEuMS4xNjk3Mzc4NTUyLjQ1LjAuMA..)

# RealMatter DID:Resume Method
did : resume : <ledger[1*]> : <id[40*]>

Technical Paper for W3C DID Registration

## Official Resume DID Method in W3C Registry

Merging into W3C Github DID Test Suite and DID Registry

## Real Matter Technology Limited
[realmatter.io](https://realmatter.io)

**Author** 
- Ming-lam Ng with Real Matter Technology

**Partner** 
- Talent Connect (Recruitment consultancy)

**Contacts** 
- mn@realmatter.io
- consultant@talentconnect.com.hk

**Date** 
- 1 Oct 20

**Version** 
- First copy V1.0



## About Real Matter

Real Matter Technology Limited
is a Fintech company that envisions implementing chip-level blockchain identity technology and smart contract-on-chip credentials to facilitate real-world asset tokenization and provide verifiable solutions for Web3 crypto-asset identities. 

Real Matter created and contributed three [DID methods](https://w3c.github.io/did-spec-registries/#did-methods) : [did:art](https://github.com/ArtracID/ArtracID-DID-ART-Method) method, [did:rm](https://github.com/realmatterio/RealMatter-DID-Method) method, and this did:resume method.

This document specifies the “Resume” [DID Method](https://w3c.github.io/did-spec-registries/#did-methods) [**did:resume**].

RealMatter uses [did-resume.web.app](https://did-resume.web.app) as the official service website.

## Talent Connect Limited
[talentconnect.com.hk](https://www.talentconnect.com.hk)

## About Talent Connect

Talent Connect Limited
is a professional recruitment consultancy company aimed at finding talents to support companies achieving success in today's competitive and fast-moving business environment.

Talent Connect cooperates with Real Matter to promote the industrial standards of Decentralized Identifier (DID) and Verifiable Credential (VC) to the industry for use in the talent exchange market and verifiable resumes.

**Decentralized Identifier (DID) for Job Seekers**

Job seekers can verify their personal identity through Decentralized Identifier (DID), and can be applied to :
job application forms,
resumes and curriculum vitaes,
recruitment condition matching,
employment ID verification, etc.

**Verifiable Credential (VC) in Talent Exchange**

Talent exchange markets can use Verifiable Credentials (VC) to confirm the accuracy of job applications, e.g.,
biography,
academic certifications,
professional qualifications,
job experience

**DID:Resume Service Endpoints**

![Service Endpoint](https://firebasestorage.googleapis.com/v0/b/json-5638c.appspot.com/o/Images%2Fdid-resume-block-diagram.png?alt=media&token=902dc069-c070-476b-bdd0-ea05ae45f023&_gl=1*1c9bjat*_ga*MTAyOTgyNzAyNS4xNjgxMzYwNjE3*_ga_CW55HF8NVT*MTY5NzQxODQxMC4xNjIuMS4xNjk3NDE4NDE5LjUxLjAuMA..)
 
**Query of job seeker's ID document**

did-resume.web.app/{job_seeker_id}?token={access_token}

**Query of job seeker's credential verifier**

did-resume.web.app/vc/{job_seeker_id}?token={access_token}

**Query of job seeker's biography**

did-resume.web.app/bio/{job_seeker_id}?token={access_token}

**Query of job seeker's academic certificates**

did-resume.web.app/cert/{job_seeker_id}?token={access_token}

**Query of job seeker's professional qualifications**

did-resume.web.app/qual/{job_seeker_id}?token={access_token}

**Query of job seeker's job experience**

did-resume.web.app/exp/{job_seeker_id}?token={access_token}

remark: for public access information, post no query

## Conformity

This DID method specification conforms to the requirements specified in the DID specification currently published by the W3C Credentials Community Group. For more information about DIDs and DID method specifications, please see DID Primer and DID Specification.

The following DID Method will be registered in the DID Specification Registries (https://w3c.github.io/did-spec-registries/#did-methods).


## Status of This Document

This document was published as an Editor's Draft. Publication as an Editor's Draft does not imply endorsement by the W3C Membership. This is a draft document and may be updated, replaced or obsoleted by other documents at any time. It is inappropriate to cite this document as other than a work in progress.


## Resume DID Block Diagram

![DID:Resume Block Diagram](https://firebasestorage.googleapis.com/v0/b/json-5638c.appspot.com/o/Images%2Fdid-resume-block-diagram.png?alt=media&token=0f383b57-ca39-494a-bc90-ec19b48df075&_gl=1*6x9yxc*_ga*MTAyOTgyNzAyNS4xNjgxMzYwNjE3*_ga_CW55HF8NVT*MTY5Njk5NDExMS4xNTcuMS4xNjk2OTk0MTYyLjkuMC4w)


## Resume DID Method

The namestring that shall identify this DID method is : **resume**

A DID that uses this method MUST begin with the following prefix: did:resume. Per the DID specification, this string MUST be in lowercase.


**DID Format**

```
Resume DID =  did: resume: method-specific-ledger-id: method-specific-subject-id 
method-specific-ledger-id  =  1*idchar   where idchar = 0-9 / a-z
method-specific-subject-id =  40*idhex   where idhex  = 0-9 / a-f
```

This generic DID scheme is a URI scheme conformant with [RFC3986](https://www.ietf.org/rfc/rfc3986.txt)

where 

method-specific-ledger-id refers to HKG-chain

method-specific-subject-id refers to a string of 40 hexadecimal characters

example :

did: resume: hkg : f045c5c7d50145b65ca2702c38b4e2d46658293c


**Method Specific Subject ID Generation**

Take the highly secured key tag hardware as a default contract , method-specific-subject-id should be encoded as follow:

Retrieve the hardware RNG generated public key in the highly secured key tag hardware

Hash the public key and take the first 20 hex digits

Use the multibase format [base16](https://tools.ietf.org/id/draft-multiformats-multibase-00.html#RFC4648) to encode the first 20 digits without the prefix letter of base16 identifier to obtain the method-specific-subject-id in 40 hexadecimal characters.


## Resume DID Document
```
     {
        "@context": [
          "https://www.w3.org/ns/did/v1",
          "https://w3c-ccg.github.io/ld-cryptosuite-registry/#ecdsasecp256k1signature2019"
        ],
        "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c",
        "verificationMethod": [
          {
            "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#masterkey",
            "type": "EcdsaSecp256k1VerificationKey2019",
            "controller": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c",
            "publicKeyMultibase": "fef2823c7d237bd094d633a1765d5896b0f442481a997da2f83d7a928ddce7e65",
            "blockchainAccountId":"enq:f045c5c7d50145b65ca2702c38b4e2d46658293c"
          }
        ],
        "authentication": [
          "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#masterkey"
        ],
        "assertionMethod": [
          "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#masterkey"
        ],
        "service": [
          {
	    "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#service",
    	    "type": "LinkedDomains",
    	    "serviceEndpoint": "did-resume.web.app"
          }
        ]
      }
```


## DID Path, Query and Fragment 


**Path**

Six types of path is supported in this version

/ : response = information of decentralized identifier : e.g. identity of job seeker

/vc : response = information of verifiable credential : e.g. verifiers and verification method

/bio : response = verified biography : e.g. biography of job seekers and change history

/cert : response = verified certificates : e.g. academic certificates of job seeker and change history

/qual : response = verified qualifications : e.g. professional qualifications of job seeker and change history

/exp : response = verified experience : e.g. job experience of job seeker and change history



**Query**

In this version, only the access token is supported, and no other queries are available.


**Fragment**

One type of fragment is supported in this version
#masterkey : the specific master key applied in the verification methods


## DID Create Operation

The instruction to create a new DID is issued via a POST HTTP request. 
```
POST /f045c5c7d50145b65ca2702c38b4e2d46658293c?token=abcde
Host: did-resume.web.app
Content-Type: application/json
Accept: application/json
Accept-Encoding: gzip, deflate
{
    "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c",
    "operation": "create",
    "document": {
        "@context": [
            "https://www.w3.org/ns/did/v1",
            "https://w3c-ccg.github.io/ld-cryptosuite-registry/#ecdsasecp256k1signature2019"
        ],
        "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c",
        "verificationMethod": [
          {
            "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#masterkey",
            "type": "EcdsaSecp256k1VerificationKey2019",
            "controller": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c",
            "publicKeyMultibase": "fef2823c7d237bd094d633a1765d5896b0f442481a997da2f83d7a928ddce7e65",
            "blockchainAccountId":"tc:f045c5c7d50145b65ca2702c38b4e2d46658293c"
          }
        ],
        "authentication": [
          "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#masterkey"
        ],
        "assertionMethod": [
          "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#masterkey"
        ],
        "service": [
          {
	    "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#service",
    	    "type": "LinkedDomains",
    	    "serviceEndpoint": "did-resume.web.app"
          }
        ]
    }
}
```


## DID Read Operation (Resolve)

The instruction to read a DID is issued via a GET HTTP request. 

did-resume.web.app/{method-specific-subject-id}

Example :

[did-resume.web.app/f045c5c7d50145b65ca2702c38b4e2d46658293c](did-resume.web.app/f045c5c7d50145b65ca2702c38b4e2d46658293c)

```
GET /f045c5c7d50145b65ca2702c38b4e2d46658293c?token=abcde
Host: did-resume.web.app
Accept: application/json
Accept-Encoding: gzip, deflate
```

Response from the service endpoint did-resume.web.app
```
{
    "responseCode": 0,
    "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c",
    "document": {
        "@context": [
            "https://www.w3.org/ns/did/v1",
            "https://w3c-ccg.github.io/ld-cryptosuite-registry/#ecdsasecp256k1signature2019"
        ],
        "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c",
        "verificationMethod": [
          {
            "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#masterkey",
            "type": "EcdsaSecp256k1VerificationKey2019",
            "controller": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c",
            "publicKeyMultibase": "fef2823c7d237bd094d633a1765d5896b0f442481a997da2f83d7a928ddce7e65",
            "blockchainAccountId":"tc:f045c5c7d50145b65ca2702c38b4e2d46658293c"
          }
        ],
        "authentication": [
          "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#masterkey"
        ],
        "assertionMethod": [
          "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#masterkey"
        ],
        "service": [
          {
	    "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#service",
    	    "type": "LinkedDomains",
    	    "serviceEndpoint": "did-resume.web.app"
          }
        ]
    }
}
```


## DID Update Operation

The instruction to update a DID is issued via a PUT HTTP request. 
```
PUT /f045c5c7d50145b65ca2702c38b4e2d46658293c?token=abcde
Host: did-resume.web.app
Content-Type: application/json
Accept: application/json
Accept-Encoding: gzip, deflate
{
    "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c",
    "operation": "update",
    "document": {
        "@context": [
            "https://www.w3.org/ns/did/v1",
            "https://w3c-ccg.github.io/ld-cryptosuite-registry/#ecdsasecp256k1signature2019"
        ],
        "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c",
        "verificationMethod": [
          {
            "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#masterkey",
            "type": "EcdsaSecp256k1VerificationKey2019",
            "controller": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c",
            "publicKeyMultibase": "fef2823c7d237bd094d633a1765d5896b0f442481a997da2f83d7a928ddce7e65",
            "blockchainAccountId":"tc:f045c5c7d50145b65ca2702c38b4e2d46658293c"
          }
        ],
        "authentication": [
          "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#masterkey"
        ],
        "assertionMethod": [
          "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#masterkey"
        ],
        "service": [
          {
	    "id": "did:resume:hkg:f045c5c7d50145b65ca2702c38b4e2d46658293c#service",
    	    "type": "LinkedDomains",
    	    "serviceEndpoint": "did-resume.web.app"
          }
        ]
    }
}
```


## DID Delete Operation

The instruction to delete a DID is issued via a DELETE HTTP request. 
```
DELETE /f045c5c7d50145b65ca2702c38b4e2d46658293c?token=abcde
Host: did-resume.web.app
Accept: application/json
Accept-Encoding: gzip, deflate
```

## Security Considerations


The Resume DID method never exposes the private key. The user can however use and display the DID's private key locally on the highly secured security key tag hardware.

In the DID:Resume system, all users' private data is stored on the highly secured security key tag hardware. Only the hash value or strings generated by crypt algorithms of the data are public on-chain, the attackers cannot derive the private data with the hash value or strings.

All data stored in DID documents is considered public. DID documents do not contain any personal information about the user concerned.

**Attacks**

To prevent an attack, a did proof has to go through the signature verification against the verifier’s challenge. The signature is processed inside the highly secured security key tag hardware.


## Privacy Considerations

The DID:Resume blockchain and DID Documents contain no PII (Personally-Identifiable Information).

Private data in RealMatter is encrypted and signed using the private key which corresponds to the public key in the DID. This ensures that no message insertion or modification is possible and authenticity of the DID Documents is ensured. 

The DID:Resume system prevents forgery and tampering through hash value checking.

Private keys(for signing operations) are to be held on highly secured security key tag hardware.

