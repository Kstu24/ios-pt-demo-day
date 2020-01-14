# iOSPT Demo Day

## Requirements

1. Fork and clone the repository
2. **Add your presentation content**
    1. Slide deck (4 required slides)
    2. Links
    3. Answer all questions 
    4. YouTube demo video (1-2 min max)
3. Polish your Github Code repository
    1. Add screenshots and an overview to your GitHub Code Repository
    2. You should make that repository the "Public Portfolio" for your project
    3. Look at [John Sundell's Splash project](https://github.com/JohnSundell/Splash) for inspiration (code, images, GIFs)
4. Create a pull request (PR) and **tag your TL and Instructor**

## Links

* Github Code: `https://github.com/jholowesko/LunchSelection`
* Github Proposal: `https://github.com/Kstu24/ios-build-sprint-project-proposal`
* Trello/Github Project Kanban: `https://github.com/jholowesko/Lunch-In/projects/2`
* Test Flight Signup (Recommended): `<insert beta signup link here>`
* YouTube demo video (Recommended): `https://www.youtube.com/watch?v=JDAD1Af4Nvk&t=1s`

## Hero Image

`<Post one screenshot in an iPhone Simulator frame or an iPhone 11 Pro render using placeit.com>`

## Questions (Answer indented below)

1. What was your favorite feature to implement? Why?

`We took into account some helpful UI elements that changed the voted buttons from blue to green when voted or not voted. It makes it easier for the user to use and see which has been selected and which ones have not.`

2. What was your #1 obstacle or bug that you fixed? How did you fix it?

`Kevin- How to establish notifications. Watching a lot of demos and researching stack overflow. 
john- Establishing multiples arrays that all saved to persistent store. Had to refactor a lot of code from the origional model to modify which array was being accessed from persistent store.`
  
3. Share a chunk of code (or file) you're proud of and explain why.

     Kevin - @IBAction func notificationTriggerTapped(_ sender: UIBarButtonItem) {
           let mDepartmentWinner = winnerWinner(deparment: modelController.marketingDepartment)
           let dDepartmentWinner = winnerWinner(deparment: modelController.designDepartment)
           let fDepartmentWinner = winnerWinner(deparment: modelController.financeDepartment)
           
           let content = UNMutableNotificationContent()
           content.badge = 1
           content.body = """
                           Marketing Department top choice: \(mDepartmentWinner)!
                           Design Department top choice: \(dDepartmentWinner)!
                           Finance Department top choice: \(fDepartmentWinner)!
                           """
           content.subtitle = "The votes have been casted."
           content.title = "TIMES UP!"
            
           let trigger = UNTimeIntervalNotificationTrigger(timeInterval: 5, repeats: false)
            
           //creating the request
           let request = UNNotificationRequest(identifier: "timerDone", content: content, trigger: trigger)
           UNUserNotificationCenter.current().add(request, withCompletionHandler: nil)
           
    Figured out how to set a notification on my own!
        
    John - func toggleDepartmentRestaurant(array: OfficeDepartment, positionInArray: Int) {
    let departmentNumber = array.departmentNumber
    switch departmentNumber {
    case 1:
        if array.restaurantArray[positionInArray].didSelfVote == true {
            marketingDepartment.restaurantArray[positionInArray].numberOfVotes -= 1
            marketingDepartment.restaurantArray[positionInArray].didSelfVote.toggle()
        } else {
            marketingDepartment.restaurantArray[positionInArray].numberOfVotes += 1
            marketingDepartment.restaurantArray[positionInArray].didSelfVote.toggle()
        }
    case 2:
        if array.restaurantArray[positionInArray].didSelfVote == true {
            designDepartment.restaurantArray[positionInArray].numberOfVotes -= 1
            designDepartment.restaurantArray[positionInArray].didSelfVote.toggle()
        } else {
            designDepartment.restaurantArray[positionInArray].numberOfVotes += 1
            designDepartment.restaurantArray[positionInArray].didSelfVote.toggle()
        }
    case 3:
        if array.restaurantArray[positionInArray].didSelfVote == true {
            financeDepartment.restaurantArray[positionInArray].numberOfVotes -= 1
            financeDepartment.restaurantArray[positionInArray].didSelfVote.toggle()
        } else {
            financeDepartment.restaurantArray[positionInArray].numberOfVotes += 1
            financeDepartment.restaurantArray[positionInArray].didSelfVote.toggle()
        }
    default:
        print("No Matched Departments")
        return
    }
    print("Toggled item in corresponding department")
    
    Had to figure out which array was being called and have them all act independently with sharing similar data.
    
    
    
    
    Also using SF symbols because they are new and haven't been used frequently. Replaced some stock symbols with some new moderne symbols. 
  
4. What is your elevator pitch? (30 second description your Grandma or a 5-year old would understand)

`You can have your work lunch orgainized by voting on a place to meet.`
  
5. What is your #1 feature?

`All the arrays work seperatley and independently even though they all share the same data.`
  
6. What are you future goals?

    `Incorporate Icloud networking!`

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

Plan on having one person present the slides and live demo. Please practice your presentation in front of a mirror or with your team 2-5 times. Have the app running and visible (Simulator or QuickTime) so you can quickly transition between slides and live demo.

* App Name / Team Slide (30 seconds)
* Elevator Pitch Slide (30 seconds)
* Your #1 Feature (30 seconds)
* Live Demo (2 minutes)
* Future Goals (30 seconds)
* Questions (3 minutes)
