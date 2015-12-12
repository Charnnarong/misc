#### This is basic steps to find what properties are available when using Camel components as an endpoint.

![alt text](http://i.imgur.com/Cl1aPPJ.png "figure 1")
(figure 1)


```xml
<to uri="jms:firstJms?concurrentConsumers=5" />
```

From figure 1, we want to find where "concurrentConsumers" comes from.

-----------------
1.) Look where jms definded. Which is
```xml
	<bean id="jms" class="org.apache.activemq.camel.component.ActiveMQComponent">
		<property name="connectionFactory" ref="myConnectionFactory" />
	</bean>
```
-----------------
2.) Find where ActiveMQComponent is. To do so, press Ctrl+Shift+T in any source code.
![alt text](http://i.imgur.com/8Q4w7Bu.png "figure 2")
(figure 2)
Click OK
-----------------
3.) Look at a class the component is extended from, in this case "JmsComponent"

![alt text](http://i.imgur.com/0aUS4Ul.png "figure 3")

-----------------
4.) Open Members view : Window > Show View > Other.. > Java Browsing > Members
![alt text](http://i.imgur.com/dCcB3p7.png "figure 4")

```java
    public void setConcurrentConsumers(int concurrentConsumers) {
        getConfiguration().setConcurrentConsumers(concurrentConsumers);
    }
```
-----------------
That is all.


