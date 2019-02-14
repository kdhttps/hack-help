https://blog.risingstack.com/node-js-interview-questions/

The differences between spies, stubs and mocks are mostly philosophical. In practice the terms are often used interchangeably as they all refer to particular kinds of test doubles. For one opinion on the difference between stubs and mocks see http://martinfowler.com/art... -- spies are test doubles that record how they were invoked (arguments, number of times called, and so on).

Sinon (see http://sinonjs.org/docs/), which the author uses in the example, defines the three terms as follows:

* spies are functions that record how (and how often) they were invoked
* stubs are spies that implement a specific behaviour
* mocks are stubs that fail if they are invoked incorrectly

So by that definition (as well as Fowler's), the test double in the example is a stub. The double itself doesn't have any expectation, but the test using it expects it to be invoked (which the stub records because the stub is also a spy).
