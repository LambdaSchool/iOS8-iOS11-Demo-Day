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

* Code: `<insert Github repository link here>`
* Trello/Github Project Kanban: `<insert trello board here>`
* Test Flight: `<insert beta signup link here>`
* YouTube demo video: `<insert video url here>`

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

    `Even though it was one of the most simple, it was the Launch Screen.  I come from a design background, and feel that UX/UI can make or break an app.  Adding a Launch Screen made the app feel like a production app, and set the tone for a lightweight user experience within the app.`

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

    `Deleting a pending local notification when an object is deleted from the array.  I was able to find the code to use, but being very new to local notifications, I was unsure how to implement it correctly.`
  
3. Share a chunk of code (or file) you're proud of and explain why.

    `extension FoodMinderViewController: AddFoodMinderDelegate {
    func foodMinderWasAdded(_ foodMinder: FoodMinder) {
        foodMinderPersisitentController.foodMinders.append(foodMinder)
        DispatchQueue.main.async {
            self.foodMinderPersisitentController.saveToPersistentStore()
            self.tableView.reloadData()
        }
    }
}`

`Delegation is still a challenge for me to overcome.  Though I knew once I created a reminder, I needed to tie that into an object I can further manipulate.  I was able to work through the logic to creating an array of objects from a created notification, and was able to implement it into a delegate.  This is probably one of my most excited moments during the whole project.`
  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

    `Sometimes it's hard to remember to take time to eat...When you live a hectic and busy lifestyle (especially with work, school, kids, and family), sometimes it's hard to remember to take necessary snack and meal breaks.  The next thing you know, it's dinner time, and you've hardly eaten all day, if you've even eaten at all!
But don't worry, foodMinder's got your back!
foodMinder is a lightweight iOS app to help you remember to eat throughout the day!`
  
5. What is your #1 feature?

    `Without adding to your already hectic day, 
foodMinder's #1 function is to manage quick and easy food reminders, 
with a lightweight and simple interface.`
  
6. What are you future goals?

 `Recurring foodMinders
 Suggested foodMinders
 Suggested meals
 Nutrition tracking`

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
