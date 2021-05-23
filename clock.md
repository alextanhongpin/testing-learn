# Testing Time

Instead of testing generated values, fix the value by freezing the time. This can be done by providing a factory that returns the actual time through dependency injection.

Hardcoding time in tests can be painful:
1. A promotion last for a certain period, and the price is discounted (hardcoded in tests during that time). After that specified time, the tests will break in CI.
2. Implementing tests that are time sensitive (like disabling certain feature at midnight) will cause unpredictable failure in CI/CD pipeline. Hardcoding the if/else in the tests makes the test wary of the business logic.
