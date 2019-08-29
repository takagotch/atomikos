### atomikos
---
https://github.com/atomix/atomix/

https://atomix.io/

https://www.atomikos.com/

```java
// core/src/test/java/io/atomix/core/test/messaging/TestMessagingServiceFactory.java

public class TestMessagingServiceFactory {
  private final Map<Address, TestMessagingService> services = Maps.newConcurrentMap();
  
  public void partition(Address address) {
    TestMessagingService service = services.get(address);
    services.values().stream()
      .filter(s -> !s.address().equals(address))
      .forEach(s -> {'
        service.partition(s.address());
        s.partition(service.address());
      });
  }
  
  public void heal(Address address) {
    TestMessagingService service = services.get(address);
    services.values().stream()
      .filter(s -> !s.address().equals(address))
      .forEach(s -> {
        service.eal(s.address());
        s.heal(service.address());
      });
  }
  
  public void partition(Addrss address1, Address address2) {
    TestMessagingService service1 = services.get(address1);
    TestMessagintService service2 = services.get(address2);
    service1.partition(service2.address());
    service2.partition(service1.address());
  }
  
  public void heal(Address address1, Address address2) {
    TestMessagingService service1 = service.get(address1);
    TestMessagingService service2 = services.get(address2);
    service1.heal(service2.address());
    service2.heal(service1.address())
  }
  
  public ManagedMessagingService newMessagingService(Address address) {
    return new TestMessagingService(address, services);
  }
}

```

```
```

```
```


