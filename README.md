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

* Code: https://github.com/narmkumar/MedicationTrackerLite
* Trello/Github Project Kanban: https://www.taskade.com/v/Na2BVjB5p4UHz2RD
* Test Flight: `<insert beta signup link here>`
* YouTube demo video: `<insert video url here>`

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

    My favorite feature to implement was how we auto-updated our "Today's" Medication section with the information from the date formatter. It was interesting to be able to convert the Date Formatter value into a string, then into an Int, and back into into a string with just the day of the week we needed to auto update our medication section.

2. What was your #1 obstacle or bug that you fixed? How did you fix it?
   Our main obstacles / bugs were the small details in recoginzing where our functions should run properly. Our logic for the most part was straight forward, but had to deal with the small details to get our app to behave the way we wanted.

3. Share a chunk of code (or file) you're proud of and explain why.

    As simple as this looks, this feature allowed us to implement the auto-update day feature in our app by checking the value of the user defaults every time. By using a delegate from our controller to determine whether to reset the view or not, we were able to achieve an extremely important feature with just a few lines of code.

        // Runs once view loads. Sets the day in user defaults and sets the controllers delegate to itself.
    override func viewDidLoad() {
        let defaults = UserDefaults.standard
        defaults.set(medicationController.today, forKey: "day")
        super.viewDidLoad()
        medicationController.delegate = self
        }
    
    // Runs before the view will appear. Compares current day to saved day in order to run resetDay() method.
    override func viewWillAppear(_ animated: Bool) {
        let day = UserDefaults.standard.string(forKey: "day") ?? ""
        let newDay = medicationController.getToday()
        if newDay != day {
            medicationController.resetDay()
        }
        super.viewWillAppear(animated)
        tableView.reloadData()
    }  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

Medication Tracker Lite is the perfect app for anyone who wants to keep track of the medications they need to take on a daily basis. It’s this simple: input your medication info and frequency of consumption, along with a description, and you’re good to go! Every day, the app will refresh and update so you will know exactly what meds need to be taken for that day.

5. What is your #1 feature?

    Auto Refresh  / Low Pill Count - Refill Reminder.
  
6. What are you future goals?

    Future goals would be to implement a reminder notification for each medication and/or groups of medications so that the user can be notified at the proper times when they need to take their medicines.

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
