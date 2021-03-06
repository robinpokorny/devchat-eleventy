---
layout: layouts/post.njk
title: >
  iPS 169 React Native with Tyler McGinnis
date: 2016-09-08 06:00:43
episode_number: 169
duration: 46:09
audio_url: https://media.devchat.tv/iphreaks/iPS169_React_Native_with_Tyler_McGinnis.mp3
podcast: iphreaks
tags:
  - iphreaks
  - podcast
---

1:28: Tyler McGinnis Introduction

- Sparrow
- [React.js Program](https://www.reactjsprogram.com/)
- [Tyler’s website](https://tylermcginnis.com/)
  2:15 [React Native](https://www.reactnative.com/)
- CodePush
  4:37: Cross Network Frameworks11:20: The Experience of Going From iOS to Android
- [Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
  16:20:[Andy Matuschak Tweet](https://twitter.com/andy_matuschak/status/560511204867575808)17:05: Basic Building Blocks
- Container Components
- Presentational Components
  21:17 Reducers
- Time Travel Debugging
  23:15: Downsides of React Native26:45: Proper Threading
- Animation Issues
  30:58: Route Transitions
- [Reactive Native Vector Images](https://github.com/oblador/react-native-vector-icons)
  36:15: Testing a React Native Application40:12: Facebook’s Goals with App Development

### Picks

[_Cannery Row_](https://en.wikipedia.org/wiki/Cannery_Row_) by John Steinbeck (Jaim)[No Man’s Sky](https://www.no-mans-sky.com) (Layne)Remember the Titans (Charles)[Dan Abramov - Live React: Hot Reloading with Time Travel](https://www.youtube.com/watch?v=xsSnOQynTHs) (Tyler)[React.js](https://www.reactjsprogram.com/) (Tyler)

### Links:

[Tyler on JavaScript Jabber](https://devchat.tv/js-jabber/151-jsj-getting-started-with-a-career-in-web-development-with-tyler-mcginnis)[Redux and React With Dan Abramov](https://devchat.tv/js-jabber/179-jsj-redux-and-react-with-dan-abramov)[JavaScript Core With Cesare Rocchi](https://devchat.tv/iphreaks/128-ips-javascriptcore-with-cesare-rocchi)

### Transcript

Charles: Hey everybody and welcome to Episode 169 of the iPhreaks Show. Today on our panel we have Jaim Zuber,

Jaim: Hello! From Minneapolis.

Charles: Layne Moseley.

Layne: Hello, from Utah.

Charles: And Charles Max Wood from devchat.tv. Since we’re talking about React Native, I’m just going to shout out real quick. I am putting on a React Remote Conference in October so go check that out at reactremoteconf.com. We have a special guest this week and that is Tyler McGinnis.

Tyler: What’s up, every one?

Charles: You want to give us a brief introduction to who you are?

Tyler: For sure. Tyler, I currently am the CTO of a company called Spero where we are building a few apps to basically help people who are affected by cancer. I do that, that’s kind of my full time job. After hours I guess you can say I run reactjsprogram.com which is basically a linear approach to learning the React ecosystem. Then, I also run React Newsletter and then do a bunch of community stuff as well so I’m kind of all over the place.

Charles: Very cool. Are you friends with some of the other Utah folks that are way into React like Ryan Florence?

Tyler: I am friends with all of them. Ryan, he’s up in Seattle now. Eric Christian is my good friend, Max Brodsky, kind of all those guys

Charles: Very cool. You’re going to be at React for Ally here in a few weeks?

Tyler: I’m planning. All set for it.

Charles: I still need to get a ticket. We brought you on today to talk about React Native and Fire Base. I think people, especially on the show, have a general idea about what React Native is but you want to of give us a thumbnails sketch for those that aren’t familiar?

Tyler: Definitely. Basically what React Native allows you to do is it allows you to take, if you’re a web developer, if you’re specifically familiar with JavaScript and even more specifically React, it allows you to take your knowledge of those technologies and then build Native iOS or Android, I guess Native iPhone applications.

Charles: Awesome. And it runs through JavaScript core. It’s pretty much a Native app. It just doesn’t really objective see run time

Tyler: Exactly. I’m not super familiar with the actual implementation details. But the whole idea for React is that, if I were to give React Native in a nutshell how it works, the whole idea of React is that, the selling point is you’re basically able to create a declarative UI for your interfaces which is really nice. Part of that is the React has this different algorithm which basically says whenever you change state in your application,React is going to say okay, it looks like the previous virtual DOM they call it, looks like this and the new one looks like this,. Let’s find minimal representation of changes between the two DIFS and then we’ll go ahead and update the DOM with those changes. But the in the React Native sense, there is no DOM. The idea is that it’s still taking that different approach but instead of updating the DOM, it’s updating UI Kit for Android view or something more Native.

It’s really interesting and really awesome piece of technology that continues to grow and continues to gain popularity which is great.

Charles: I am much more familiar with the React Native things. I’ve talked with several people. I felt Nader Davit put together the React Native radio podcast. I understand some of this, I’m really curious to see what Layne and Jaim want to know about React Native or what question they have. They’re coming from a different place than I am.

Jaim: I also think it’s such thing to point out where I’m at. I know nothing about actual Objective-C, Swift, ex-code ecosystem. Everything that they know, so it will be interesting that we have a discussion like me being super naïve to everything like real Native and then being arguably naïve to the web.

Layne: I have lots of experience with cross platform frameworks and so I’m also quite excited to talk about this. A lot of opinions about that, good and bad.

Charles: What have you placed your plane?

Layne: I started with iOS 2 back in 2008. The first thing I did was I wrote an app with a cross platform in a framework called Quick Connect which actually was one of the first, if not like a B first in fact, as far as I understand phone gap which is pretty popular these days was kind of base around how Quick Connect did its cross platform thing.

I’ve always been really cautious of them because most of them were based on web technologies. Performance is usually pretty poor, you don’t get a lot of the Native scrolling and all the nice and easy you get with the Native app. React Native is so interesting to me because it actually translates everything into UI Kit. I’m pretty excited about it myself

Tyler: Have you have the chance to play around with it at all yet?

Layne: I did. When did it come out? It was two years ago. It’s been a while. I did immediately when I came out and I thought this is going to be great. I didn’t think it was great then but two years later, from everything that I am hearing, they’ve made some really great product persona. I haven’t picked it up recently, I would love to but I haven’t done it recently but I’m excited for the future of this type of an approach.

React is amazing, I’ve never written a React app, I can’t say this is why it’s so great. As far as I understand, the architecture of how React works is perfect for this kind of thing where it’s able to push everything in the view layer off to whatever view system possible. That’s just like the coolest technology.

Jaim: As Layne mentioned, the previous cross platform technologies, most of them ran on some kind of JavaScript page development, performance was awful. This presents a new paradigm where doing actual Native components that aren’t standard, UI Kit components. But most of our listeners are Native iOS developers, our world controllers, UI buttons that type of thing. What are the basic building blocks for building a React Native app?

Tyler: That’s a really good question. What’s interesting about React Native specifically if you’re coming from a React background, you can get up and running fairly quickly. The idea like on the web we have DIVS and SPANS and all of those developments.

With React Native, instead of using DIVS and SPANS, you use view text. My understanding of that is that just like call some Native, basically Native implementation for view and the Native implementation for text. If I were to recommend someone who has no experience with the web but they wanted to check React Native, what’s really nice about React is a lot of it is just JavaScript, and I know lot of you Native guys don’t are going to really want to hear that or love JavaScript language. Well, that’s fine.

What’s nice about it is you can get upper grounding very quickly. I think what’s so cool about React Native isn’t—I mean the idea that uses the React and all the benefits of React is really cool but what’s nice about it is well as you get all of these cool developer experiences. You have like a hot matcher replacement now so basically if you have some state in your application, you can go ahead and change some style or change some logic. The state of your application isn’t going to get thrown away when you hit refresh, it’s just going to stay there. Instead of navigating back to the same view you’re on, it just stays there, it has live reload which is really nice.

There’s some cool companies, there’s this thing called Code Push which basically allows you to push out updates to your app without having to go to the app store which is really nice.

Even besides all of the benefits of using React and using JavaScript where you’re coming from the web, that’s really nice. There’s a lot of really great experiences as a developer as well.

Layne: You know that hard reloading to me, especially with the app I’m currently working on is so enticing because I compile my app how many hundreds of times a day probably and it takes a good two minutes to get on the device. You stack that over your development, hours and hours and hours of time. That’s super interesting.

Tyler: I think why React Native is so popular is because as a web developer, you’re not really making sacrifices to develop on a Native I guess. If you’re coming from web, you’re used to hot module replacement, you’re used to live reload and all of those really nice experiences. Obviously, there’s a bunch more benefits you get when you go Native but you’re at least not having to sacrifice those experiences that you’re used to in order to go Native which I think is really enticing.

Charles: I’m going to push back though a little bit on the sacrifices you make to go Native or not to go Native. The way that I understand JavaScript Core works is that, sure it’s JavaScript process running out in JavaScript virtual machine, but my understanding is that the performance and other aspects of JavaScript Core are comparable to Swift and Objective-C once you build and compile them.

The other end of it is that all of your components or all of your views in React Native or Native Script to otherwise JavaScript core application are Native. These changes are being made by calling into another process that’s running as Swift or Objective-C run time application and then that’s what’s going in and updating the views. It is very comparable in performance and behavior to the Objective-C or Swift setup.

I think the places where you fall down a little bit are the places where if you’re building across platform app, you have to do something different on Android than you do on iOS so you wind up branching your code or building something into your build process so you can handle those things. For all the things I have in common such as menus and tables and the way that it handle views and lists and all that stuff, it’s pretty comparable across the board.

Tyler: This is actually interesting, let’s dive into this a little bit. For the last year, my background as I mentioned, I’ve been building a React Native iOS app pretty more primarily. I was coming on the&nbsp; show and I do haven’t at that point which was Monday, I haven’t really dove into React Native for Android yet. I really wanted to do that because I want to come on here and be able to speak to both platforms.

Monday morning I took out the app that I’ve been working on for about a year and built an Android version of it in a day. It probably needs about three to four hours of work in order to be ready to go to production. It was amazing because as you mentioned Chuck, the experience from going from iOS to Android was as smooth as I would’ve ever hoped for.

Essentially, all I did was obviously like they’re two different platforms, they have different styles. What I did was with our iOS app we have just a normal footer that switches views. With Android, instead of having a normal footer, we put our navigation in like a drawer, like a slide out drawer. Basically, all of our underlining logic code is still the exact same and even most of our style code is the exact same. When you switch platforms, the fonts get switched out and all those Native things get switched out. Just the way we navigate and the app is different.

From building an iOS app for about a year and then building one that’s very comparable in Android took about a day which is incredible.

Layne: We talked to Throw and he had an exact similar experience. He had worked on the iOS version for months and then in two days he was like “Oh! Cool! Android app! Way to go.”

Tyler: Basically, the way it works is, he might have explained this, I’ll just explain it really quickly. If you have a footer.js file, what you basically do if you want that specific iOS, you just change it to footer.iOS.js. And then when you’re on a iPhone, React Native us smart enough to just ignore the footer.js file under the footer.iOS.js file. Same thing for Android.

Essentially what I did was I just swapped out the files for navigation and changed them with the .iOS with the Android extension and then put the platforms specific code in there and then it worked which was amazing.

Layne: That sounds amazing.

React Native is open sourced so I looked at some of the source code. When I looked a couple of years ago, it looked to me like it’s using UI Kit but it’s basically just using views and they had to reengineer most of rendering lists, navigation, and all that kind of stuff.

I’m assuming that’s still the case cause that’s the person they had before. That to me worried me just a little bit because now we have layers upon layers upon layers and it just seems like a big maintenance task. Does that make sense what I’m saying?

Tyler: Yes. I’ve actually never looked at the code. All of that. I’m like a pure web developer, I'm scared of all things Java and Objective-C. I haven’t dove into the source code too much. For what I know, I know they build their own flex box implementation or they did at the time a year and a half, two years ago. But as far as the underlining primitives of what’s going on…

Layne: For people who don’t really know web like me. What is flex box?

Tyler: Flex box, you can think of it as CSS2.0, or basically it just gives you kind of more power over styling and application. Basically, the one line take away for flex box is with just like regular CSS, you’re talking about that like they’re different but they’re the same thing.

With the old way of styling, you basically have classes and IDs and then you just pick an element and that element styles itself. With flex box, you kind of inverse that so instead of the child element styling themselves, you just have the parent be able to have more control over the children element.

On web, it’s sourced really well, even on Native it probably works even better because you’re able to basically create these nice fluid layouts without having a bunch of one off styles like you’re kind of used to with CSS if you’ve done CSS before.

Layne: Flex box can replace UI appearance, I'm okay with it.

Jaim: Anything that can replace your eye appearance is probably a good thing. Tyler has no idea what we’re talking about UI.

Tyler: I have no idea. I trust that the if you say it is to be replaced, I’m all for it.

Jaim: Eventually, it’s how you style your app, how your buttons look, you’ve got the smaller something of a button, you can do that one thing, it’s a logical way of doing your layouts, fonts, colors, that type of thing.

Layne: It’s a lot different than the web because with UI Kit, we have so many things at our disposal just automatically. Buttons and navigation bars and tools bars and all this stuff. Having UI parents is a way to style these elements that we don’t have direct control over. Does that make sense?

Tyler: I don’t know him personally. I don’t even know how to pronounce his last name, Andy Matichak, he’s at Con Academy right now I think.

Layne: Yeah, I’m familiar with him.

Tyler: I think he did some UI Kits stuff. I’m looking for a specific tweet, here’s the tweet.

Layne: I know this tweet.

Tyler: It’s a popular one. I loved it because I’m a web guy. He twitted, “I say with confidence he’s a former UI Kit author, Reacts model for the UI leaders fast better than UI Kits, React natives is a huge steal.” That was a few years ago.

Layne: And that’s the moment when I also was like oh man, React Native is probably going to be a big thing when he said that.

Tyler: Yeah for sure. Styling things with React Native is not a breeze but I have no complaints to it but I’ve heard a lot of complaints from Native iOS developers about whatever it is that you guys do for styling. I’m glad it’s an improvement whether it’s just slightly or not.

Jaim: I’m curious a little bit on basic building blocks. If you have a view with the button, you click on the button, it goes to the web source, downloads some data and chose other view. How does that translate into the React world?

Tyler: A great question. You can thing of React as like—and again, I have no idea how things are done in Native iOS land so I might be explaining the things you guys do. But essentially, with React, everything is like a component, you just have components built on components and they nest components. It’s a really popular pattern in React is to have this idea of like container of components and also like a presentational components.

The way that I structure a React app is all of my business logical, my Ajax requests, those are all in what I call a container component. The sole purpose of a container component is either like manage dates or to fetch some state from some database and then get that state and then pass that state down to presentational components just to render the view.

The idea is that you have these smart components that understand the data and they manage the states and then you have these presentational components which all they do is they receive data from their parent component and then they just render it to the view.

It’s really nice because the same way you reason about functions in JavaScript or even other programing languages as well is you can take the same way you think about that and apply it to your UI now where all you’re doing is you have one function which goes and fetches some data and then you’re passing that data to another function which just receives it and displays it to the view. As far as the mental model for React, it’s really nice because it’s just that process.

Layne: In that model, can it be broken down? Is there flexibility—ruin that model?

Tyler: Yes.

Layne: The reason why I ask is because in UI Kit, it’s really easy to step out of the bounce of the MBC architecture. I’m just wondering if it’s the same in the React.

Tyler: Yes. They have, you probably heard the thing they called redux, it’s hugely popular. That paradigm came along and basically said, “Hey, instead of keeping the state of your app in components, what if we keep the state of our app in this huge state tree and that will give us lot of benefit because one we have this snapshot of the current state of our app so you can do things like time travel debugging which is really cool. Even if an error occurs, you can see what the current state of your entire application was at what point.”

That model instead of keeping state inside of component, it puts it in a store, or basically one big JavaScript object and then your components can subscribe the what parts of the store that they want.

If I have a footer component which needs to know the current tab we’re on, the footer component can just say “hey redux, keep me updated whenever that particular part of the state changes and then I’ll update accordingly.”

It’s kind of the same idea with as I described like container and presentational components, but instead of the state living inside the container, it’s now living inside of a redux store and then you just subscribe to those changes. That’s another paradigm, it’s super popular, it’s really nice with React Native actually because this will be interesting for you all. When I want to Native initially, I’m so used to if I go to view new fetched data and then render it, I don’t need to cache anything cause it’s cool.

With Native, it’s not a good idea because when you’re switching tabs, if you just fetch data every time you switch a tab and never cache anything, it’s a terrible experience.

Version 1.0 of our app was every time you switch a footer tab, you would go and fetch the data again. That was kind of a learning experience for me. But with redux, it’s really nice because when you go to a new view, you can say, “Hey, has this date been fetched before or basically is it already in redox? If it is then render it, if it’s not then go ahead and fetch and update redox.” It’s really nice model for Native as well.

Charles: The other thing is this a lot of that’s state is managed through pure functions called reducers. Since they’re pure functions, they don’t have side effects or there are a few other properties related to that. Basically what it boils down to is, this is where the time travel debugging comes in, is that those state changes are so simple and so easy to reason about that the machine can actually backup and back forward and you change your state and it just does the right thing. It’s really easy because you can just look at which of those reducers is being triggered and you can know beyond any certainty that it’s just going to do the right thing

You change the state, you just know what it’s going to be, you know what it’s going to do and it keeps things really simple and makes it really easy to test.

Tyler: Exactly.

Layne: Time travel debugging sounds magical to me.

Tyler: Time travel debugging is one of those things where you show your friends like, “Hey, this is so cool.” You show your developer buddies and they think it’s really cool but you never really use it. Though my favorite thing about redux is the developer tooling that surrounds it. There’s this thing, I don’t exactly what, it’s just called Redux Dev Tools.

Basically whenever I’m developing an app, I have these Redux Dev Tools open as well. Anytime my state changes or anytime I dispatch an action to tell my state to change, I’m aware of that. If something goes wrong, I can look at what actions were dispatched and exactly what changes were made to the states in a very nice user interface and kind of see what happen. I can revert to a specific commit or revert to specific state changes. It’s just a really, really nice experience.

Layne: Yeah, I’m recalling a time I think yesterday when I was doing some debugging, I stopped the programmer and a debugger. I have my stack trace right, but I’ve gone between a couple threads and so I go back in the stack trace little bit and recorded the frames but the state’s lost. I can’t even see where any of these state. I would take that time travel debugging any day.

Tyler: Yeah, that’s awesome.

Layne: What are the down sides? I’m really curious from your opinion or anyone else.

Tyler: I started way back. I’ve been there since React Native .5 and it’s on .31 right now so I’ve kind of seen it all. Upgrading with React Native is just a huge pain and I haven’t found a decent way to do it yet. This is kind of embarrassing, everyone who’s in React Native land is going to laugh at me for this.

Basically whenever it is time for us to upgrade which is basically whenever they make a change to React Native Core that I need to have, what I’ll do is I’ll just like initialize a brand new React Native project and then I’ll take all of our code and just migrate it to that new project rather than trying to update the actual project that I have and then I’ll just move my GIF folder over.

Layne: Why is that?

Tyler: I don’t know.&nbsp; It’s probably one of those things because I’m so naive with the Native world. If something breaks, I’m just clueless to what’s wrong. One example was we were running .13 for a while but in .14 they introduced Android so Android wasn’t there from the beginning. When they did that, the folder structure all changed. They admitted a bunch of brand new Android stuff.

We tried to upgrade with the CLI that they have and then it just didn’t work and some stuff broke. Firebase wouldn’t work with the new version, just things like that where it’s like because we’re moving so quickly which is great, because we’re getting all of these features but it sucks us from a stand point of trying to maintain and upgrade a code base consistently. I’ve actually had really good luck with just creating a new project, we’ve been messed up over repeating everything again and it takes probably an hour but it’s not too bad.

That’s probably the biggest complaint I have and they’re super aware of it. It’s getting better every iteration. I think my issue is I wait ten versions and then I try to upgrade so it’s just like I kind of do it to myself.

I did have some way back about six to eight months ago I think as well. We were having some animation issues where a route would change and then it would go fetch some data then there will be some dank there. But I think again that was probably me being naive to the Native platform because on web this idea of waiting for specific animations to end before you do anything heavy is important but it’s not critical.

With Native, if you’re doing a route change but as that routes change, if you go and then fetch some data from some API, there’s going to be some issues there because it’s like doing multiple things at once.

They introduced this thing called interaction manager for React Native. What it allows you to do is as you can say like hey if there are any animations running around, if the app is doing anything to do with transitions or whatever, don’t run this code. That was a life saver for my code base just because I can wrap everything with interaction manager call-backs. Basically now whenever I do route changes, I don’t have to worry about anything happening during the route transition because I’ll wait for that transition to finish before it goes and runs that code.

Those are probably my two biggest complaints. The transition ones has been fixed now and the upgrading one I think is getting better but it’s still kind of a pain.

Layne: That’s sounds like a side effect of not being able to do proper threading. Is that the case?

Tyler: I think so. The way it works is all of your JavaScript runs on this JS or JavaScript Core thread. If you ask me to start doing multi threading in a React Native App, I wouldn’t even know how to do it or if it’s even possible. I think the answer to your question is yes.

Layne: Interesting.

Jaim: Does it cause any problems with animations? It feels like a Cordova app. I can spot a Cordova app from the web. It doesn’t look right.

Tyler: Oh, yeah.

Layne: Do they look Native?

Tyler: The idea of our app that we’re building, it’s basically like a social network for individuals affected by cancer. It is kind of like Twitter mixed with Facebook kind of, there’s a lot of lists, there’s a lot of posts, there’s a lot of user profiles. With all of those, I haven’t noticed any like lists. The only animation issues that I have seen or when I’m specifically doing route transitions, and even those were like this new version of the app that we’re about to release, this all begun just because of the process I just explained.

I don’t know what they’re doing under the hood as far as making animations smooth or making lists move but I never had any issues with that.

Charles: I can tell you some of it. In objective C, in&nbsp; Swift, you typically do a list with UI table, if I'm understanding things quickly.

Tyler: That’s right.

Charles: If that’s the way your approach things, my understanding is that React Native and Native script, because I’ve talked a lot more to the Native script guys than the React Native guys. They do things in a lot of the same way. What they do is since JavaScript core can call into or spin up an Objective C or Swift process, then what it does is spins that up. It creates the UI table view and a corresponding view controller that has the APIs, the U.I table you expect it to have and then it feeds the data in. When it makes those calls, it calls back into JavaScript and says here’s the data you need to put into.

That scroll is basically what you would expect in a Native app because it’s a UI table view just like the Native app. When you scroll it, it’s gonna perform because it’s a Native rendered view just like you have in a Swift app. A lot of the other view type things are done in the same way. Yes, you can style them some and we’ve talked a bit about that. The default is just the default look and feel and performance level of a Native app.

React Native app are much harder to spot because it’s not a web view that’s customized and styled to look like a Native view. It’s actually a Native view that makes calls back into the JavaScript when it needs in order to do its job. Does that make sense?

Jaim: Very cool.

Layne: Yeah, that’s so awesome. That’s what makes React Native, for me, a very approachable cross platform approach.

Charles: Yap. One other thing I think is interesting here that I don’t know if we’ve talked about is that people who are accustomed to and enjoyed building applications in Swift and Objective C, I think a lot of them write this off as a tool that they’re just never going to need because they’re comfortable where they’re at. But if you want to go build an Android app that is comparable to your iOS app, then there’s no reason why this is not a viable option for you there too.

If you’re out there and you're building iOS apps and you like the way you do that and you just want some other cross platform system that will work on Android and I think they’re working on Windows phone or some other systems as well. If you’re looking for things that will work on those, then you just want to keep your iOS app the way it is and kind of pioneer the way that your app works and interacts with the user, then you can continue to do that in Swift and then you can use these the other tools to build the apps in the other platforms.

Layne: Tyler, one other thing that came to mind is you talked about route transitions.

Tyler: Yup.

Layne: I’m guessing that with React Native, the entire state of your app is accessible through routes. Is that correct?

Tyler: Kind of. I don’t know, I think you have some underlying knowledge about how your view of routes in the world works that just different from the mine because I’m coming from web.

Layne: I’m coming from the web perspective of if I have a web app, if I’ve structured it right, then I can basically get anywhere through routes.

Tyler: Okay, gotcha. Yeah, it’s the same idea. React is interesting, React Native is still trying to figure out the best way to approach routing. Initially, there was a I think it’s called a navigator iOS that you use for routing and then they switched it to like a cross platform, just a navigator component which is really interesting because I don’t really know how to describe it all just right now.

It’s a decent way of doing routing. Now, they’re experimenting with a new version of routing called Navigator Experimental and I'm assuming they’ll change that name once it’s out. The whole idea of that one is it’s more like a redux approach, going back to what we talked about earlier. If you want to change a route, you would just dispatch an action and then the state of your router would change to that new route. It’s kind of interesting because there’s a few different ways to do routing right now in React Native. I wouldn’t say none of them were super, super interesting or super cool.

Layne: The reason I bring this up is because there is not really much of a concept of routing in UI Kit. I would say this is a huge benefit because doing this stuff manually in UI Kit is pretty tedious and a little bit difficult. I find the routing and web app stuff to be significantly better in that regard.

Tyler: I’m coming from React Router which is awesome. This is probably my, again, one of those moments where I love React Router, it’s so great. When I go React Native, it’s not as good as React Router so I judge it. It sounds like it still really great comparatively to other things.

Layne: Yeah, I would say it’s vastly superior.

Tyler: I’ll stop complaining about it then.

Layne: Yeah. In fact in our app that we have right now, we have a few routes that our app accepts. It’s basically a bunch of custom code that says, “Hey, you wanna go here? Okay, let me create this view controller and push it on the stack. Oh, I need to go here after that. Okay, let me create this view controller and push it on the stock.” It’s not a magical route system.

Tyler: Gotcha.

Charles: I was hoping that you could also talk to us just for a minute about &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; RNPM.

Tyler: Yeah, this is really cool. You’re going to get may spill from a web side. Initially, one of the hardest things about…

Charles: People are pretty familiar about coco pods and I think it’s kind of similar.

Tyler: It’s the same idea.

Probably the hardest thing for me with React Native was whenever I had to link a Native module into my code. Up until I started, I had never opened ex-code before. For example, there is a library call React Native vector images. In order to use it, you have to basically link that library with ex-code and also with Android studio.

What you used to have to do is use to have to go—I’m sure you are all familiar with—basically go into ex-code and going to like build phases or whatever and do all that linking. But now, what you can do is there’s a tool, it used to be called RMPN and now it’s actually tied into React Native Core where you can just basically MPM install which is kind of like for what I understand your version like coco pods or just like pod install.

MPM install a specific package and then instead of having to open up ex-code and enter a studio and manually link the package, you can just run React Native link and it will go and do all that for you.

That was really nice for me specifically because ex-code just freaks me out so much that I always break stuff. But now when I develop I never really have ex-code open just because to run a React Native app, you just run from the CLI React Native run iOS or run Android. That will open up the simulator for you and then on those rare occasions where you do need to link a package, you can just run React Native link from the CLI which is really nice.

Layne: I love to hear that ex-code freaks you out.

Tyler: It does. I’m coming from Sublime which is just like you just open it up and that’s it. There’s not even a play button, you just run it.

Layne: Yup, yup, yup.

Jaim: I’ve been using it for 10 years off and on, it still kind of freaks me out.

Tyler: The idea of having to clean stuff, I don’t know how many times I’ll make changes and it wouldn’t work and I’d spend a day trying to figure it out. And then I’ll be like, “Oh yeah, I think I need to like clean this.” I don’t know what that does but it’s going to clean it and it would work. It just freaks me out.

Jaim: Is that a simulator you can call?

Tyler: Yeah, exactly

Jaim: There’s like the three steps of it won’t work. With ex-code it’s like do a clean build, reset the simulator and then restart your computer and then that’s it.

Tyler: Yeah, exactly. Exactly. I learned all three of those steps the hard way, trust me.

Charles: How do you go about testing your React Native application?

Jaim: Great idea, or great question. It’s very similar to just the web app, I haven’t had too much testing with React Native just because—thats terrible to say—just because we’re going to start a plan that we were trying to get an NDP out initially.

I assume it’s very similar to web and what’s nice about redux is because as you mentioned earlier, you have all of these functional components that just receive data and output some view. Essentially, what you can do is there’s a few different ways to do it. I think the most popular one with React and with redox specifically is basically you’re just testing the app and put all of those functional component or you’re even just testing the inputs. You can assume if the input is the same that the output’s going to do the same as well.

I don’t know, I don’t think a specific pattern or a specific library has really come to the forefront of testing React Native app. Its kind of the same with React as well like, there’s enzyme by AirBNB which is nice but there hasn’t been a specific tool that the community has rallied around. That’s the way we do testing. Even Facebook is pushing just now, there’s a few different ways. I don’t think any of them are amazing or the community way to do it. I think its all just pretty standard.

Charles: Yeah, it makes sense. There are a lot of great tools out there for testing JavaScript

Tyler: Yup.

Charles: 99% of unit testing is the same no matter what language you use.

Tyler: Exactly.

Charles: Very cool.

Layne: When iOS 10 comes out and there’s new features in iOS 10, how do you take advantage of that before React does or is that even possible?

Tyler: That’s a good question. I’ve never even thought about that.

There is this idea of bridging with React Native. I talked about earlier React Native vector images or whatever. If there is some Native thing that you need to do, I don’t know if this specifically answers your question. You can’t write a bridge, basically you can write some Objective C or Swift code that is able to do something but that basically gives an API to the JavaScript code or JavaScript plan so that your JavaScript can then basically invokes some function that goes and run some Native module.

I don’t know if that specifically answers how do you get benefits from that upgrade but I personally have never really had that want. I know eventually I will, like when there are upgrades, but I have it yet.

Layne: Yeah, I’m sure that’s how you do it then because iOS 10 for example, they’re kind of revamping the entire notification system. I doubt React will have that right off the gate. You would just write a Native module and bridge to it. That makes sense.

Tyler: What’s nice about the JavaScript community is there’s so many people doing JavaScript, there’s so many people doing React Native. I’ve never personally had to write a bridge just because whatever I’ve needed to do, there’s always been a project or a module that’s already doing it that’s been really, really nice.

Layne: Interesting, yeah that’s great.

Charles: Most of these teams too. Live I’ve said, I’ve talked to Ruby Motion which has to maintain parity with the current state of the art so to speak with iOS development. I know that some of the folks that work on Native script and usually within a week or two, they have those features tested and ready to go. The other thing is that we get developer previews for some of the stuff. It’s not like when they announce it that’s it (a) a big, huge great surprise and (b) that we already haven’t already had it for a month if we really wanted to fiddle with it.

Tyler: True

Jaim: That’s true. In fact in iOS, it’s about three months so that seems like it’s plenty of time to get in.

Charles: By the time people have it on their phone, it’s usually pretty well built and tested.

Layne: I have one final question for you, Tyler. Facebook put their weight behind React Native and React and its whole ecosystem Do you think that Facebook’s goal is to create the new generation of app development with this?

Tyler: Oh, that’s tricky. I can tell what they say that I think has held pretty true from what they’ve done. Facebook is interested, and are very transparent about this. Facebook is interested in creating the best product for Facebook. They’ve always said that. If there’s ever something the community needs but Facebook doesn’t care about, they’ll just ask the community to build it.

To answer your specific question, I’m not too worried about it just because what Facebook needs currently is aligned with what I need and&nbsp; what helps me out. It is interesting just watching kind of how everything happens. Facebook is a business and they want to make money. I think their number one thing for React or React Native is just to help themselves build better products. The kind of side effect of that is just building an amazing community and having all these people who now know their specific thing that they use at Facebook can become recruit better and all of those side effects. I really think the underlying principle is they want to help Facebook build a better apps.

Layne: That’s fair. That I think is a great response because it’s not like Facebook could figure out this amazing cross platform way to make apps and then somehow make money for that. They’re never going to able to do that.

Charles: All right so let’s go ahead and do some picks. Jaime, do you want to start us off with picks?

Jaim: Sure, my wife and I were downsizing so I’m getting rid of a bunch of book and stuff. One book I read was released over the past two years. I really liked it andI think many other people will like it. It’s Cannery Row by John Steinbeck. Most of us at least in the US, you know of John Steinbeck from writing depressing, dustful novels. I read him in high school.

This is Cannery Row, it’s set in Monterey, California, kind of skit row. It’s hilarious. It’s laugh at loud funny, people that live in this area, their interactions with each other, they get into weird situations. Very entertaining to read.

Cannery Row in Monterey, California is a poem, a stink, a great in noise, a quality of light, a tone, a habit, a nostalgia, a dream, also a great book. If you’re looking for something to read that is hilarious, check it out, Cannery Row by John Steinbeck.

Charles: I remember reading his books in high school and going uhh…

Jaim: So sad, so sad.

Layne: My pick this week is No Man’s Sky. This is a video game, if you haven’t heard of it, that is set in what they call an infinitely large universe. I was a little bit hesitant about it and on Monday night I just kind of made an impulse decision and bought it. I’m truly amazed at the scale of this game.

It’s a space exploration video game. As a programmer, the technology behind it is just a wonder to me because they claim that there are—if I remember right—it’s like eighteen quintillion planets in this universe. You’re talking I think it’s like nineteen zeros. In essence, it’s infinite. I don’t know what else to say about it, it’s just a super cool technology wonder to me. I just want to know how they accomplished that. So super cool, really cool. I recommended it.

Charles: One pick that I have is kind of an older movie but we got highlights of it when I did Wood Badge a couple weeks ago. They were teaching us about team building and we watched clips from it. It’s Remember The Titans which is just a great movie. I really enjoyed that movie. I’m gonna go ahead and pick that. I think that’s all I got this week. Tyler, what are your picks?

Tyler: I have two. The first one is Dan Abramov from React Europe over a year ago now. This was kind of his introduction to the dev world. He’s the one who built redux and a bunch of cool tooling around redux.

This is his talk where he introduces redux or talks about redux and introduces hot module replacement, time travel debugging, kind of all the things we talked about. That’s a really cool piece of history in the web world that you can watch.

The second one, I mentioned earlier Reactors program is a website I run which basically teaches people about reactors, it’s free. If you heard this and like, “Hey, I want to learn more about Reactors, a free fundamental course that from what I’ve heard is the best way to get up to date with the fundamentals of React.” There’s also going to be a React Native course that I’m hoping to release by the end of this month that you can check out as well.

Charles: Very cool. We also had Dan Abramov on JavaScript Jabber a while back to talk about React and Redux. Tyler was also on JavaScript Jabber a while back talking about careers. We’ll put links to both of those in the show notes. I’m also going to put a link in the show notes for our episode about JavaScript Core and hopefully that will give people an idea on how some of this works behind the scene of your interested in that.

Tyler, if people want to know more about you, follow you on Twitter, see what other awesome stuffs you’re up to these days, what do they do?

Tyler: I am @tylermcginnis33 on Twitter. That’s the best way.

Charles: Awesome, we’ll go ahead and wrap this show up and we’ll catch you all next week.
