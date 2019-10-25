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

* Code: https://github.com/morsedan/HeartRateTracker/tree/master
* Trello/Github Project Kanban: https://trello.com/b/FYUuI4EB/80-20-heart-rate-tracker
* Test Flight: `<insert beta signup link here>`
* YouTube demo video: `<insert video url here>`

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

    I really enjoyed implementing setting lactate threshold heartrate. I like how it cascades through to get the most accurate way of setting the user's LTHR even if you user doesn't understand how to use it.

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

    Getting the dates of the tableview header was a big headache. I ended up just adjusting it manually every time I display the date. 
  
3. Share a chunk of code (or file) you're proud of and explain why.

    This is the code for setting the LTHR:
    
    func setLTHR() {
        guard let lthrText = lthrTextField.text, let maxHRText = maxHRTextField.text, let ageText = ageTextField.text else { return }
        if !lthrText.isEmpty {
            guard let lthr = Int(lthrText)
                else {
                    lthrAlert(with: lthrText)
                    return
                    
            }
            guard lthr > 0
                else {
                    lthrAlert(with: lthrText)
                    return }
            settingsHelper?.setLTHR(to: lthr)
            
            dismiss(animated: true, completion: nil)
            
        } else if !maxHRText.isEmpty {
            guard let maxHR = Int(maxHRText)
                else {
                    lthrAlert(with: maxHRText)
                    return
                    
            }
            let lthr = Int(Double(maxHR) * 0.88)
            guard lthr > 0
                else {
                    lthrAlert(with: maxHRText)
                    return
                    
            }
            
            settingsHelper?.setLTHR(to: lthr)
            
            dismiss(animated: true, completion: nil)
            
        } else if !ageText.isEmpty {
            guard let age = Int(ageText)
                else {
                    lthrAlert(with: ageText)
                    return
                    
            }
            let lthr = Int(Double(220 - age) * 0.88)
            guard lthr > 0
                else {
                    lthrAlert(with: ageText)
                    return
                    
            }
            
            settingsHelper?.setLTHR(to: lthr)
            
            dismiss(animated: true, completion: nil)
        }
    }
  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

    Fitness trackers for endurance athletes aren't hard to come by, but what if you want to train using the 80/20 rule? Finally, there's an app for that! The 80/20 rule says that you should spend 80% of your training time below 90% of your lactate threshold heartrate (roughly 88% of your max heartrate), and as much as possible of the rest of the time above 102% of your lactate threshold heartrate. This app helps you see how well you are doing at following the 80/20 rule and helps you plan your coming workouts. 
  
5. What is your #1 feature?

    See what percent of your workout you spent in zone 1, zone 2, and zone 3 of a 3 zone heart rate scheme.
  
6. What are you future goals?

    - Be able to take .fit files and download them from the web.
    - Show 80/20 split over the length of a week.

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
