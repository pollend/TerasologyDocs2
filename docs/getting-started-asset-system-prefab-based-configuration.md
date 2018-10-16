---
id: asset_system_prefab_based_configuration
title: Latin-ish
sidebar_label: Add A New Creature
---

Modules may expose some values for configuration or tuning, independent from the code.
For example the rate how fast trees grow or how fast the player gets hungry.
If these values are hardcoded, other modules have a hard time to change them.

One way to achieve this is to expose the configuration by a prefab.

Take the following component as example:
```java
public class ConfigurationComponent implements Component{
    public String value1;
    public String value2;
    public String value3;
    public String value4;
    
}
```

We can define a prefab with this component in our module at `prefabs/configuration.prefab` with the following content:
```
{
    "Configuration" : {
        "value1" : "test1",
        "value2" : "test2",
        "value3" : "test3",
        "value4" : "test4"
    }
}
```

Now when using the values, load the prefab and obtain the values.
In this example we use a simple greeter which logs a message on the console when a players enters the server (or starts a local game):
```java
@RegisterSystem(RegisterMode.AUTHORITY)
public class Greeter extends BaseComponentSystem {

    private static final Logger LOG = LoggerFactory.getLogger(Greeter.class);


    @ReceiveEvent(components = ClientComponent.class)
    public void onConnect(ConnectedEvent event, EntityRef entity) {
        
        Optional<Prefab> prefab = Assets.getPrefab("configuration");
        ConfigurationComponent configuration = prefab.get().getComponent(ConfigurationComponent.class);
        LOG.info("Greeting with value {}, {}, {}, {}", configuration.value1, configuration.value2, configuration.value3, configuration.value3, configuration.value4);
    }
    
}
```

Note, that we use the prefab but do not create an entity from it.

Starting the game with the module activated should give a log output like 
```
Greeting with value test1, test2, test3, test4
```

Now lets say we define a second module which uses the first one but requires different values (e.g. a gameplay module which does balancing between separate modules).
In the second module, we can define a delta to the current prefab.
A delta is defined in the same way as a prefab, with the difference, that a delta overrides values from another modules prefab.

In the second module, create the file `deltas/<nameOfTheFirstModule>/prefabs/configuration.prefab` with the content:
```
{
    "Configuration" : {
        "value1" : "test1_2"
    }
}
```

When we now start the game using the second module, we should get the following log output:
```
Greeting with value test1_2, test2, test3, test4
```

***
### NOTE
Do not confuse the *deltas* folder with the *overrides* folder.  
See [[Deltas and Overrides|Deltas and Overrides]] for a detailed explanation.
***
