These tutorials/notes are for the IntelliJ IDE. They don't have to apply on other IDEs.  
Please let me know if anything here is incorrect or if there is a better way in doing something.
I just started yesterday and I am just trying to give some advice so that others won't waste as much time as I did in dealing with these problems. 

## To display messages to the IntelliJ console  
1. import org.slf4j.Logger;
2. import org.slf4j.LoggerFactory;
3. private static final Logger logger = LoggerFactory.getLogger(yourSystemName.class); // inside your class
4. logger.info("The message you want to print");

## Tutorial on detecting the block you are standing on

This code was extracted from the DamagingBlocks module  
  
    @RegisterSystem(RegisterMode.AUTHORITY)  
    public class yourSystemName extends BaseComponentSystem implements UpdateSubscriberSystem {
    private static final Logger logger = LoggerFactory.getLogger(speedBoosterSystem.class);

    @In
    private BlockEntityRegistry blockEntityProvider;

    @In
    private EntityManager entityManager;

    @In
    private WorldProvider worldProvider;

    @Override
    public void update(float delta) {
       // This foreach loop gets the player
       for (EntityRef entity : entityManager.getEntitiesWith(CharacterMovementComponent.class, LocationComponent.class)) {

            LocationComponent loc = entity.getComponent(LocationComponent.class); // Location component of player
            Vector3f pos = loc.getWorldPosition(); // Position of player
            pos.setY( pos.getY() -1 ); // Decrease Y-axis by one to get position under player
            Block block = worldProvider.getBlock(pos); // Get the block under the player
            logger.info( block.getDisplayName() ); // Print to the game console the name of the block
       }
    }

    }

## imports disappearing?
If you are using IntelliJ and your imports are disappearing once you add them, or at random. This is because IntelliJ only leaves the imports your code is using/accessing. In case this happens to you, do one of the following :  
1. Go to File->Settings->Editor->General->Auto Import and make sure "Optimize imports on the fly" is set to false.  
2. Write the code first and press Alt+Enter on the unimported class to automatically import them.
