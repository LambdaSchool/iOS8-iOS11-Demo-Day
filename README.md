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

* Code: `https://github.com/ios11superteam/FoodyFriends`
* Trello/Github Project Kanban: `https://trello.com/b/TobSkpsg/ios-11-build-week-1-foody-friends`
* Test Flight: `<insert beta signup link here>`
* YouTube demo video: `<insert video url here>`

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

    My favorite feature to implement was the notification popping up at a specific time/date

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

    My number 1 obstacle was the notifications popping up at a specific time. I fixed it by making sure I set only flags and    not an entire converted Date() object.
  
3. Share a chunk of code (or file) you're proud of and explain why.

    func randomIsComing() {
        for index in 0...(groupMembers.count - 1) {
            let isComing = Int.random(in: 1...10)
            groupMembers[index].isGoing = (isComing % 2 == 0) ? true : false
        }
    }
    I am proud of this code because of how compact the code is for the logic being used.
  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

    Foody friends is an app that you can schedule a place to eat with your friends/co-workers. Friends can decide if they are attending or not and it will notify them when to leave.
  
5. What is your #1 feature?

    Schedule to place to eat and app will send a notification to members when it is time to eat!
  
6. What are you future goals?

    Allow users to vote on going to a place or not, implement yelp, and maps/eta time till location of meetup.

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
