## How to request SCiMMA OIDC integration for your application 
In order to register an OIDC client with the SCiMMA organization, please supply the following information to anders15@uwm.edu:

*Name* : During a login flow your users will see this name printed on the
consent screen. Choose a name for your application that makes sense 
for your users.

*Home URL* : The name above will be hyperlinked using this URL. Use a link
that makes sense for your service and your users. Again, the point is to
help them make a decision during the consent screen. The user will not 
be authenticated when going to this URL.

*Callbacks* : One or more redirect_uri URLs. This is the URL to which the 
browser will be redirected with the authorization code. It will be consumed 
by the OIDC client library your application uses. You should consult the 
documentation for your application or OIDC library on what the callback 
should be. You may have more than one, for example to assist with development.

*Scopes* : Choose the scopes your client needs. The scopes that CILogon
supports and the resulting claims are detailed in the section "Scopes"
[here](https://www.cilogon.org/oidc).

*LDAP to Claim Mappings* :  By default CILogon will pass through the claims
from the upstream campus IdP. If instead you want claim values to come
from the SCiMMA COmanage Registry you can specify which attributes to 
pull from LDAP and which claims to populate with the attribute values. 
You can override "standard" claims or add new ones or both. 

Commons LDAP to Claim Mappings configurations are
```
givenName -> given_name
sn -> family_name
mail -> email
isMemberOf -> is_member_of
voPersonID -> vo_person_id
```
In general, just tell us what you information about the user you want and we will try to provide it.

## Configuring your application
We will return two strings to you when your application is registered, the cilentID and a secret key. You must save this information in a safe place since your application cannot work without them (and anyone can set up an application to impersonate yours if they have this information). The particulars of how to use these strings to configure your clients are library or application dependent, so check your documentation.
