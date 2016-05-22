CSS Playing Cards
=================

CSS Playing Cards help you to create simple and semantic playing cards in (X)HTML.

* @author   Anika Henke <anika@selfthinker.org>
* @license  CC BY-SA [http://creativecommons.org/licenses/by-sa/3.0]
* @version  2011-06-14
* @link     http://selfthinker.github.com/CSS-Playing-Cards/

Contents
--------

* **cards.css** is the main part and provides the styles for the cards
* **examples.html** provides some example HTML
* **README.md** is this file
* **faces/** contains images for the faces

How to use it
-------------

### Surrounding container

    <cards class="[fourColours|faceImages|simpleCards|inText|rotateHand]">
        ...
    </cards>

There needs to be a surrounding container with the class "playingCards" around all the cards. That container can also have other classes which serve as **configuration options**:

* **fourColours**: Switches the default two colour deck with a four colour deck. (The colours of the German four colour deck will be different.)
* **faceImages**: Switches the default dingbat symbols for faces with images. *Note: Depending on the size of the card, you might need to adjust the image positioning of the faces in cards.css.*
* **simpleCards**: Switches the default multiple suits to one simple single big suit in the middle.
* **inText**: Switches the size to something small enough to fit into normal text and also removes the inner bits.
* **rotateHand**: Switches the hand to rotate and fan in a semi circle.

### The back of a card

    <card class="back">*</card>

To make the cards smaller or bigger, just change the font-size in the main "card" class in cards.css (search for "@change").

### The front of a card

    <card class="rank-[2|3|4|5|6|7|8|9|10|j|q|k|a] [diams|hearts|spades|clubs]">
        <rank>[2|3|4|5|6|7|8|9|10|J|Q|K|A]</rank>
        <suit>&[diams|hearts|spades|clubs];</suit>
    </card>

Depending on the context, the main card element should either be an **a** (for selecting single cards), or a **label** (for selecting multiple cards), e.g.

    <[a|label] class="card rank-a clubs" [href=""] [title=""]>
        <rank>A</rank>
        <suit>&clubs;</suit>
        [<input type="checkbox" [...] />] <!-- if in label -->
    </[a|label]>

### A joker

    <card class="joker [big|little]">
        <rank>[+|-]</rank>
        <suit>Joker</suit>
    </card>

### Different hands

    <ul class="[table|hand|deck]">
        <li>
            [<strong>] <!-- if selected -->
                ... card ...
            [</strong>]
        </li>
        ...
    </ul>

* **table** places the whole cards side by side.
* **hand** places them side by side, but lets them overlap, so you will only see a part of each card. If the "rotateHand" option is enabled, you'll see the cards rotated in a semi circle.
* **deck** places the cards on top of each other, so that you cannot see single cards but a pack.

Requirements
------------

The CSS is only intended to work in **modern browsers** (Firefox 3.6+, Opera 10+, Chrome, Safari).  
(Edit: I wouldn't call Firefox 3.6+ modern anymore, but oh well...)

Credits
-------

* The faces' images are taken from [svg-cards](http://svg-cards.sourceforge.net/)
* One of the cards back images was taken from http://www.squidfingers.com/patterns/
