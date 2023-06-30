# spring-retry-example

. In spring-retry, we can retry the operations using the following annotations ,
a. The @EnableRetry annotation enables the spring retry feature in the application. 
We can apply it to any @Confguration class. 
The @EnableRetry scan for all @Retryable and @Recover annotated methods .It also configures RetryListener interfaces used for intercepting methods used during retries.

b. @Retryable It indicates retry can be applied on this method.
 We mention the exception type for which the retry should be done, the maximum number of retries and the delay between two retries using the backoff policy.
In the question given: maxAttempts =5 and delay = 5000( assume we have 5 seconds delay , so here we need to provide time in milliseconds, therefore value is 5000)

c. @Recover
It implies  the fallback method if all retries fail for a @Retryable method. 
The method accepts the exception that occurred in the Retryable method and its arguments in the same order.

For example, we created a simple Spring boot project to imitate the behavior of the scenario.
To expose one Rest API which will call one backend API operation.
Let us assume the backed API operation is prone to failure, and we will fail it randomly to simulate the service failures.
