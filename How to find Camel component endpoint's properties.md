#### This is basic steps to find what properties are available when using Camel components as an endpoint.

![alt text](http://i.imgur.com/Cl1aPPJ.png "figure 1")
(figure 1)

From figure 1, we want to find where "concurrentConsumers" comes from.

```xml
<to uri="jms:firstJms?concurrentConsumers=5" />
```
