========
Usage
========

====
Registering an Event/Listener
====

It's quite easy to setup an event, you need to create a new class that implements $Listener
Override the two methods below:

    $ public void onEvent(Event) and public void onPost(Event)

To register your events, simply use this method in your main plugin class:

    $ PluginRegistry.registerEvent(Plugin Instance, Event Class, Instance Object);
    $ PluginRegistry.registerEvent(this, RenderGameOverlayEvent.Text.class, new ExampleListener());

Currently, Tim's Mod uses the following events that you may listen to:
    * RenderGameOverlayEvent.Post
      - Used to render the tab gui and armor textures.
    * RenderGameOverlayEvent.Text
      - Used to render the text on screen like coordinates.
    * GuiOpenEvent
      - Used to override the custom main menu.
    * GuiScreenEvent
      - Used to write/render stuff on other guis. 
      - Will most likely be unnused in the future.

====
Registering your own Mod
====

Create a new class file and have it extend the class $Mod
You should implement the overloaded constructor and methods from the Mod class

    $ public Mod (String name, int key) { super(name, key); }
    /** Called when the mod is enabled. **/
    $ public void enable() {}
    /** Called when the mod is disabled. **/
    $ public void disable() {}
    /** Called every time the mod updates. (About every tick) **/
    $ public void run(Event event) {}
    /** Gets the category of the mod in the tab gui. **/
    $ public String getCategory() {}

Now you can register the Mod by constructing it.
     
    $ new ExampleMod("ExampelMod", Keyboard.KEY_A);


The rest is up to you on how you would like to use this API. It's still in early stages, and we will be adding more as time progresses. 