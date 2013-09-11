Creating a mission type should only be undertaken if you intend to produce a lot of content for it and it will serve an explicit purpose in regards to both gameplay and player reward. The default mission types in I&A 3 are there because they cover the vast majority of situations and help players attain pieces of I&A 3 (attach vehicles, emplacements and the like) that would otherwise be too easily obtainable.

It is worth noting that this is a process that I intend to make even easier, but obviously other core gameplay elements will come first. This currently requires the editing of files where I would prefer for there to be no editing at all so, eventually, this will all be possible through developer-focused files such as configs.

## Requirements

For these examples, we will call our new mission type `example`, with the full name of Example Missions. We'll only skim over the requirements here, so it's best to check the files of other mission types to understand the content.

1. Create `config\example.hpp`.
2. Create `config\hints\example.hpp`.
3. Create `config\markers\example.hpp`.
4. Create `config\notifications\example.hpp`.
5. In `init\server.sqf`, scroll to the bottom and find the `MISSIONS` section. Find the line that, by default, reads `} foreach ["tactical", "ghost", "priority"];` and add your new mission code. In this example, we'd change this line to `} foreach ["tactical", "ghost", "priority", "example"];`.
6. Create an `example` folder in the `missions\` directory and start adding your new missions! (e.g. `missions\example\stabTheMan`, `missions\example\kissTheWonka`)
7. In each mission folder, be sure to create a `mission.fsm` that ends by setting the global variable `result` to either `true` (success) or `false` (failure).

That's all! So, it does take a bit of set-up here and there as you need to figure out what your markers will look like, how your notifications are presented and a good few other bits and bobs, but if you have a solid plan it's a pretty easy process.
