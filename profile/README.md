# Chimera RPG
Chimera is a work-in-progress multiplayer RPG written in Go. It is intended to be easy to make content for, including new graphics, objects, and maps.

The current complete features:
  * Tile-based in three dimensions!
  * Client/Server
    * Networking stack
    * Animation, Sounds, and Images transfer and management
    * Optional encryption
    * Account registration/login
    * Basic character creation
    * Reconnection to character
    * Map traveling
    * Character movement
    * Basic object inspection
    * Object and Map scripting
    * Lots of other things that are to be expanded on in the future
  * Editor
    * Map creation, loading, and saving
    * Object placement
    * Fill, magic wand, draw
    * Shape copying
    * Other shape features
    * Script editor
    * Properties editing
    * In-map object editing

A basic list of the code objects and ideas in place are:
  * Archetypes
    * Used to instantiate game world objects.
    * Can inherit from other Archetypes, either merging or overriding fields.
    * Scripting!
  * Maps
    * Each tile can contain archetypes. These archetypes work exactly like normal Archetypes with inheritance.
    * Scripting!
  * Objects
    * Optimized "live" instances of archetypes that can be: bullets, spells, players, tiles, blocks, enemies, and more.
  * Owners
    * Owners are used for managing client-to-character interaction, handling commands from the client and creating the necessary actions for the character object to use.
    * Owners are also used for AI control (WIP)
  * Actions
    * Actions are what certain Objects handle during their processing loop. These determine attacking, moving, and more.
  * Statuses
    * Statuses are placed upon Objects and handle features such as squeezing, swimming, falling, and otherwise.
  * Events
    * Events can be emitted by various sources, such as Statuses, the results of an Action, or scripting. They are used to trigger sound effects, messages, and more.
  * Players
    * A Player represents a game account. It contains credentials along with Characters and their meta information.
  * Character
    * A Character is a single playable character that exists in the game. It uses an Archetype for storing information, and this is used by an ObjectCharacter to determine features such as statistics, equipment, and more.
