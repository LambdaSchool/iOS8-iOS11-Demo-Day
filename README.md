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

* Code: [Poopmaster](https://github.com/mredig/Poopmaster)
* Trello/Github Project Kanban: [Trello](https://trello.com/invite/b/CHICMbjN/cbe78ac10b15a9d7d1c7b809562fad8a/poopmaster)
* Test Flight: [Testflight](https://testflight.apple.com/join/Dt85uyxu)
* YouTube demo video: `<insert video url here>`

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

    Charts - they just look so cool and are a great way to visualize your data!

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

    Figuring out the migration process within Apple's sandboxing requirements. It was mostly just a logic/process problem, and it was fixed through "just doing it" and rubber ducking how the process might work. 
  
3. Share a chunk of code (or file) you're proud of and explain why.

	    private var _daysLogged: (days: Int, lastLogged: Date)?
		var daysLogged: Int {
			if let days = _daysLogged, Date().timeIntervalSince(days.lastLogged) < 60 {
				return days.days
			}
			let fetchRequest: NSFetchRequest<CDPoop> = CDPoop.fetchRequest()
			let timeDescriptor = NSSortDescriptor(key: "timestamp", ascending: true)

			fetchRequest.sortDescriptors = [timeDescriptor]

			var oldest: CDPoop?
			let moc = CoreDataStack.shared.mainContext
			moc.performAndWait {
				do {
					let allPoops = try moc.fetch(fetchRequest)
					oldest = allPoops.first
				} catch {
					NSLog("Error fetching oldest poop: \(error)")
				}
			}
			guard let oldestDay = oldest?.timestamp else { return 1 }

			let difference = Calendar.current.dateComponents([.day], from: oldestDay, to: Date())
			let days = (difference.day ?? 0) + 1
			_daysLogged = (days, Date())
			return days
		}

  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

    Track your digestive health by logging every time you poop into this app. You can get additional insight into your health if you log additional statistics about your stool. Your data will be easily visualized with pretty charts!
  
5. What is your #1 feature?

    Bowel movement logging with data visualization.
  
6. What are you future goals?

    * Track food intake to analyze how your diet is affecting your digestive health.
    * scrap realm code in new version
    * update for new revenue model
    * ipad support

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
