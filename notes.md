src/core/components/auth/authorization-popup.jsx -> Auths
src/core/components/auth/authorization-btn.jsx
src/core/components/auth/auths.jsx -> authorizeWithPersistOption
src/core/plugins/auth/actions.js

src/core/oauth2-authorize.js -> authorize case "password", "application", "accessCode", "implicit", "clientCredentials"
src/core/components/auth/oauth2.jsx: calls oauth2-authorize
src/core/presets/base.js bundles up react components including oauth2
src/core/auth/auths.jsx uses oauth2
src/core/components/auth/authorization-popup.jsx -> Auths


Error on authorization error:
src/core/components/errors.jsx


# GOAL

* Read `additionalFormParams` from openapi.json

## Trace back from src/core/plugins/auth/actions.js-> authorizeRequest

1. authorizeRequest: form (along with query, header, name, url, auth) is
   destructured from data
2. previous called by src/core/plugins/auth/actions.js-> authorizeApplication
   (and others). form consists of
   formWithAdditionalFormParams(form, schema.get("additionalFormParams"))
   schema (along with scopes, name, clientId, clientSecret) is destructured
   from auth. schema has the keys: flow, clientCredentials, tokenUrl, scope,
   type
3.


## Find out where openapi.json is read


