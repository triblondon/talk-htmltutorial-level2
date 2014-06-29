# HTML Workshop

Here is an article we published recently on ft.com.  You can see this, and half a million subscribers can read it, thanks to the world wide web.  In fact, we now have more digital subscribers than we sell papers, so of all the people that see the content, most are seeing it using the web.

Let's dig a bit deeper.  Right click inspect element.  Now we're looking at the source code of the page, HTML.  As I move my mouse over each part of the code, the browser highlights the bit of the page that corresponds to that bit of code.  I can edit stuff, delete this paragraph, maybe insert a word here, or make this word bold.

[Describe the payoff - show some inspector stuff]

If you've ever wondered why does my content look like this on the web, or can I do something more interesting, like inserting a video or how can I make it look good on mobile, understanding the basics of HTML will help you.

The most important thing about HTML is that it has nothing to do with how your content looks.  It's all about what it means.

For example, let's take an FT headline

	<h1>EU exit will block UK bank trade, top Brussels official says</h1>

What was needed was a standard way of linking one document to another.  And that meant we needed a way of uniquely identifying a document that didn't require a central authority (because who would that be?), but which was guaranteed not to clash with anyone else's document.  Once we had that, we needed a way of embedding those links into the documents, and making sure that everyone could view the documents reliably.

The thing that solved these problems was the world wide web. Incidentally, the world wide web is not the Internet, it's just one use of the internet.  It's not even the biggest use of the internet.  What is?  Email.

So, how does the web solve our problem of making documents accessible?  There are two very important technologies to understand: URLs, and HTML.  First, we have URLs.  These act as globally unique identifiers, like postal addresses.  Everything on the world wide web has one, whether it's a document, an image, video, zip file, PDF, whatever.  We'll never run out of URLs, so we can give one to anything we want.  Once something has a URL, anyone else can reference it.

It's here that HTML comes in.

Tim looked around for something that would allow him to describe the content of a document, and he found XML, or Extensible Markup Language.  XML is a set of useful rules allowing you to describe, classify and structure things.  For example, we might have some text, like this, and some of it is nonsense.  We can identify the nonsense by using XML like this:

	The sky <nonsense>raining</nonsense> is blue today

This is an ELEMENT, created by placing CONTENT between an opening TAG and a closing TAG.  You create an opening tag simply by putting its name between angle brackets.  The closing tag is exactly the same, except you prefix the tag name with a slash.

XML also allows elements that don't have an end tag, because they have no text content.  For example, Obama is famous for adding long dramatic pauses into his speeches.  We can invent an XML tag to document where the pauses should be:

	Forty-four Americans have now taken the presidential oath.  The words have been spoken during rising tides of prosperity<pause /> and the still waters of peace. Yet, every so often<pause /> the oath is taken amidst gathering clouds<pause /> and raging storms. At these moments, America has carried on not simply<pause /> because of the skill or vision of those in high office, but because We<pause /> the People<pause /> have remained faithful to the ideals of our forebears, and true to our founding documents.

Let's look at this creature in a bit more detail.  Because the tag doesn't have a closing tag, we bring the slash into the opening one.  This is called a self-closing tag.

	<pause />

One of the most powerful bits of XML is the ability for the content of one element to contain other elements.  Shakespere would no doubt have taken advantage of that when writing Hamlet, and I've always thought that Shakespere is better when experienced in the original XML, so let's take a look:

	<soliloquy>
		<verse>To be, or not to be:
			<deleted>I there's the point</deleted>
			<inserted>that is the question</inserted>
			:
		</verse>
		<verse>Whether 'tis nobler in the mind to suffer</verse>
		<verse>The slings and arrows of outrageous fortune,</verse>
		<verse>Or to take arms against a sea of troubles,</verse>
		...
	</soliloquy>

There's quite a bit going on here, but if you work through it, you can see the whole text is a soliloquy, and it contains some verses, a piece of text that's been deleted, and a replacement inserted.  The most important thing is that every tag we opened, we also closed, and we closed them in the opposite order we opened them.  That means the markup we wrote is 'well formed'.  You can demonstrate this by laying the markup out with indentation every time you open a tag, so that closing tags line up vertically with opening ones.

This principle of writing well formed markup is very important to ensuring documents don't get confusing as they get more complicated.

So far, all the tags we've used, we just made up.  The beauty of XML is you can do that, make up whatever tags you want.  But that's also a problem, because everyone will use different tags and that makes it very hard to read each other's documents.

Tim Berners Lee took XML, and defined a set of tags as a standard that we could all agree on.  The things he chose to standardise are the basic building blocks of prose.  Here are some of them:

	* Headings (H1, H2, H3, H4, H5, H6)
	* Paragraphs (P)
	* Emphasis (EM, STRONG)
	* Lists (UL, OL)
	* Links (A)
	* Images (IMG)
	* Tables (TABLE)

So, in HTML, if you want to describe two paragraphs, you use the P tag:

	<p>Nay, do not think I flatter; For what advancement may I hope from thee that no revenue hast but thy good spirits, to feed and clothe thee? Why should the poor be flatter'd?</p>
	<p>No, let the candied tongue lick absurd pomp, and crook the pregnant hinges of the knee where thrift may follow fawning.  Dost thou hear?</p>

Let's say Will wanted to emphasise advancement in paragraph 1, and strongly emphaisise candided in paragraph 2:

 	<p>Nay, do not think I flatter; For what <em>advancement</em> may I hope from thee that no revenue hast but thy good spirits, to feed and clothe thee? Why should the poor be flatter'd?</p>
	<p>No, let the <strong>candied</strong> tongue lick absurd pomp, and crook the pregnant hinges of the knee where thrift may follow fawning.  Dost thou hear?</p>

Because we all agree on what P, EM, and STRONG mean, we can also apply some sensible formatting when we display the document, even if the author hasn't told us what it should look like.  In a web browser, the two paragraphs above will, by default, look like this.  The browser has applied vertical spacing between the paragraphs, has made the emphasised text italic, and has made the strong text bold.

So, while XML is like a grammar with no vocabulary, HTML adds a vocabulary.

Now, we're going to do an exercise.  On your computer you have a split screen with an HTML document on the left, and a live interpretation of the document on the right.  When you make changes on the left, they'll be instantly reflected on the right.  If you don't close your tags properly, your code will go red.  As it stands the document is already well described in HTML, and you'll see it makes use of headings, paragraphs, emphasis, and line breaks.  Your job is to add some emphasis and strong emphasis to the prose itself, so read the text to yourself and find some words or phrases that should be emphasised when spoken, then use the right tags to mark up that emphasis.

For this, you're going to need to use two tags:

	<em>
	<strong>

---

OK, so far, we have learned that:

* HTML is a standard set of tags that give meaning to content
* An HTML element consists of an opening tag, some content and a closing tag; or a single self-closing tag
* Any tags we open, we have to close, and they must be closed in the right order
* We can 'nest' elements inside of one another
* Indentation helps us verify that the code is well formed

The ability to nest elements inside one another also enables us to use more complex strcutures, such as lists.  In a list, we need to know where each item starts and ends, but also where the list as a whole starts and ends.  In HTML, we have two kinds of list:

	<ul>  Unordered list
	<ol>  Ordered list

Everything we've done so far has used tags that apply meaning without being prescriptive about the visual style.  For example, em and strong are not called italics and bold, because how you display emphasis is actually much less important than communicating that there is a need for it.  This is something that's very important in HTML, and is called SEMANTICS.  You can see that at work again in the naming of these two types of list.  But you can probably imagine what these lists would look like - what's the difference?  Numbers vs bullets.

If you're writing a list, thinking semantically means not thinking whether you'd like to see numbers or bullets, instead, think about whether the order is important.  What would you use for driving directions?  Ordered list, because the order is important.  How about a shopping list?  Unordered, right, because it doesn't matter in what order you buy the things on the list.

In HTML lists, whether it's an ordered or unordered list, each item is marked with the li, or LIST ITEM, tag.  Here's an example to a TODO list with three items:

	<ul>
		<li>Learn HTML</li>
		<li>Feed the cat</li>
		<li>Pick up dry cleaning</li>
	</ul>

I've decided it doesn't matter what order I do these things in, so it's an unordered list.

Now we're going to do a second exercise.  Switch to the second tab on your browser, and you'll find a shopping list in an HTML document.  I've put the structure of the document in place (because we won't cover that part of HTML today), but the body of the document has no tags, and you can see how the browser is showing it as a big lump of text on the right.  Your job is to put markup in place to give meaning to the text.  You're going to need these tags:

	<h1> Heading
	<h2> Subheading
	<ul> Unordered list
	<li> List item
	<em> Emphasis

---

OK, another quick recap:

* HTML elements are semantic, they convey meaning, not visual style
* Some tags work together to create more complex structures like lists
* As ever, every tag we open, we have to close, and indenting them helps to keep the code WELL FORMED

So far, we've made documents that stand alone, and don't link to anything else.  But the whole point of the web is to link stuff together, so it's time to change that.  In order to make links though, we need to cover one bit of XML that we haven't seen yet: attributes.

Attributes sound like a scary technical term, but you use them all the time.  Here's a dog.  The dog has a number of attributes, for example, it has a breed, in this case labrador, it has a name, shadow, and it has an owner, me.  These are all attributes of Shadow.  They aren't expressed directly in the content, but they are important to add extra meaning to the content.

In XML, attributes are added to the opening tag of an element, and we'll look at how that works for the HTML link tag, which for historical reasons is the letter a, which stands for ANCHOR.  Here's some text that we want to add a link to:

	See the New York Times piece on inflation trends for more information.

First, we can insert tags to create a link element:

	See the <a>New York Times piece on inflation trends</a> for more information.

But whilst that tells us that the content is a link, it doesn't say where the link goes.  For that we add the link's main attribute, the destination URL of the link.  Again for annoying historial reasons that attribute is called href, for hypertext reference.

	See the <a href='http://www.nytimes.com/...'>New York Times piece on inflation trends</a> for more information.

So now we have some content - "New york times piece on inflation trends", which is classified by a tag as a link, and that link is further described by an attribute that tells us where the link goes.

Here's a final exercise.  Go back to your shopping list.  You'll find that I'm quite fussy, and want only some very specific brands of some items.  All those brands have websites, so open a new tab and use Google to find the URL of their homepage, then link to them from the shopping list.  For this exercise you're going to need the following tag and attribute:

	<a>  Link

	href=""  Reference to another URL

---

OK, final recap:

* HTML is a set of standard TAGS that you can use to create ELEMENTS following a set of rules inherited from a generic language structure called XML. It's like a vocabulary to XML's grammar.
* Elements are semantic, they convey meaning without visual style
* You can nest elements inside of one another, but it's important that they are closed in the right order
* Some tags need to be opened and closed, others are 'self-closing'
* Attributes can be used to add further information to elements which is not displayed

Now, you've been coding for most of the workshop so I thought I could do some coding too, to show you what you might be able to learn in level 2.

* Origami demo

And finally, to show you how easy HTML is, I'm going to finish with a video.  I help raise money for a charity called CodeClub, which teaches programming to 9-11 year olds.  Here is their demo of making a webpage.
