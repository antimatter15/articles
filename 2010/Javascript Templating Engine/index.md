---
title: Javascript Templating Engine
author: admin
date: 2010-07-20 8:42:44
categories:
  - Uncategorized
tags: 

template: article.jade
---

Well, there are a bazillion other JS templating engines out there, and it's pretty easy to say why: It's really easy to make. You just take a regex string replace and stick an eval in there and hours of boredom makes something you think is unique despite being one or two bits of (non)functionality away from any other library.

This is, of course, totally un-unique or innovative in any imaginable way. I won't bore you with concepts like "lightest and smallest ever" because it's really not.

    //this might be close .replace(/\{(.*)\}/g,function(a,b){return eval(b)}) `</pre>
    However, I feel compelled to do something utterly non-innovative or useful because everyone loves the NIH (Not Invented Here) syndrome.

    Code is prefixed by the @ symbol, similar to Microsoft's WebMatrix Razor stuff. It's not modeled after Razor, but I just felt like using the @ symbol too. Or that microsoft planted an inception.

    Blocks are like this: @{+new Date}

    Anything can go inside blocks pretty much, and they can be multiline. @{ var now = (new Date).getTime(); var random = Math.random() * Math.pow(10,Math.floor(Math.log(now)/Math.log(10))); var magic = random - now; for(var i = 0; i &lt; magic; i+= 42){ magic -= Math.PI; } magic }

    Take note about how amazingly awesome it is that despite being regexp powered, it can still handle the nested for-loops instead of puking it as a syntax-errored explosive somethingness.

    The last non-whitespace line gets inserted into the html. You can optionally use 'return magic' but that doesn't really do anything more except look more verbose. If you really just want to have code there for some reason, you can end it with '' @{ //do stuff '' }

    Of course this is all boring. You can also do a shorthand notation. @name

    This inserts the value of the variable "name". There are a few rules about the shorthand notation. @name //interpreted as @{name} @name game //interpreted as @{name} game \@name blame //not interpreted at all, outputs as "@name blame" @games_are_fun //interpreted as @{games_are_fun} @name="bob" //interpreted as @{name="bob"} @explosive?'run':'poke' //interpreted as @{explosive?'run':'poke'}

    If you don't want to end it with space, you can also end one with a semicolon;

    Basically, it scans starting from an @ sign (unless the character immediately before is a \ which causes it to remove the \ and not parse the @). It includes everything until it encounters a whitespace character.

    However, like any rule, there are exceptions.
    <pre>`@format_time(date + 2 - 5/64) //interpreted as @{format_time(date + 2 - 5/64)} @blah(234 + 2) + 45 //interpreted as @{blah(234 + 2)} + 42 @blah(234 + 2)+45 //interpreted as @{blah(234 + 2)}+42 @blah(234+2)+45 //interpreted as @{blah(234+2)}+42 `</pre>
    Note that the last three examples demonstrate a sort of unexpected behavior. The function call pattern takes precedence over the include-until-whitespace behavior, because I dont really feel bothered by it and don't feel like fixing it.

    And if you don't feel like doing JS stuff, you can also do some neat things like ifs and loops
    <pre>`@explosive? OH NOES! &lt;strong&gt;RUUUNNN&lt;/strong&gt; @else Well, i guess it's safe. &lt;em&gt;let's poke it!&lt;/em&gt; @/ @if(boom) No comment. @end `</pre>
    Here you can see that there are two ways to start an if. You can postfix it with a ? or you can start it with if(condition). This probably won't ever be useful, but the latest if value gets saved to the @_ifval value.

    There are also two ways of ending a block. You can @end or @/. Both are the same, but one's shorter.

    What about looping arrays and objects? It can do that too.
    <pre>`@each(numbers, number) @number is a magical number, presumably a real number. @/ @each(pets, name, index) Aww, look at how cute @name is! He is my @index+1;'th pet @/ @each(new Array(50)) SPAM @end @each(users, password, username) The password of @username is @password @/ `</pre>
    Note that the loop terminators are the same as the if terminators. Neat isn't it.

    So now that I've demonstrated there's nothing interesting about this solution, go on and leave this document before I explain to you something that's utterly useless and that you shouldn't use.

    Probably the most distinguishing feature is something I call blocks. That's probably a really really bad name and it probably will get people confused with other things, but as the name of this library is "templating" I can't imagine anyone who didn't find this expected. I haven't even hung around the guys who make Prototype or Closure.

    So. Blocks. They're an okay-ish feature that allows for event-based updates of certain sections of the template after the initial rendering. It's a feature that doesn't even belong as part of the templating engine, so it sort of isn't. It's part of the execute() function, which doesn't really count as the templating engine. That's the function which takes your variables and code sticks it through templating, and evals() the result. It also handles blocks.
    <pre>`@time.span{{{ //har har har i love puns It is now @format_time(+new Date) }}} @{ setInterval(function(){time()},1000) '' } `</pre>
    Here we see a block being created, and a piece of attached js which updates the block every second. But blocks can also have triggers that aren't just timeouts and other boring stuff.
    <pre>`&lt;a href="#update_time" onclick="@{{{ time(); }}};return false"&gt;Update the time&lt;/a&gt; 

The way blocks work are pretty simple. It basically creates a function out of the compiled template and then it associates it with a function in the scope of the template. It wraps a

or (based on whether the block name ends with .span or .div or .bacon) and gives it an ID of a random number. This random number is stored in the scope of the template.

When the associated update function is called, it looks up the associated ID number and tries to do a document.getElementById and re-executes the template in the previous scope and then replaces the innerHTML. Basically enabling live templates.

Its all 3KB before gzip (minified). Not that bad, but still, compared to fifty four bytes in the code from the introduction, it's huuge.

Possible changes:

*   name.el_id.interval{{{ }}} block notation for auto updating chronologically. Probably useful for the twitter/facebook style real-time relative dates.
