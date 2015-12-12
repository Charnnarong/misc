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
3.) Look at a package where the component is. There will be xxxEndpoint.class, in this case "ActiveMQEndpoint.class"

![alt text](http://i.imgur.com/0aUS4Ul.png "figure 3")
(figure 3)

Open an extends class if it was presented. In this case "JmsEndpoint"
```java
public class ActiveMQEndpoint extends JmsEndpoint {
```

-----------------
4.) Open Members view : Window > Show View > Other.. > Java Browsing > Members
![alt text](http://i.imgur.com/ZbnMi2f.png "figure 2")
On the right hand side, all members (setter for property) are listed.

-----------------
That is all.
For "timer" , to find its properties available, this approach is also applied. You will be end up with "TimerEndpoint.class"

