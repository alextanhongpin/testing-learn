# testing-learn
How to excel at testing

- the basics
- what makes a good test
- is your code testable? structure matters
- testing clean architecture
- testing dependency or infra
- testing complex pipeline
- unit testing technique
- how to unit test microservice
- testing in containerized application
- how to cover all combinations of scenarios?
- how does testing relate to user story/requirements/use cases?
- writing user stories
- writing bdd - come up with a list of examples
- specification by examples
- writing use cases
- writing readme


# Scenarios

Take for example for user registration, we have the following variables:

- user state: registered/not registered
- email state: valid email/not valid email
- password state: valid password/not valid password

Which leaves us with the following combinations:
```
2x2x2 = 8 combinations
```

But since if the user is already registered, there are no possible combinations after that, that leaves us with only five test cases that needs to be covered, namely:

```
given that the user is already registered,
  when I register with email john.doe@mail.com and password 12345678
  then the account should not be created
  and I should receive an error

given that the user is not registered,
  // Single test vs multiple input test below.
  // when I register with email john.doe@mail.com and password 12345678
  // then an account should be created

  when I register with invalid email (list of invalid emails) and invalid password (list of valid passwords)
  then an account should not be created
  and I should receive an error

  when I register with valid email (list of valid emails) and invalid password (list of invalid passwords)
  then an account should not be created
  and I should receive an error

  when I register with invalid email (list of invalid emails) and valid password (list of valid passwords)
  then an account should not be created
  and I should receive an error
  
  when I register with valid email (list of valid emails) and valid password (list of valid passwords)
  then an account should be created
```

Test the scenario that will cause failure first - that is the priority. Test the success scenario last. For password, there are actually two scenarios, which is valid (length validation, format etc) and correctness (it matches the user password).
Also, we want to ensure that the user's password is not stored as plain text in the db, so it should be an additional test too.

## Fuzz Testing (Fuzzing)

https://en.wikipedia.org/wiki/American_fuzzy_lop_(fuzzer)

## QuickCheck

Property testing.


## String

Prepare fixtures for text:

- Long/short
- No whitespace long
- Empty
- Just white space
- Start white space
- End white space
- Chinese
- Korean
- Accented
- Foreign
- Emoji
- Scripts
- SQL injection
- Links 
- Promo code
- Email
- Phone number
