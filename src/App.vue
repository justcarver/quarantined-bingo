<template>
  <div id="app">
    <BingoCard :items="cardData" />
    <Rules />
  </div>
</template>

<script>
import BingoCard from "./components/BingoCard.vue";
import Rules from "./components/Rules.vue";

const potentialSquares = [
  `Someone yells at family member or roommate who isn't playing`,
  `Someone tells a dick joke`,
  `Someone is being extra negative about themselves`,
  `Someone goes to the restroom right as about to pull`,
  `Someone mentions missing their Battle Shout`,
  `Burping in Discord`,
  `Inappropriate body part discussions during non farm content`,
  `Someone puts themselves down`,
  `A non-tank offers to tank`,
  `A non-heal offers to heal`,
  `Random people trying to Raid Lead`,
  `Down new boss in 3 or less tries`,
  `Someone reminisces about old raids/groups`,
  `Someone shouts "C'mon guys, we got this!" or similar`,
  `Someone grumbles about closets or cookies`,
  `Someone shouts "Don't jinx us!"`,
  `Ready Check to Ready Check`,
  `We have no feasts`,
  `Wipe at less that 5%`,
  `B-Rez used on someone who immediate dies again`,
  `Face Pull`,
  `Transmog Emergency!`,
  `Someone posts link instead of whisper lewt person`,
  `Something about nipples`,
  `Pet pictures in discord`,
  `Someone was muted and didn't realize it`,
  `Debate on who drops a cauldron`,
  `"Does anyone have an extra flask?"`,
  `Someone face/ass pulls a boss`,
  `"That's what she said!"`,
  `Someone demands silence in voice chat`,
  `Slurred Words in chat`,
  `Too Lazy to Release`,
  `"I'm/They're a Pod"`,
  `Stop healing!`,
  `Confusion over Battle Rezes`,
  `A comparison is made to Infernals' raids`,
  `Someone demands their slut mog be inspected/judged`,
  `Someone starts singing`,
  `Multiple Feasts are dropped at the same time`,
  `"This is fine!"`,
  `"Come on <insert tank>, only <insert damage> left!!!"`,
  `Keyboard Sounds in voice chat`,
  `Someone starts reexplaining a fight after first explanation`,
  `Dog/Baby Shenanigans`,
  `Someone saying gib tier`,
  `"I wasn't standing in that!"`,
  `"Can't stop won't stop"`,
  `Someone releases after someone says "Don't Release!"`,
  `Can't trade loot after roll due to iLevel`,
  `Someone forgot to re-flask`,
  `Roll of 100 or 1`,
  `One of every class is present`,
  `4 or more of a single class is present`,
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

<style></style>
