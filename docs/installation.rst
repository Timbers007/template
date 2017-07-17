============
Installation
============

You can install the library through adding the mod as an external library through your IDE, if you use one.

Once you've installed it, you'll have to add tim's mod as a dependancy to your mod, or some features will not work. You can do this like at the top of your class header:
     
    $ @Mod(dependencies = Core.MODID, modid = "exampleplugin", version = "1.0.0.0", name = "exampleplugin")

Now, simply add your required Forge method loaders (FMLInitializationEvent, etc.).

Next, in one of those methods you'll have to register your plugin with Tim's Mod. You can do this by:

    $ PluginRegistry.registerPlugin(this, this);

That's all, you now have a basic plugin with Tim's Mod.