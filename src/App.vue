<template>
  <div id="app">
    <BingoCard :items="cardData"/>
    <Rules />
  </div>
</template>

<script>
import BingoCard from './components/BingoCard.vue';
import Rules from './components/Rules.vue';

const potentialSquares = [
  `Someone yells "Nick!"`,
  `VooDoo is unsure if he'll be in raid`,
  `Someone tells a dick joke`,
  `Someone is being extra negative about themselves`,
  `Someone goes to the restroom right as about to pull`,
  `Moo mentions missing her Battle Shout`,
  `Burping in Discord`,
  `Inappropriate body part discussions during non farm content`,
  `Moo puts herself down`,
  `A non-tank offers to tank`,
  `A non-heal offers to heal`,
  `Random people trying to Raid Lead`,
  `"Dammit Wiki"`,
  `"Dammit Pokez"`,
  `Wiki talks in discord (while not tanking)`,
  `Down new boss in 3 or less tries`,
  `Someone reminisces about old raids/groups`,
  `Someone shouts "C'mon guys, we got this!" or similar`,
  `Aera grumbles about closets or cookies`,
  `Someone shouts "Don't jinx us!"`,
  `Someone asks for "Noods"`,
  `Someone yells about missing a pre-pot`,
  `Ready Check to Ready Check`,
  `We have no feasts`,
  `Dik Diks!`,
  `Wipe at lest that 5%`,
  `B-Rez used on someone who immediate dies again`,
  `Face Pull`,
  `Transmog Emergency!`,
  `Someone posts link instead of whisper lewt person`,
  `Something about nipples`,
  `Pet pictures in discord`,
  `Body Massage`,
  `Someone was muted and didn't realize it`,
  `Debate on who drops a cauldron`,
  `"Does someone have an extra flask?"`,
  `Someone face/ass pulls a boss`,
  `"That's what she said!"`,
  `Someone has forgotten seals after a boss has been killed`,
  `Someone demands silence in voice chat`,
  `Slurred Words in chat`,
  `Too Lazy to Release`,
];

function randomCard() {
  const tempArray = [];
  const optionsArray = potentialSquares;
  for (let i = 0; i < 24; i += 1) {
    const item = optionsArray.splice(Math.floor(Math.random() * optionsArray.length), 1);
    tempArray.push(item[0]);
  }
  tempArray.splice(12, 0, `FREE!`);
  tempArray.unshift(`B`, `I`, `N`, `G`, `O`);
  return tempArray;
}

export default {
  name: `app`,
  components: {
    BingoCard,
    Rules,
  },
  data: function () {
    return {
      cardData: randomCard(),
    };
  },
};
</script>

<style>
</style>
