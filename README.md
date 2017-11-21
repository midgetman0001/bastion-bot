# Bastion  
Bastion is a [Discord](https://discordapp.com/) bot written in the NodeJS module [discord.io](https://github.com/izy521/discord.io), with a focus on functions related to the Yu-Gi-Oh! card game and a simulator of it, [YGOPro Percy](http://ygopro.co). The name comes from [an intellectual character](http://yugioh.wikia.com/wiki/Bastion_Misawa) in the related anime. All commands are case-insensitive.  
  
You can install a copy of Bastion yourself, more information on how below, but if you'd rather just use my copy, [here's](http://google.com) **(temporarily private)** the invite link. For support and feedback, my Discord server is [here](https://discordapp.com/invite/GrMGspZ), and you can support me on Patreon [here]( https://www.patreon.com/alphakretinbots).  
  
## Commands  
Bastion's primary purpose is a database of card information. Basic knowledge about relevant terms will be assumed in this section and the next. Note that Bastion's prefix is customisable - more information on that in the configuration section - this section assumes the default prefix of ".".  
  
A few general notes on card searching: My copy of Bastion references a card database with official cards, including recently revealed unreleased cards, anime cards from YGOPro Percy, and custom cards from the [G2 YGO Custom Server](https://discordapp.com/invite/Vv5NnCq). Bastion will search for the nearest guess if you don't type an exact name. Bastion has a system for hardcoded shortcuts - if you type a common abbreviation for a card name, it will try to convert it to the full name. Price data comes from the (http://yugiohprices.com)[http://yugiohprices.com] API. "Status" is a term I use for what YGOPro developers call "OT" - a designation that reflects whether a card is legal in the OCG, TCG, both, or other options for unofficial cards like Anime, Illegal and Custom.  
  
### Help  
Usage: `@Bastion#3599`  
  
Mentioning Bastion will provide a link to this readme.  
  
### Card Lookup  
Usage: `{card name|ID}`  
  
This command searches for a card by the name or YGOPro ID specified in the brackets and returns the card's name, all of its IDs in YGOPro, its status, its lowest, average, and highest prices if available, its types, its attribute if it's a monster, any stats, and its card text.  
  
As an example, `{dark magician}` returns the following output:  
![card output](/readme-images/card.png)  
  
### Card With Image  
Usage: `<card name|ID>`  
  
This command works the same way as the above command, but also displays an image of the card's artwork.  
  
As an example, `<stardust dragon>` returns the following output:  
![card image output](/readme-images/card-image.png)  
  
### .randcard  
Usage: `.randcard [opts]`  
  
The `.randcard` command will select a random card and display its information as if you searched it. The command accepts options that allow you to specify the status, level, type, or attribute of the card, as well as optionally display an image by including "image".  
  
As an example, `.randcard tcg/ocg 4 image` returns the following output:  
![.randcard output](/readme-images/randcard.png)  
  
### .script  
Usage: `.script [name|id]`  
  
The `.script` command searches for a card by name or YGOPro ID and returns a link to its script for YGOPro, as well as embedding it if short enough.  
  
As an example, `.script macro cosmos` returns the following output:  
![.script output](/readme-images/script1.png)  
![.script output 2](/readme-images/script2.png)  
  
### .matches  
Usage: `.matches [name]`  
  
The `.matches` command simulates a search for cards by name and returns the 10 closest matches for your search term, that share a status. This command ignores cards with the same name, for example alternate artworks.  
  
As an example, `.matches junk warrior` returns the following output:  
![.matches output](/readme-images/matches.png)  
  
### .trivia  
Usage: `.trivia [options]`  
For fun, Bastion can play a game where it will provide the art of a card, and players have 30 seconds to give its name, with a hint at 10 seconds. By default, the game will display TCG/OCG cards, but you can choose the status as an option. You can end the game prematurely by typing ".tq".  
  
## Installation  
If you so choose, you can run a copy of Bastion yourself! This section will assume some basic familiarity with NodeJS and the command line.  
  
All of Bastion's dependencies are properly documented in the package.json, so you can just download that, put it in a folder, and run `npm install`. To run the bot, the script expects some certain files - a configuration file, a shortcuts file, and any number SQLite databases containing card data, in the format YGOPro uses.  
  
### Configuration  
By default, the configuration file is called `config.json`, and is expected to be found in a subfolder of the local directory called `config`, i.e. `config/config.json`. The script expects `config.json` to contain a JSON object with the following properties:  
```json  
{  
	"TODO": "I gotta do this later when I'm home."  
}  
```  
`token` is the Discord User token that the discord.io module will use to log in to Discord. You can obtain a bot token through the [Discord Developers website](https://discordapp.com/developers/applications/me/).  
  
`prefix` is the text that Bastion will look for at the start of messages to indicate that it's a bot command. For example, if `prefix` is "b$", `.randcard` becomes `b$randcard`.  
  
TODO...  
  
### Shortcuts  
  
TODO...  
  
### Database  
  
TODO...
