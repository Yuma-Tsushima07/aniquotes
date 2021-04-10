# aniquotes
Collects anime quotes for node.js, discord.js !
Who doesn't like a dose of anime from time to time, maybe a quote to motivate you?

## Usage

### Discord.js Example
```js
const { MessageEmbed } = require('discord.js');
const { randomQuote } = require('aniquotes-npm')
const { searchAnime } = require('node-kitsu'); // credits to the person who made node-kitsu!!
module.exports = {
  name: "aniquote",
run: async ( client, message) => {

    const { quote, anime, id, name } = randomQuote();

    const res = await searchAnime(anime,0).catch(()=>{}) || [];

    const image = res?.[0]?.attributes?.coverImage?.original || null;

    return message.channel.send(
      new MessageEmbed()
      .setColor(`#b60c0c`)
      .addField(`Quoted from ${anime}*`,`${quote}\n\n-${name}`)
      .setImage(image)
      .setTimestamp()
      .setFooter('Made by Yuma-Tsushima07 with ❤️')
    );
  }
};
```

### Node.js
```js
const aniquote = require('aniquotes-npm')
 
// Shows a random anime quote
console.log(aniquote.randomQuote())
 
// You can also fetch quotes by their id
console.log(aniquote.getQuote(7))
 
// Fetching quotes from an anime! Nice!!
console.log(aniquote.getQuotesByAnime('Tokyo Ghoul'))
 
// Who said you couldn't fetch quotes from a character!
console.log(aniquote.getQuotesByCharacter('Sakura Kinomoto'))
```
### Further Examples

#### Random Quotes
```js
const aniquote = require('aniquotes-npm')

module.exports = {
    name: "animequote",
    run: async (client, message, args) => {

console.log(aniquote.randomQuote())
    }
}
```
##### Result
```
{
  quote: 'Why do people have to work? I just want to eat and sleep. I should have born as a panda at the zoo.',
  anime: 'Bakuman',
  id: 4136,
  name: 'Kazuya Hiramaru'
}
```
#### Quotes by Searching up with ID
```js
const aniquote = require('aniquotes-npm')

module.exports = {
    name: "animequote",
    run: async (client, message, args) => {
        console.log(aniquote.getQuote(7))
    }
}
```

##### Result
```json
{
  quote: "Let's make our past fade into comparison with the present.",
  anime: "Bokura ga Ita",
  id: 7,
  name: "Motoharu Yano"
}
```
#### Finding quotes by Anime name
```js
const aniquote = require('aniquotes-npm')

module.exports = {
    name: "animequote",
    run: async (client, message, args) => {
        console.log(aniquote.getQuotesByAnime('Tokyo Ghoul'))
 
    }
}
```

##### Result

```
[
  {
    quote: "You're wrong. It's not the world that's messed up; it's those of us in it. Yes, some ghouls walk a path that leaves sorrow in their wake, but just like humans, we can choose a 
different path altogether. We have a lot to learn, both your kind and mine. We need to stop fighting, and start talking. Because when it comes to the state of the world, you can't point your finger at ghouls or humans. We're all to blame.",
    anime: 'Tokyo Ghoul',
    id: 8440,
    name: 'Kaneki Ken'
  },
  {
    quote: "Books are nice, aren't they? With just one sentence you can get lost in all sorts 
of dreams. They way I think of it, literature allows the reader's consciousness to deeply relish the author and be closer to him. And so, we freely walk around the world of the story from 
the yarn spinner's point of view. It's only when you immerse yourself in the world of a book that you are able to forget just who you are.",
    anime: 'Tokyo Ghoul',
    id: 8420,
    name: 'Shuu Tsukiyama'
  },
  {
    quote: "After you've gobbled him down you'd be left alone to regret it while covered in blood and guts. That's the hunger of a ghoul. That's our destiny.",
    anime: 'Tokyo Ghoul',
    id: 8083,
    name: 'Touka Kirishima'
  },
  {
    quote: 'All we can do is live while losing things.',
    anime: 'Tokyo Ghoul',
    id: 8078,
    name: 'Renji Yomo'
  },
  {
    quote: 'As my fingers and toes re-grew like fingernails or hair over and over and over and over... and over again, every single time I got the feeling that I truly, truly truly was a monster.',
    anime: 'Tokyo Ghoul',
    id: 8074,
    name: 'Kaneki Ken'
  },
  {
    quote: 'Never trust anyone too much, remember the devil was once an angel.',
    anime: 'Tokyo Ghoul',
    id: 8070,
    name: 'Kaneki Ken'
  },
  {
    quote: "As long as it's for the right cause, there's nothing wrong with playing dirty.",  
    anime: 'Tokyo Ghoul',
    id: 7795,
    name: 'Kureo Mado'
  },
  {
    quote: 'We can only live while we lose.',
    anime: 'Tokyo Ghoul',
    id: 7778,
    name: 'Renji Yomo'
  },
  {
    quote: 'Why should I apologize for being a monster? Has anyone ever apologized for turning me into one?',
    anime: 'Tokyo Ghoul',
    id: 7736,
    name: 'Juuzou Suzuya'
  },
  {
    quote: 'If an angelic being fell from the sky and tried to live in this world of ours, I think even they would commit many wrongs.',
    anime: 'Tokyo Ghoul',
    id: 7168,
    name: 'Juuzou Suzuya'
  },
  {
    quote: 'I led me by the hand, as if to fill the niches in the memories in my oozing brain 
fluid. Without even a destination, we kept walking. Disgusting clouds were floating in the sky. I already know what will happen to me the next time I wake up.',
    anime: 'Tokyo Ghoul',
    id: 7094,
    name: 'Kaneki Ken'
  },
  {
    quote: "The bird fights it's way out of the egg. The egg is the world. Who would be born, 
must first destroy a world.",
    anime: 'Tokyo Ghoul',
    id: 7093,
    name: 'Tokyo Ghoul'
  },
  {
    quote: "I know I haven't always made the right decisions up to now... Whether I was right, or whether I was wrong, may not even matter in the first place. However, running up against my sins like this-- all of the choices I've made up to this point-- today, being able to die for someone-- is something I'm glad for... ",
    anime: 'Tokyo Ghoul',
    id: 7063,
    name: 'Irimi Kaya'
  },
  {
    quote: "There's no way someone who can't even protect himself can protect anyone else, is 
there?",
    anime: 'Tokyo Ghoul',
    id: 7018,
    name: 'Touka Kirishima'
  },
  {
    quote: "I was wrong. I wasn't eating ghouls. I'm the one who was being eaten.",
    anime: 'Tokyo Ghoul',
    id: 7010,
    name: 'Kaneki Ken'
  },
  {
    quote: 'Human relationships are chemical reactions. If you have a reaction then you can never return back to your previous state of being.',
    anime: 'Tokyo Ghoul',
    id: 7000,
    name: 'Kaneki Ken'
  },
  {
    quote: "Whose fault is it that things ended up like this? Coincidence? An accident? Fate? 
There's no such thing as fate. It's simply a combination of one circumstance and the next. And who is it that creates those circumstances? Who is it? It's you.",
    anime: 'Tokyo Ghoul',
    id: 6751,
    name: 'Rize Kamishiro'
  },
  {
    quote: "All suffering in the world is born from an individual's incompetence.",
    anime: 'Tokyo Ghoul',
    id: 6750,
    name: 'Yakumo Oomori'
  },
  {
    quote: "We're always trying to justify our actions with ideals. But ideals cannot give grounds for killing another person. The act of taking a life will always be considered... evil.",    anime: 'Tokyo Ghoul',
    id: 6738,
    name: 'Yoshimura'
  },
  {
    quote: "You think something like that would hurt, after all I've been through?",
    anime: 'Tokyo Ghoul',
    id: 6721,
    name: 'Kaneki Ken'
  },
  {
    quote: 'Why is it that the beautiful things are entwined more deeply with death than with 
life?',
    anime: 'Tokyo Ghoul',
    id: 6638,
    name: 'Kaneki Ken'
  },
  {
    quote: `Isn't it arrogant to put a price on whether life is "higher" or "lower", Kaneki? We are just bags of meat. The weak bow down and the strong devour them. Rather, if you compared them to all living things, it's humans who have shaved away the most lives. We are different 
than them.\r\n` +
      ' ',
    anime: 'Tokyo Ghoul',
    id: 6219,
    name: 'Shuu Tsukiyama'
  },
  {
    quote: "You don't need to blame yourself just because you've hurt someone, just like when 
you're walking you can't really blame yourself to crush some ants... that's what being stronger ones means. ",
    anime: 'Tokyo Ghoul',
    id: 6218,
    name: 'Shuu Tsukiyama'
  },
  {
    quote: "I'm not going to protect you by being your shield or armor, but I'll be the dagger hidden below your pillow.",
    anime: 'Tokyo Ghoul',
    id: 6212,
    name: 'Shuu Tsukiyama'
  },
  {
    quote: `My severe injuries had healed and the sweet taste of blood coated my mouth. I kept walking, my goal vague...trying to dispel the building unease in my chest... Upon entering an open area was the scent of rotting flowers and in the middle of the flowerbed, he stood... Without anyone saying a thing, without his name given, like an unsolved puzzle falling into place by itself, just by seeing that figure, I--understood exactly who I faced. The CCG's reaper. 
The undefeated ghoul investigator. A cold, vivid gaze. There, stood the God of Death. Why was 
it that I was seeing beauty in death rather than life? Strangely, I thought he was beautiful... Disoriented, I had failed to comprehend the scene before my eyes. It was not anything like flowers but a large amount of "Death". Had he done this alone?... It's a lie... Koma...Irimi...After all that... No matter how I tried to rouse my will to fight with hatred, more than sorrow, more than rage, the emotion that arose within me was despair. \n` +
      "Because 'my turn' was next.",
    anime: 'Tokyo Ghoul',
    id: 6202,
    name: 'Kaneki Ken'
  },
  {
    quote: '...The act of taking is equally evil. We, from the moment of birth, continue to take. Food, connections, even fellow blood. Living to utmost. Continuing to slaughter, kill, take. Life is to constantly sin. Life is evil itself. I am aware I am evil... And so are you all. Now, come kill me. And I shall do the same!',
    anime: 'Tokyo Ghoul',
    id: 6196,
    name: 'Yoshimura'
  },
  {
    quote: 'You only need a strong will and a clear purpose.',
    anime: 'Tokyo Ghoul',
    id: 6195,
    name: 'Kureo Mado'
  },
  {
    quote: 'The world runs on power. Everything is determined by the superior power. You are weak. That is why you lose.',
    anime: 'Tokyo Ghoul',
    id: 6117,
    name: 'Ayato Kirishima'
  },
  {
    quote: 'We need to have a mask that we never take off.',
    anime: 'Tokyo Ghoul',
    id: 6071,
    name: 'Uta'
  },
  {
    quote: "It's better to be hurt than to hurt others. Nice people can be happy with just that.",
    anime: 'Tokyo Ghoul',
    id: 5912,
    name: 'Kaneki Ken'
  },
  {
    quote: "I'm begging you, don't make me a killer!",
    anime: 'Tokyo Ghoul',
    id: 5882,
    name: 'Kaneki Ken'
  },
  {
    quote: 'Doing what one likes is the right of the powerful.',
    anime: 'Tokyo Ghoul',
    id: 5750,
    name: 'Yakumo Oomori'
  },
  {
    quote: 'If you were to write a story with me in the lead role, it would certainly be... a 
tragedy.',
    anime: 'Tokyo Ghoul',
    id: 5742,
    name: 'Kaneki Ken'
  },
  {
    quote: "There are times when you have to give up on one thing to preserve the other. Your 
mother couldn't. That isn't kindness. That's just being weak.",
    anime: 'Tokyo Ghoul',
    id: 5741,
    name: 'Rize Kamishiro'
  },
  {
    quote: "Sometimes good people make bad choices. It doesn't mean they are bad people. It means they're human.",
    anime: 'Tokyo Ghoul',
    id: 5740,
    name: 'Kishou Arima'
  },
  {
    quote: "When you're in front of the enemy, even if your hands are trembling - fight.",    
    anime: 'Tokyo Ghoul',
    id: 5703,
    name: 'Kureo Mado'
  },
  {
    quote: "What's wrong isn't me, what's wrong is the world!",
    anime: 'Tokyo Ghoul',
    id: 5640,
    name: 'Kaneki Ken'
  },
  {
    quote: "If you like, you can stay over here tonight. If you're lucky, you may see some cannibalism and that's always fun...",
    anime: 'Tokyo Ghoul',
    id: 5419,
    name: 'Uta'
  },
  {
    quote: 'I  can neither live with you. Nor without you.',
    anime: 'Tokyo Ghoul',
    id: 5418,
    name: 'Uta'
  },
  {
    quote: "All of the disadvantage in this world stems from a person's lack of ability.",    
    anime: 'Tokyo Ghoul',
    id: 5302,
    name: 'Rize Kamishiro'
  },
  {
    quote: "It's not because we can't take vengeance that we should feel sorry. The real reason to feel sorry... is when one is hung up on revenge and can't live their own life.",
    anime: 'Tokyo Ghoul',
    id: 5184,
    name: 'Yoshimura'
  }
]
```

#### Get quotes by anime character 
```js
const aniquote = require('aniquotes-npm')

module.exports = {
    name: "animequote",
    run: async (client, message, args) => {
        console.log(aniquote.getQuotesByCharacter('Sakura Kinomoto'))
 
    }
}
```


##### Result

```
[
  {
    quote: 'You are the most important person to me in the whole wide world.',
    anime: 'Tsubasa Reservoir Chronicle',
    id: 2946,
    name: 'Sakura Kinomoto'
  },
  {
    quote: "Uhh.. Syaoran.. it's okay if you don't have any more feelings for me, that doesn't matter to me at all. But I'm in love with you and I just wanted you to know, that's all.",   
    anime: 'Tsubasa Reservoir Chronicle',
    id: 2945,
    name: 'Sakura Kinomoto'
  },
  {
    quote: "*Holding Syaoran's hand* If I sleep like this, the first person I want to see when I wake up, is Syaoran.",
    anime: 'Tsubasa Reservoir Chronicle',
    id: 1359,
    name: 'Sakura Kinomoto'
  },
  {
    quote: `In my room at the palace, right before I go to sleep... I always think to myself, 
"What's Syaoran doing right now? Is he thinking about me?".`,
    anime: 'Tsubasa Reservoir Chronicle',
    id: 1354,
    name: 'Sakura Kinomoto'
  },
  {
    quote: 'Because I wished for everyone to live, I did everything I could.',
    anime: 'Tsubasa Reservoir Chronicle',
    id: 1349,
    name: 'Sakura Kinomoto'
  },
  {
    quote: "You really loved Mr. Clow, didn't you? It hurts, doesn't it? It hurts to lose someone you love.",
    anime: 'Cardcaptor Sakura',
    id: 1168,
    name: 'Sakura Kinomoto'
  },
  {
    quote: 'I am not a monster!',
    anime: 'Cardcaptor Sakura',
    id: 1158,
    name: 'Sakura Kinomoto'
  },
  {
    quote: "*to Yue*  I don't want to be your master. I want to be your friend.",
    anime: 'Cardcaptor Sakura',
    id: 1157,
    name: 'Sakura Kinomoto'
  },
  {
    quote: "The person he loves, I love that person too, and I'm sure that person loves him too. So it's okay that he doesn't love me.",
    anime: 'Cardcaptor Sakura',
    id: 1156,
    name: 'Sakura Kinomoto'
  },
  {
    quote: '*to Kero* Stop eating snacks so mindlessly and think of what we can do!',
    anime: 'Cardcaptor Sakura',
    id: 1153,
    name: 'Sakura Kinomoto'
  },
  {
    quote: '*to Li* In the elevator, when you called me "Sakura", it made me very happy.',    
    anime: 'Cardcaptor Sakura',
    id: 1152,
    name: 'Sakura Kinomoto'
  },
  {
    quote: 'Yue-san is handsome, but Yukito-san is... schweeeet!',
    anime: 'Cardcaptor Sakura',
    id: 1144,
    name: 'Sakura Kinomoto'
  },
  {
    quote: 'Living in a world without the feeling for the person you love most is too harsh!',    anime: 'Cardcaptor Sakura',
    id: 1142,
    name: 'Sakura Kinomoto'
  },
  {
    quote: 'Niichan, you really do work part-time everywhere...',
    anime: 'Cardcaptor Sakura',
    id: 1141,
    name: 'Sakura Kinomoto'
  }
]
```
