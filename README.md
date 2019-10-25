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

* Code: `https://github.com/bradleyyin/TravelBook`
* Trello/Github Project Kanban: `https://trello.com/b/oBj9JYi8/travel-app`
* YouTube demo video: `https://youtu.be/6uY-EjzW_8g`

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

`My favorite feature to implement was displaying the trip on to the map because having a quick way to see where you have traveled is satisfying, especially when your trip counts are high.`

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

`the number one obstacle I encountered was the the image orientation changing unexpectedly, later found out that the image will be store in the cloud differently even if they look upright at first. So I flatten the image before uploading the image so it is always upright.`
  
3. Share a chunk of code (or file) you're proud of and explain why.

``` swift
func uploadPhoto(photo: UIImage, completion: @escaping (URL?) -> Void) {
    
    guard let userID = Auth.auth().currentUser?.uid else { return }
    
    let photoID = UUID().uuidString
    
    let photoRef = storageRef.child("photos").child(userID).child(photoID)
    let resizedPhoto = photo.imageByScaling(toSize: CGSize(width: 300, height: 300))
    let flattenedPhoto = resizedPhoto?.flattened
    guard let photoData = flattenedPhoto?.jpegData(compressionQuality: 1.0) else { return }
    
    let uploadTask = photoRef.putData(photoData, metadata: nil) { (metadata, error) in
        if let error = error {
            NSLog("Error storing media data: \(error)")
            completion(nil)
            return
        }
        
        if metadata == nil {
            NSLog("No metadata returned from upload task.")
            completion(nil)
            return
        }
        
        photoRef.downloadURL(completion: { (url, error) in
            
            if let error = error {
                NSLog("Error getting download url of media: \(error)")
            }
            
            guard let url = url else {
                NSLog("Download url is nil. Unable to create a Media object")
                
                completion(nil)
                return
            }
            completion(url)
        })
    }
    
    uploadTask.resume()
}

```

the above piece of code help me upload my photos in a configured way so it's not too big and it's always upright.

  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

    `a travel app that allows a comprehensive view , a world map, of the places traveled. The app combines journal and map to allow you to see where you have traveled in a glance on the map, as well as seeing the detail of each travel in a journal form`
  
5. What is your #1 feature?

    `displaying photos on the map, to be view at a glance and show off how many places you have been`
  
6. What are you future goals?

    `work on improving the UX, allow more content in the entry, add a profile page to track total trip counts`

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
