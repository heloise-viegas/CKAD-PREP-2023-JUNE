## 27-JUNE-2023

## Day4

## Configuration

**Configuration** *Service Accounts*

### Service Accounts
1. used by application to access cluster
 2. Create SA, create Token for the SA, Attach SA in the deployment
                     

**Commands**
 1. kubectl create SA sa-name
 2. kubectl create token sa-name
 3. In yaml file : serviceAccountName: sa-name


Links :
- https://kubernetes.io/docs/reference/access-authn-authz/service-accounts-admin/


Questions :

- https://github.com/bmuschko/ckad-prep/blob/master/2-configuration.md#using-a-service-account
- https://github.com/dgkanatsios/CKAD-exercises/blob/main/d.configuration.md#serviceaccounts
![image](https://github.com/heloise-viegas/CKAD-PREP-2023-JUNE/assets/37453877/f2f269cb-d9e3-470b-a33f-53aa5e9e7b68)



