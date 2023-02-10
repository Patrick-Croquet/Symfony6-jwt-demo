# Symfony6-jwt-demo
 
composer require symfony/webpack-encore-bundle
npm install

npm run watch

npm install bootstrap

# dans app.js ajouter
import "bootstrap/dist/js/bootstrap.min.js";
# dans app.css ajouter
@import "~bootstrap/dist/css/bootstrap.min.css";


composer require symfony/security-bundle

symfony console make:user

symfony console make:migration
symfony console doctrine:migrations:migrate

symfony console make:registration-form

composer require symfonycasts/verify-email-bundle

# Commenter le ligne
#Symfony\Component\Mailer\Messenger\SendEmailMessage: async

symfony console make:controller Auth

# Symfony 6 and EasyAdmin 4
composer require symfony/webpack-encore-bundle

composer require easycorp/easyadmin-bundle

symfony console make:admin:dashboard

https://symfony.com/bundles/EasyAdminBundle/current/index.html

# Ajouter dans security.yaml
- { path: ^/admin, roles: ROLE_USER }

symfony console make:admin:crud

# Construire l'authentification et l'autorisation JWT
composer require "lexik/jwt-authentication-bundle"

# Générer une paire de clés
symfony console lexik:jwt:generate-keypair

# accès à l'API avec JWT
symfony console make:controller api

# Dans Git Bash
curl --insecure -X POST -H "Content-Type: application/json" -d '{"username":"patrick.croquet@afpa.fr","password":"Formateur"}' https://127.0.0.1:8003/auth

# Le token est créé
{"token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJpYXQiOjE2NzYwMjI0NzIsImV4cCI6MTY3NjAyNjA3Miwicm9sZXMiOlsiUk9MRV9VU0VSIl0sInVzZXJuYW1lIjoicGF0cmljay5jcm9xdWV0QGFmcGEuZnIifQ.Gh7LR44PNwckL-9estFb_N-Yricr9L_gUOsVeIMQUz4_zWdQ_kguo7_Gk5BMMqJSvgHPT37OKlivuc5vzUhKvKbfjrPfy3oRo0RNA9Kg6Rt_gvf4RIRVc5FvZsznBzc-p5Ov7gSgwoCUrONcyeH6PRrKTQs7EcTA52w6d1R80QErd3MiZXt7ltucsWonIea0nRfbE6r-C5nZFbxvV3rdblNi0bKJin36UsAQWmf2Vh3Uwd0rKJFcGoWLm567o3OXlCo3bBY7IkOInfmgwpS0Ln6c3t0KdalRxS4-_HzXz5x7v1ZXzfsD4AbA6fG5fr_nrliqbMhvOG95ZC97T6ePwg"}

# Utiliser le jeton
curl -o /dev/null -s -w "HTTP Response = %{http_code}\n" https://127.0.0.1:8003/api

curl -o /dev/null -s -w "HTTP Response = %{http_code}\n" -H "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJpYXQiOjE2NzYwMjI0NzIsImV4cCI6MTY3NjAyNjA3Miwicm9sZXMiOlsiUk9MRV9VU0VSIl0sInVzZXJuYW1lIjoicGF0cmljay5jcm9xdWV0QGFmcGEuZnIifQ.Gh7LR44PNwckL-9estFb_N-Yricr9L_gUOsVeIMQUz4_zWdQ_kguo7_Gk5BMMqJSvgHPT37OKlivuc5vzUhKvKbfjrPfy3oRo0RNA9Kg6Rt_gvf4RIRVc5FvZsznBzc-p5Ov7gSgwoCUrONcyeH6PRrKTQs7EcTA52w6d1R80QErd3MiZXt7ltucsWonIea0nRfbE6r-C5nZFbxvV3rdblNi0bKJin36UsAQWmf2Vh3Uwd0rKJFcGoWLm567o3OXlCo3bBY7IkOInfmgwpS0Ln6c3t0KdalRxS4-_HzXz5x7v1ZXzfsD4AbA6fG5fr_nrliqbMhvOG95ZC97T6ePwg" https://127.0.0.1:8003/api