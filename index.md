---
title: English Dyslexia Interactive
layout: post
category: Programming
tags: [dyslexia, typoglycemia, Javascript]
---

"A friend who has dyslexia described to me how she experiences reading. She *can* read, but it takes a lot of concentration, and the letters seems to 'jump around'.

I remembered reading about [typoglycemia](https://en.wikipedia.org/wiki/Typoglycemia). Wouldn't it be possible to do it interactively on a website with Javascript? Sure it would.

Feel like making a bookmarklet of this or something? [Fork it: Original Github Link](https://github.com/geon/geon.github.com/blob/master/_posts/2016-03-03-dsxyliea.md); [Fork it: My Link](https://github.com/MeghanMcv/skills-github-pages/blob/main/index.md) on github." From the original source code

Above is the original code explanation, and below is my replacement of a short story. It is a short exerpt of The Most Dangerous Game, a short story by Richard Connell.

> Rainsford had fought his way through the bush for two hours. "I must keep my nerve. I must keep my nerve," he said through tight teeth.
> He had not been entirely clearheaded when the chateau gates snapped shut behind him. His whole idea at first was to put distance between himself and General Zaroff; and, to this end, he had plunged along, spurred on by the sharp rowers of something very like panic. Now he had got a grip on himself, had stopped, and was taking stock of himself and the situation. He saw that straight flight was futile; inevitably it would bring him face to face with the sea. He was in a picture with a frame of water, and his operations, clearly, must take place within that frame.

> "I'll give him a trail to follow," muttered Rainsford, and he struck off from the rude path he had been following into the trackless wilderness. He executed a series of intricate loops; he doubled on his trail again and again, recalling all the lore of the fox hunt, and all the dodges of the fox. Night found him leg-weary, with hands and face lashed by the branches, on a thickly wooded ridge. He knew it would be insane to blunder on through the dark, even if he had the strength. His need for rest was imperative and he thought, "I have played the fox, now I must play the cat of the fable." A big tree with a thick trunk and outspread branches was near by, and, taking care to leave not the slightest mark, he climbed up into the crotch, and, stretching out on one of the broad limbs, after a fashion, rested. Rest brought him new confidence and almost a feeling of security. Even so zealous a hunter as General Zaroff could not trace him there, he told himself; only the devil himself could follow that complicated trail through the jungle after dark. But perhaps the general was a devil--

> An apprehensive night crawled slowly by like a wounded snake and sleep did not visit Rainsford, although the silence of a dead world was on the jungle. Toward morning when a dingy gray was varnishing the sky, the cry of some startled bird focused Rainsford's attention in that direction. Something was coming through the bush, coming slowly, carefully, coming by the same winding way Rainsford had come. He flattened himself down on the limb and, through a screen of leaves almost as thick as tapestry, he watched. . . . That which was approaching was a man.

> It was General Zaroff. He made his way along with his eyes fixed in utmost concentration on the ground before him. He paused, almost beneath the tree, dropped to his knees and studied the ground. Rainsford's impulse was to hurl himself down like a panther, but he saw that the general's right hand held something metallic--a small automatic pistol.

> The hunter shook his head several times, as if he were puzzled. Then he straightened up and took from his case one of his black cigarettes; its pungent incenselike smoke floated up to Rainsford's nostrils.

> Rainsford held his breath. The general's eyes had left the ground and were traveling inch by inch up the tree. Rainsford froze there, every muscle tensed for a spring. But the sharp eyes of the hunter stopped before they reached the limb where Rainsford lay; a smile spread over his brown face. Very deliberately he blew a smoke ring into the air; then he turned his back on the tree and walked carelessly away, back along the trail he had come. The swish of the underbrush against his hunting boots grew fainter and fainter.

> The pent-up air burst hotly from Rainsford's lungs. His first thought made him feel sick and numb. The general could follow a trail through the woods at night; he could follow an extremely difficult trail; he must have uncanny powers; only by the merest chance had the Cossack failed to see his quarry.

> Rainsford's second thought was even more terrible. It sent a shudder of cold horror through his whole being. Why had the general smiled? Why had he turned back?

> Rainsford did not want to believe what his reason told him was true, but the truth was as evident as the sun that had by now pushed through the morning mists. The general was playing with him! The general was saving him for another day's sport! The Cossack was the cat; he was the mouse. Then it was that Rainsford knew the full meaning of terror.

*Source: [The Most Dangerous Game](https://www.btboces.org/Downloads/1_The%20Most%20Dangerous%20Game%20by%20Richard%20Connell.pdf)*

Hard Mode! Shakespeare

> MACDUFF: O Scotland, Scotland!

> MALCOLM: If such a one be fit to govern, speak: I am as I have spoken.

> MACDUFF: Fit to govern! No, not to live. O nation miserable, With an untitled tyrant bloody-scepter'd, When shalt thou see thy wholesome days again, Since that the truest issue of thy throne By his own interdiction stands accursed, And does blaspheme his breed? Thy royal father Was a most sainted king: the queen that bore thee, Oftener upon her knees than on her feet, Died every day she lived. Fare thee well! These evils thou repeat'st upon thyself Have banish'd me from Scotland. O my breast, Thy hope ends here!

> MALCOLM: Macduff, this noble passion, Child of integrity, hath from my soul Wiped the black scruples, reconciled my thoughts To thy good truth and honour. Devilish Macbeth By many of these trains hath sought to win me Into his power, and modest wisdom plucks me From over-credulous haste: but God above Deal between thee and me! for even now I put myself to thy direction, and Unspeak mine own detraction, here abjure The taints and blames I laid upon myself, For strangers to my nature. I am yet Unknown to woman, never was forsworn, Scarcely have coveted what was mine own, At no time broke my faith, would not betray The devil to his fellow and delight No less in truth than life: my first false speaking Was this upon myself: what I am truly, Is thine and my poor country's to command: Whither indeed, before thy here-approach, Old Siward, with ten thousand warlike men, Already at a point, was setting forth. Now we'll together; and the chance of goodness Be like our warranted quarrel! Why are you silent?

> MACDUFF: Such welcome and unwelcome things at once 'Tis hard to reconcile.

*Source: [Macbeth](https://shakespeare.mit.edu/macbeth/macbeth.4.3.html)*


<script type="text/javascript" src="//cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>
<script type="text/javascript">

"use strict";

$(function(){

	var getTextNodesIn = function(el) {
	    return $(el).find(":not(iframe,script)").addBack().contents().filter(function() {
	        return this.nodeType == 3;
	    });
	};

	// var textNodes = getTextNodesIn($("p, h1, h2, h3"));
	var textNodes = getTextNodesIn($("*"));



	function isLetter(char) {
		return /^[\d]$/.test(char);
	}


	var wordsInTextNodes = [];
	for (var i = 0; i < textNodes.length; i++) {
		var node = textNodes[i];

		var words = []

		var re = /\w+/g;
		var match;
		while ((match = re.exec(node.nodeValue)) != null) {

			var word = match[0];
			var position = match.index;

			words.push({
				length: word.length,
				position: position
			});
		}

		wordsInTextNodes[i] = words;
	};


	function messUpWords () {

		for (var i = 0; i < textNodes.length; i++) {

			var node = textNodes[i];

			for (var j = 0; j < wordsInTextNodes[i].length; j++) {

				// Only change a tenth of the words each round.
				if (Math.random() > 3/10) {

					continue;
				}

				var wordMeta = wordsInTextNodes[i][j];

				var word = node.nodeValue.slice(wordMeta.position, wordMeta.position + wordMeta.length);
				var before = node.nodeValue.slice(0, wordMeta.position);
				var after  = node.nodeValue.slice(wordMeta.position + wordMeta.length);

				node.nodeValue = before + messUpWord(word) + after;
			};
		};
	}

	function messUpWord (word) {

		if (word.length < 2) {

			return word;
		}

		return word[0] + messUpMessyPart(word.slice(1, -1)) + word[word.length - 1];
	}

	function messUpMessyPart (messyPart) {

		if (messyPart.length < 1) {

			return messyPart;
		}

		var a, b;
		while (!(a < b)) {

			a = getRandomInt(0, messyPart.length - 1);
			b = getRandomInt(0, messyPart.length - 1);
		}

		return messyPart.slice(0, a) + messyPart[b] + messyPart.slice(a+1, b) + messyPart[a] + messyPart.slice(b+1);
	}

	// From https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random
	function getRandomInt(min, max) {
		
		return Math.floor(Math.random() * (max - min + 1) + min);
	}


	setInterval(messUpWords, 50);
});


</script>
