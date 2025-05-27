---
title: English Dyslexia Interactive
layout: post
category: Programming
tags: [dyslexia, typoglycemia, Javascript]
---

"A friend who has dyslexia described to me how she experiences reading. She *can* read, but it takes a lot of concentration, and the letters seems to "jump around".

I remembered reading about [typoglycemia](https://en.wikipedia.org/wiki/Typoglycemia). Wouldn't it be possible to do it interactively on a website with Javascript? Sure it would.

Feel like making a bookmarklet of this or something? [Fork it](https://github.com/geon/geon.github.com/blob/master/_posts/2016-03-03-dsxyliea.md) on github." From the original source code

Above is the original code explanation, and below is my replacement of a short story. It is a short exerpt of The Most Dangerous Game, a short story by Richard Connell.

> "I wanted the ideal animal to hunt," explained the general. "So I said,
`What are the attributes of an ideal quarry?' And the answer was, of
course, `It must have courage, cunning, and, above all, it must be able
to reason."'

>"But no animal can reason," objected Rainsford.

> "My dear fellow," said the general, "there is one that can."

> "But you can't mean--" gasped Rainsford
> "And why not?"

> "I can't believe you are serious, General Zaroff. This is a grisly joke."

> "Why should I not be serious? I am speaking of hunting."

> "Hunting? Great Guns, General Zaroff, what you speak of is murder."

> The general laughed with entire good nature. He regarded Rainsford quizzically. "I refuse to believe that so modern and civilized a young man as you seem to be harbors romantic ideas about the value of human life. Surely your experiences in the war--"

> "Did not make me condone cold-blooded murder," finished Rainsford stiffly.

> Laughter shook the general. "How extraordinarily droll you are!" he said. "One does not expect nowadays to find a young man of the educated class, even in America, with such a naive, and, if I may say so, mid-Victorian point of view. It's like finding a snuffbox in a limousine. Ah, well, doubtless you had Puritan ancestors. So many Americans appear to have had. I'll wager you'll forget your notions when you go hunting with me. You've a genuine new thrill in store for you, Mr. Rainsford."
> 
*Source: [https://www.btboces.org/Downloads/1_The%20Most%20Dangerous%20Game%20by%20Richard%20Connell.pdf)*




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
				if (Math.random() > 1/10) {

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

		if (word.length < 3) {

			return word;
		}

		return word[0] + messUpMessyPart(word.slice(1, -1)) + word[word.length - 1];
	}

	function messUpMessyPart (messyPart) {

		if (messyPart.length < 2) {

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
