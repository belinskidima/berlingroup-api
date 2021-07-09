# Introduction

## Definitions


Term | Definition
---------|----------
 **Authorisation** | The XS2A API will allow an ASPSP to implement OAuth2 as a support for the authorisation of the PSU towards the TPP for the payment initiation and/or account information service. In this case, the TPP will be the client, the PSU the resource owner and the ASPSP will be the resource server in the abstract OAuth2 model. |
 **Consent** | A range of rules on security, providing access to accounts, and enabling traceability and the mitigation of fraud risks. |
 **Provider** | Represents the ASPSP. A bank or financial institution that offer payment accounts with online access. |
 | **Provider** | Represents the ASPSP. A bank or financial institution that offer payment accounts with online access. |
| **TPP** | A third party provider application. |
| **Customer** | A bank account holder. The end-user of payment services. |
| **AISP** | Account Information Service Provider. A Client application that allows a Customer to list account and holder information. |
| **Session** | Any activity that is forwarded by Salt Edge PSD2 Compliance on behalf of a Customer. |
| **Scopes** | A set of permissions granted to a TPP application. |
| **SCA** | Strong Customer Authentication using SaltEdge Authenticator. |


## Registration

TPP may have a number of TPP Applications, them being essentially API keys(ID and secret). These applications serve to identify a specific TPP configuration. For example, say we have a company X that identifies itself as a PFM. Suppose it targets mobile devices(iOS, Android) and web browsers, thus they would have to configure three TPP applications, one for Apple devices, another for Android devices, and one for web browsers. Or maybe Company X needs to test their new features within staging environment first, then it would be convenient to configure another client application for these purposes.

But before managing API keys it is wise to check the TPP configuration. In order to do this, navigate to **[TPP Settings](https://priora.saltedge.com/clients/settings)**. Here it is possible to modify TPP's name, email, as well as other business details.

Take into consideration that all TPP Applications will have the same, predefined during registration, scopes. This will ensure that an AISP license certificate will be used only for getting information about Customer's banking details and PISP license certificates will allow creation of payment orders on behalf of Customer.

![dashboard1](https://priora.saltedge.com/assets/client_docs/client_details-a48e46f2276fdc6be8e04cb205b06ce5eff5c169a6bdb78632a694969d18c005.jpg)

In order to be able to go Live, TPP has to supply a valid certificate. This could be accomplished using tpp-certificates endpoint.

![](https://priora.saltedge.com/assets/client_docs/certificates-c68d0e283491d1497fa86bd66b222344228bfa831a9f73f952d981c3679dff9f.jpg)

Proceed by selecting **Test application**.

![](https://priora.saltedge.com/assets/client_docs/application_details-087a29ff3ff84c3be379d73331eb0f68b3b3d1494ac3ad85436d99694c2cd787.jpg)

On the page presented above it is possible to change application's **name** regenerate application **secret** and set up **callback** (also doubles as redirect) URL for updates from Salt Edge PSD2 Compliance Solution. In order for your TPP to go live, you must have configured at least one TPP application.


## Requesting Provider access

After successful registration and configuration, Salt Edge PSD2 Compliance Team will move TPP into **Test** status.

This will allow TPP to start making requests to all sandboxes available to Salt Edge PSD2 Compliance Solution.

![](https://priora.saltedge.com/assets/client_docs/provider_management-95a9c69712e3307138390d4d920324b6bd3d88974a77d61ad6067ae0d40d6e66.jpg)

After TPP finishes development, it can ask Salt Edge PSD2 Compliance Team to change its status to Live. This way, TPP will be able to request access for Live banks connected to Salt Edge PSD2 Compliance Solution.

## API Endpoints

The table below describes the list of all API endpoints available at Salt Edge PSD2 Compliance Solution. The endpoints are based on NextGenPSD2 Framework version 1.3.6. also known as BerlinGroup Standard. BerlinGroup endpoints are name-spaced after selected **provider_code**. Ex: for **NextGenPSD2Demobank**, the endpoints will start with **/nextgenpsd2demobank/api**...


