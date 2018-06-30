Api will consume data from https://www.ing.nl/api/locator/atms/
and will print the result from base on the city provided
User will need autherization header to access the API

Following are the links to api

This is a current way to access api Currently only two users are allowed
1) Depanker:
`curl -H 'authorization: Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJkZXBhbmtlciJ9.MMt5if3HAMbXB2afrZ8j4Gp4tqfZ2LsU_7QfuofUj-eQeok4v5of8GWD-VnjbGpjQo_dw9I_y2UWjzIt2XUcTA' http://localhost:8080/backbase-test/ing-atm/page/filter/{city}`

Backbase:
`curl -H 'authorization: Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJiYWNrYmFzZSJ9.mIMC70Lgpwp6_YdsHER4yel0ciP_hjPFzFlGWS3tJkjSAqRGtqK5u-GLW4GrrUVzXygpfgO-KLWOxH-FL2npgA' http://localhost:8080/backbase-test/ing-atm/page/filter/{city}`

Api Documentation: http://localhost:8080/backbase-test/api-doc


The code was created using Intellij 2018.1.4 (Ultimate Edition)

Application uses spring security to secure camel rest endpoints
using SpringSecurityAuthorizationPolicy

Using the above any endpoint could be secured by applying policy bean as mentioned above application currently allow access to two
users depanker, backbase both are mentioned in application.yml (and JWT tokens are mentioned above)

Api doc mentions three possible http response codes are 200, 401 and 500

Testing is done by injecting mock data and not hitting actual endpoints

Test coverage is present in coverage-report folder

Solution is done using apache camel rest DSL along with spring boot.
