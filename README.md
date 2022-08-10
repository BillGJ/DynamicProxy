# Exercise: Dynamic Proxy

This program's goal is to create a prototype data access object, 
and a *Dynamic Proxy* is the perfect tool for the job. 

What's so "dynamic" about this proxy, you might ask? Well, the proxy itself is implemented at runtime. 
This means you can create a dynamic proxy for any interface, 
and the proxy implements that interface dynamically 
— as methods get called on the proxy object, 
the proxy is able to examine the method calls and arguments as they come in, 
and decide on-the-fly how to handle them.

In this case, my dynamic proxy will be handling method calls by looking up properties 
from the property map (a `Map<String, Object>`).

Notice that, `UdacisearchClient` is an interface and not a class. 
That's because Java's dynamic proxy (`java.lang.reflect.Proxy`) only works on interfaces, not classes.


## Compiling and running

    javac -cp . Main.java
    java -cp . Main

If everything worked, you should see the client information printed to standard output:

    {quarterlyBudget=8000, numEmployees=5, name=CatFacts LLC, timeZone=America/Los_Angeles, id=17, billingAddress=555 Meowmers Ln, Riverside, CA 92501, contractStart=2020-10-11T23:03:39.374133Z, contractLength=PT4320H}
    UdacisearchClient{name='CatFacts LLC', id=17, quarterlyBudget=8000, numEmployees=5, contractStart=2020-10-11T23:03:39.374133Z, contractLength=PT4320H, timeZone=America/Los_Angeles, billingAddress='555 Meowmers Ln, Riverside, CA 92501'}