---
layout: default
title: CAS - InMemory Service Registry
---

# InMemory Service Registry

This is an in-memory services management tool seeded from registration beans wired via Spring beans.

```xml
<util:list id="inMemoryRegisteredServices">
    <bean class="org.apereo.cas.services.RegexRegisteredService"
          p:id="1"
          p:name="HTTPS and IMAPS services on example.com"
          p:serviceId="^(https|imaps)://([A-Za-z0-9_-]+\.)*example\.com/.*"
          p:evaluationOrder="0" />
</util:list>
```

<div class="alert alert-info"><strong>Caveat</strong><p>
This component is <strong>NOT</strong> suitable for use with the service management webapp since it does not persist data.
On the other hand, it is perfectly acceptable for deployments where the XML configuration is authoritative for
service registry data and the UI will not be used.
</p></div>

## Auto Initialization

Upon startup and if the services registry is left blank, 
the registry is able to auto initialize itself from default 
JSON service definitions available to CAS. 

To see the relevant list of CAS properties, please [review this guide](Configuration-Properties.html).

