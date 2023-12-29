# Rayter Template
This is a template for creating a Rayter site. Rayter is a program that can be used to rank players in games and using this template you can create a website that displays the rankings.

## What is a Rayter site?

A Rayter site is a website that is generated from a GitHub repository. The site contains a list of games and a list of players. For each game, there is a list of players ranked by their Rayter rating for that game. See [What is the Rayter rating?](#what-is-rayter) for more information about Rayter.

The site is generated from a GitHub repository and is hosted by GitHub Pages. The site is updated automatically when you update [game files](#game-files) in the repository.

## Quick start
* Fork the GitHub repository https://github.com/rayter-org/rayter-template by clicking the "Fork" button. You will need to be logged in to GitHub to do this.
* Navigate to Actions and click "I understand my workflows, go ahead and enable them". This is necessary to enable the functionality of the Rayter site.
* Go to Settings/Pages in your new repository and change "Source" to "GitHub Actions".
* Go back to Code and create a file named after your game (poker.txt if you are playing Poker, for example). See [game files](#game-files) for more information about the file format.
* Remove hearts.txt (since you probably don't want to keep the included example games).
* Change site_name in config/rayter.toml to something else, if you want to.
* Visit Settings/Pages again and click on the link that is displayed after "Your site is live at"

## Game files
The game files list all matches played within a specific game. Game files are named after the game they represent, for example poker.txt, and always reside in the root of the repository. They are plain text files and have a .txt extension. See [the file format specification](https://github.com/peterjaric/rayter/blob/master/README.md) to learn more. Currently these files need to be updated manually, but in the future there will be a web interface for this.

## What is the Rayter rating?
The Rayter rating for a player is a number that is calculated from the results of the games that the player has played. The rating is calculated using the Rayter algorithm, which is described in the [Rayter repository](https://github.com/peterjaric/rayter?tab=readme-ov-file#rayter-algorithm). In short, it gives a pretty good estimate of the skill of a player in a game.

## Configuration
There are two ways to configure your Rayter site. You can setup the site itself and you can customize each player.

### The site
The site is configured in ./config/rayter.toml. Currently it is possible to change the name and the description that is displayed on the front page. Example:

```
site_name = The Game Group
site_description = Game rankings for our local game group.
```

### Players
In ./config/players.json you can add custom avatar images, custom email addresses and custom display names for any number of players, like this:

```
{
      "Dahlia": {
            "imageUrl": "https://images.example.com/dahlia.jpg"
      },
      "Lee": {
            "displayName": "The Boardgamer",
            "email": "boardgamer@example.com"
      }
}
```
