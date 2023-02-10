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
- Configuring the business logic for your users sign in experience is called a *User Journey* in B2C. In other words, User Journeys are how you define, step-by-step, what happens when a user goes through an authentication flow such as during sign-in or sign-up. You have two options for creating your User Journeys: *User Flows* and *Custom Policies*. User Flows configuration is GUI-based and they are designed for the most common authentication scenarios. Custom Policies are configured via XML files and are much more complex, but can support a wider range of scenarios. Read more about the differences h on [User flows and custom policies overview](https://learn.microsoft.com/en-us/azure/active-directory-b2c/user-flow-overview)
- A technical overview that summarizes the main components of B2C: [Technical and feature overview of Azure Active Directory B2C](https://learn.microsoft.com/en-us/azure/active-directory-b2c/technical-overview)

## Custom Policies

Custom policies are one of the options available to configure the user experience in B2C. Configuration with Custom Policies and configuration with User Flows cannot be mixed together, you must use one or the other. If you have a scenario that is not supported in User Flows, you must move all your configuration to use Custom Policies, so it is very important to plan out your user experiences from the start so you can make the appropriate decision. 

Each page in the documentation usually has a "tab" at the top switching between the User Flow and Custom Policy documentation. To find out if what you'd like to do requires Custom Policies, visit the documentation page for the feature you'd like to use. It will say under the "User Flows" tab if it is unsupported in User Flows and if you must use Custom Policies. Example: [Azure AD (multitenant) identity provider](https://learn.microsoft.com/en-us/azure/active-directory-b2c/identity-provider-azure-ad-multi-tenant?pivots=b2c-user-flow)

To learn how to use Custom Policies, I'd recommend reviewing the following resources:

- Custom policies are made up of a lot of components, and have many moving pieces. Read [Custom policy overview](https://learn.microsoft.com/en-us/azure/active-directory-b2c/identity-provider-azure-ad-multi-tenant?pivots=b2c-user-flow) and all pages linked inside for a breakdown of all the pieces of a custom policy. You'll probably want to read it a few times. 

- The B2C product group (PG) has several custom policy "starter packs" they maintain. I would highly recommend starting from one of these instead of creating your own from scratch: [Custom Policy Starter Packs](https://github.com/Azure-Samples/active-directory-b2c-custom-policy-starterpack)
- [The schema reference for Custom Policies](https://learn.microsoft.com/en-us/azure/active-directory-b2c/technical-overview)
- This is a custom policy tutorial written by some of the B2C PG as well as some people from the community: [Custom Policy Concepts](https://azure-ad-b2c.github.io/azureadb2ccommunity.io/docs/custom-policy-concepts/)
  - There is also a series of [webinars](https://azure-ad-b2c.github.io/azureadb2ccommunity.io/training/recordings/) on OIDC, OAuth, and custom policies. 


## Authorization

- A great sample written to explain how to use app roles in Azure AD B2C for authorization. Also explains the main differences between the other options. https://github.com/azure-ad-b2c/api-connector-samples/tree/main/Authorization-AppRoles

## Training Resources


## Other Resources or Notes

- Note that Azure AD B2C has a limitation with one OAuth2.0 authentication flow in particular called the *on-behalf-of* flow. This is a [documented limitation](https://learn.microsoft.com/en-us/azure/active-directory-b2c/access-tokens) that most often comes into play when building a microservice architecture in which each service needs awareness of who the user is and what they're doing. See Also: https://github.com/AzureAD/microsoft-identity-web/wiki/b2c-limitations. 
- For troubleshooting (and later on monitoring), I'd recommend enabling log collection in your B2C tenant: https://learn.microsoft.com/en-us/azure/active-directory-b2c/troubleshoot-with-application-insights?pivots=b2c-custom-policy 