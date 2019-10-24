# iOS8 and iOS11 Demo Day

## Requirements

1. Fork and clone the repository
2. Create a pull request (PR) and tag your TL and instructor

**Add your:**

1. Slide deck (4 required slides in Keynote)
2. Add your links
3. Answer all the questions (Replace placeholders with your answers)
4. Video demo (2 minutes max), share YouTube video link

The video demo is for sharing your work on your portfolio, but it is also a fallback if you have a technical issue during demo time.

## Links (Add your links)

* Code: `https://github.com/jonbash/CountdownTracker`
* Trello/Github Project Kanban: `https://github.com/jonbash/CountdownTracker/projects/1`
* Test Flight: `not sure how to generate link!`
* YouTube demo video: `https://youtu.be/GeCUVl4tQjo`

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

    `That's a tough one... I think I'll go with combination filtering/sorting. It ended up being very easy and straightforward, but it somehow just felt very satisfying to implement.`

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

    `At various points, seemingly innocuous things caught me off-guard. Most recently, I was having a hard time getting completed countdowns to alert the user when the countdown had completed if the app was open. I had not yet implemented dynamically updating countdown timer cells, and implementing that actually ended up making the alert a total breeze.`
  
3. Share a chunk of code (or file) you're proud of and explain why.

    `The following portion of my EventController made working with the same instance of the controller as a singleton very simple without having to pass the instance around via segues and delegates and such. I borrowed the concept from some C# coding videos I've been watching, so I'm not sure if the naming convention is "standard," but it works quite well.`

```swift
class EventController {
    //...
    
    private static var _shared: EventController?
    
    static var shared: EventController {
        if let sharedInstance = _shared {
            return sharedInstance
        } else {
            _shared = EventController()
            _shared?.loadEventsFromPersistenceStore()
            
            return _shared!
        }
    }
    
    //...
}
```
  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

    `Add the dates/times of important events in the near or distant future, and the app tells you how much time is left until then. When it arrives, you get an alert telling you the countdown has ended. You can sort/filter your list of countdowns by tags, end date, and more.`
  
5. What is your #1 feature?

    `Sorting/filtering`
  
6. What are you future goals?

    `Post-countdown notes... Coloring countdowns based on nearness... Viewing archived countdowns... Adding images to countdowns... Customizable formatting... Recurring countdowns...`

## Required Slides (Add your Keynote to your PR)

1. App Name / Team Slide
2. Elevator Pitch
3. Your #1 Feature (Customer facing — what can I do with your app?)
4. Future Goals

## Slide Requirements

1. 50 pt font minimum
2. Be concise — don't write sentences/paragraphs (put these in your slide notes for speaking)
3. 3-6 bullets maximum per slide
4. Do the squint test (can you read the text if you squint, if so, make the font bigger)
6. Images are always welcome
7. Do the Grandma Test (Would your Grandma understand you?)

### Optional Slides

1. Blooper: What's a funny bug or blooper? (screenshots/GIFs please)
2. Revenue Model: If the app was your sole source of income, how would you monetize it?

## Presentation Format

**7 minutes/team**

* 4 minute presentation (5 minute hard cap)
* 3 minutes of questions

We have ~12 teams presenting today — please practice your presentation with a timer (as a team), and make sure you fit within the time limit.

Plan on having one person present the slides and live demo. Please practice your presentation in front of a mirror or with your team 2-5 times. Have the app running and visible in QuickTime so you can quickly transition between slides and live demo.

* App Name / Team Slide (30 seconds)
* Elevator Pitch Slide (30 seconds)
* Your #1 Feature (30 seconds)
* Live Demo (2 minutes)
* Future Goals (30 seconds)
* Questions (3 minutes)
