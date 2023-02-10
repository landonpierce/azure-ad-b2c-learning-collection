# azure-ad-b2c-learning-collection

Azure AD B2C is a product designed to facilitate logins for your end user application. It is part of the Microsoft Identity Platform and has very similar features to mainstream Azure AD, but also has many differences. This repository is an organized collection of materials I'd recommend reviewing in order to learn how to use Azure AD B2C for user's that are both getting started, and also implementing more complicated scenarios.

## Getting Started

If you are just getting started with B2C, I'd recommend reviewing the following links in order. These documents will provide a good baseline of what the product is and how it's used. 

- Read this page for an overview of what the B2C product is and what it is designed for: [What is Azure Active Directory B2C?](https://learn.microsoft.com/en-us/azure/active-directory-b2c/overview)
- Azure AD B2C is a product grouped together in a suite called *External Identities*. Read more about the different external identities products here: [External Identities Overview](https://learn.microsoft.com/en-us/azure/active-directory/external-identities/external-identities-overview)
- Authentication and Authorization are sometimes terms that are used interchangeably, but they are different. [Authentication vs Authorization](https://learn.microsoft.com/en-us/azure/active-directory/develop/authentication-vs-authorization)
- Having a baseline understanding of the OIDC and OAuth2.0 protocols is important as well: [Authentication requests](https://learn.microsoft.com/en-us/azure/active-directory/develop/v2-app-types)
- Interfacing with the Microsoft Identity Platform is usually done through the Microsoft Authentication Library (MSAL). It can be done manually, but it is not recommended. [Overview of the Microsoft Authentication Library](https://learn.microsoft.com/en-us/azure/active-directory/develop/msal-overview)
- Applications that interface with the Microsoft Identity Platform must be registered with an *App Registration*. Read more about app registrations: [Application model](https://learn.microsoft.com/en-us/azure/active-directory/develop/application-model)
- Configuring the business logic for your users sign in experience is called a *User Journey* in B2C. In other words, User Journeys are how you define, step-by-step, what happens when a user goes through an authentication flow such as during sign-in or sign-up. You have two options for creating your User Journeys: *User Flows* and *Custom Policies*. User Flows are GUI-based and are designed for simple authentication scenarios. Custom Policies are based on XML files and are much more complex, but can support a wider range of scenarios. Read more about the differences h on [User flows and custom policies overview](https://learn.microsoft.com/en-us/azure/active-directory-b2c/user-flow-overview)


## Basics

If you're just getting started with B2C, I would recommend reviewing these links in order. 

- An overview of what Azure AD B2C is and what it's used for - https://learn.microsoft.com/en-us/azure/active-directory-b2c/overview
  - A deeper dive of how the pieces of B2C fit together - https://learn.microsoft.com/en-us/azure/active-directory-b2c/technical-overview

## Authorization

- A great sample written to explain how to use app roles in Azure AD B2C for authorization. Also explains the main differences between the other options. https://github.com/azure-ad-b2c/api-connector-samples/tree/main/Authorization-AppRoles

## Training Resources


## Other Resources or Notes

- Note that Azure AD B2C has a limitation with one OAuth2.0 authentication flow in particular called the *on-behalf-of* flow. This is a [documented limitation](https://learn.microsoft.com/en-us/azure/active-directory-b2c/access-tokens) that most often comes into play when building a microservice architecture in which each service needs awareness of who the user is and what they're doing. See Also: https://github.com/AzureAD/microsoft-identity-web/wiki/b2c-limitations 