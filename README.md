# AI-TTRPG-RAG-System
## A flexible rag system that can take a AI API key, and process it using rules of a multitude of different TTRPG. 

## General Summary

The first iteration of translating a TTRPG into the rag system will be using the rule set of CANE. the way the player interacts is the GUI will set the scene with text and the player will type in a response of 150 charector max to interact with the scene. The story the charector is following is organized by a story arch, that contains chapters, that contain scenes. The general story arc is generated when the player creates a new story, chapters are mile stones within the story arc, each time a a player finishes a chapter the ai will do a deep analysis of the current arc to check if the general story arc still makes sense contexually. You can only have one milestone you are pursuing at a time that follows the story arc and finishes once the "pressure" point builds up to its max and the player either resolves or fails. each scene you take increases the pressure based on your actions, you can never decrease pressure.  

## How is the Data indexed? 

Through the splitting of the documents entered in predictable way, these are context cards that can also link to other context cards.  Catogories tracked by the State is geography and envirament, current setting scene, hunt area. pressure, effects, spells and attacks, player state, monsters, hooks, and npcs. current scene will have a purelt physical description base that will change based on the region and the current weather which is calculated based on the region and the time of year in story plus npcs current mood and player charectors mood if explicetly stated. under the physical description there is what has specific effects when interacted with. each pressure buildup there is a esculation in stakes within the story. the monster have a a goal and hunt pattern that it exuctes on every pressure increases within the hunt area, this will change the physical desctiption of the scene when it becomes the current setting by synthesising the monsters effect with the pysical description and when ignore players and npc mood when building description. player state will have a charector sheet on skills they can do and also a spell/attack sheet. 
## level of ability 
### how many it can effect
  1. one
  2. a few
  3. small group
  4. large group
  5. a crowd
  6. a large crowd
  7. thousand of peopl
  8. many thousand of people
### the size 
  1. human size
  2. heavy furniture 
  3. large animal
  4. vehicle
  5. building
  6. large building
  7. sky scarper
### area of effect 
  1. personal
  2. a few people
  3. entire room
  4. a few rooms
  5. a whole building
  6. a city block
  7. a whole nieghborhood
  8. a whole town
### distance 
  1. touch
  2. same room
  3. across the room
  4. down the block
  5. a few blocks away
  6. across town
  7. visual town
  8. visual range
  9. over the horizon
### speed 
  1. average
  2. fast human
  3. fast animal
  4. cat
  5. train
  6. maglev
  7. airliner
  8. jet fighter


AREA Personal A few people Entire Room A few rooms Whole building A city block A whole
neighborhood A whole town
DISTANCЕ
(0-2 Short)
(3-4 Long) Touch Same Room Across the
Street Down the Block A few blocks
away
Across town Visual range Over the horizon
(5+ Extreme)
SPEED Average human Fast human Fast animal Car Train Maglev Airliner Jet Fighter
MAGNITUDE Small Noticeable Large Very Large Massive Destructive Overwhelming Cataclysmi

# database starting design

# rolls 
only roll is the action is risky, contested, or unclear, or a action roll
## risky rolls 
an action should be risky if the situation is tense and there is some significant and clear consequence, or complication, or danger from a character's action. 
• On beating a dc by matching a number to 3 above, the outcome or consequence is about as expected, success or failure, with no further complications. 
• On losing a dc by 1 to 5, it’s worse than expected. Consequences might be a little worse, actions a little less effective or more complicated, even on a success. 
• On beating the dc by 4 above, it’s better than expected - the action is more effective, has lighter consequences, or reveals a sudden opportunity. 
• On a 1, it’s much worse than expected - the worst thing that could happen happens.
## fate rolls
fate roll is a 1d6 that is for something up to change 
• 1: Poorest result • 2-3: Poor result • 4-5: Good result • 6: Best result
## consequences 
when a player fails a roll or rolls low the game will impose a consequence or complication 
examples 
in attention (an exorcist is preoccupied for a while, or misses something important) • effectiveness (someone else needs to follow up to finish the job, slash a talisman (see pg. 17) one less time) • gear (tools or weapons break or jam, supplies or ammo are used up) • safety (the situation gets more risky) • time (miss opportunities, degrade situations) • Threaten an exorcist with more severe consequences unless further action is taken • Cut off an opportunity: a door closes, an NPC isn’t cooperative, someone gets away • Separate an exorcist • Force an exorcist to make a hard choice (dropping their ally off a building or saving their own skin). • Hinder an exorcist - make something harder for them until they can change the situation • Give a hook: Give a hook to an exorcist (see pg. 32) • Start a ticking clock - Set out a talisman (see pg. 17) with negative consequences, or slash an existing talisman this way

# talismans 
this and hooks are the main way to track complex actons. when actions are complicated and can't be solved in one roll a talisman entity is completed. talisman fill up and resolve when a certain number of slashes are completed, the longer the talisman, the longer the complexity of the task involved. talisman should be descriptive not proscriptive. 
• simple talismans are typically 1 or 2 segments 
• medium are 3-5 
• complex are 6-8

# player module

## stress and injuries

there's orginial player score and then current player score
your personal talisman has 6 slots for 6 stresses you can take. when it fills up you gain a injury that effects your player ability score. when you gain 3 injuries you are in the brink of death. some stress is non lethal and will never fill up your talisman up (leave 1 slot open)
### guide to how many slashes does a consequence those 
• 1 slash: Pain, strain, tiredness, suffering, minor injury 
• 2/3 slashes: Crippling or even fatal to most humans, injury, exhaustion, bleeding, deprivation, poison, etc. 
• 4+ slashes: Instantly and messily fatal to human (players are stronger then normal humans)
### injuries 
• a twisted ankle 
• a bleeding gunshot 
• poison taking hold of your body 
• deep mental distress 
• exhaustion

### hooks 
some complication are not immediate, instead of immediately apply consequence the game can assign a talisman that stats empty that when filled up give a consequence to the character
## supporting tables 
### ability score 
this is the generally ability of our player, each player has a ability's score and it references this table which has the description and other associating data. the ai references this table to find the difficulty rating
- **Strength**
- 1 (–5): Morbidly weak, has significant trouble lifting own limbs
- 2-3 (–4): Needs help to stand, can be knocked over by strong breezes
- 4-5 (–3): Knocked off balance by swinging something dense
- 6-7 (–2): Difficulty pushing an object of their weight
- 8-9 (–1): Has trouble even lifting heavy objects
- 10-11 (0): Can literally pull their own weight
- 12-13 (1): Carries heavy objects for short distances
- 14-15 (2): Visibly toned, throws small objects for long distances
- 16-17 (3): Carries heavy objects with one arm
- 18-19 (4): Can break objects like wood with bare hands
- 20-21 (5): Able to out-wrestle a work animal or catch a falling person
- 22-23 (6): Can pull very heavy objects at appreciable speeds
- 24-25 (7): Pinnacle of brawn, able to out-lift several people

- **Dexterity**

- 1 (–5): Barely mobile, probably significantly paralyzed
- 2-3 (–4): Incapable of moving without noticeable effort or pain
- 4-5 (–3): Visible paralysis or physical difficulty
- 6-7 (–2): Significant klutz or very slow to react
- 8-9 (–1): Somewhat slow, occasionally trips over own feet
- 10-11 (0): Capable of usually catching a small tossed object
- 12-13 (1): Able to often hit large targets
- 14-15 (2): Can catch or dodge a medium-speed surprise projectile
- 16-17 (3): Able to often hit small targets
- 18-19 (4): Light on feet, able to often hit small moving targets
- 20-21 (5): Graceful, able to flow from one action into another easily
- 22-23 (6): Very graceful, capable of dodging a number of thrown objects
- 24-25 (7): Moves like water, reacting to all situations with almost no effort

- **Constitution**

- 1 (–5): Minimal immune system, body reacts violently to anything foreign
- 2-3 (–4): Frail, suffers frequent broken bones
- 4-5 (–3): Bruises very easily, knocked out by a light punch
- 6-7 (–2): Unusually prone to disease and infection
- 8-9 (–1): Easily winded, incapable of a full day’s hard labor
- 10-11 (0): Occasionally contracts mild sicknesses
- 12-13 (1): Can take a few hits before being knocked unconscious
- 14-15 (2): Able to labor for twelve hours most days
- 16-17 (3): Easily shrugs off most illnesses
- 18-19 (4): Able to stay awake for days on end
- 20-21 (5): Very difficult to wear down, almost never feels fatigue
- 22-23 (6): Never gets sick, even to the most virulent diseases
- 24-25 (7): Tireless paragon of physical endurance

- **Intelligence**

- 1 (–5): Animalistic, no longer capable of logic or reason
- 2-3 (–4): Barely able to function, very limited speech and knowledge
- 4-5 (–3): Often resorts to charades to express thoughts
- 6-7 (–2): Often misuses and mispronounces words
- 8-9 (–1): Has trouble following trains of thought, forgets most unimportant things
- 10-11 (0): Knows what they need to know to get by
- 12-13 (1): Knows a bit more than is necessary, fairly logical
- 14-15 (2): Able to do math or solve logic puzzles mentally with reasonable accuracy
- 16-17 (3): Fairly intelligent, able to understand new tasks quickly
- 18-19 (4): Very intelligent, may invent new processes or uses for knowledge
- 20-21 (5): Highly knowledgeable, probably the smartest person many people know
- 22-23 (6): Able to make Holmesian leaps of logic
- 24-25 (7): Famous as a sage and genius

- **Wisdom**

- 1 (–5): Seemingly incapable of thought, barely aware
- 2-3 (–4): Rarely notices important or prominent items, people, or occurrences
- 4-5 (–3): Seemingly incapable of forethought
- 6-7 (–2): Often fails to exert common sense
- 8-9 (–1): Forgets or opts not to consider options before taking action
- 10-11 (0): Makes reasoned decisions most of the time
- 12-13 (1): Able to tell when a person is upset
- 14-15 (2): Can get hunches about a situation that doesn’t feel right
- 16-17 (3): Reads people and situations fairly well
- 18-19 (4): Often used as a source of wisdom or decider of actions
- 20-21 (5): Reads people and situations very well, almost unconsciously
- 22-23 (6): Can tell minute differences among many situations
- 24-25 (7): Nearly prescient, able to reason far beyond logic

- **Charisma**

- 1 (–5): Barely conscious, incredibly tactless and non-empathetic
- 2-3 (–4): Minimal independent thought, relies heavily on others to think instead
- 4-5 (–3): Has trouble thinking of others as people
- 6-7 (–2): Terribly reticent, uninteresting, or rude
- 8-9 (–1): Something of a bore or makes people mildly uncomfortable
- 10-11 (0): Capable of polite conversation
- 12-13 (1): Mildly interesting, knows what to say to the right people
- 14-15 (2): Interesting, knows what to say to most people
- 16-17 (3): Popular, receives greetings and conversations on the street
- 18-19 (4): Immediately likeable by many people, subject of favorable talk
- 20-21 (5): Life of the party, able to keep people entertained for hours
- 22-23 (6): Immediately likeable by almost everybody
- 24-25 (7): Renowned for wit, personality, and/or looks
