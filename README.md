# Inspirational Quotes Generator App: Inspirator

This is a tutorial for beginners to make their first iOS application! There are step by step explanations of the environment that you will be coding in and how to get started. Please note that not all aspected of the IDE (Xcode) are explained here but only the ones relevant to the tutorial. Have fun!
	
**Part I**:
- Creating a new Xcode project
- Getting to know the Xcode components
- Build a simple single view application (one button and one label)
- Use an array of quotes to generate the data on the screen
- Add an app icon to your project

**Part II**: (Not available now)

- Use a photo as a background 
- Use API to retrieve more quotes from a website

## Getting to know our Integrated Development Environment (IDE):
*Xcode is the IDE we will be using to develop our iOS applications in this course*. Using it, we can create iOS application, as well as application for mac, apple watch and apple TV. For now, let's focus on iOS apps. 

Xcode doesn't only allow us to write and build code like we used for playgrounds, there is a graphical interface called **Interface Builder** that allows us to build and visualize the User Interface (UI) of the app without coding it. Xcode also contains a **simulator** that allows us to test and run our apps on a simulated iPhone on the mac, without the need of an actual iPhone. 


## Let's get started: New Project
This is the app we will be making in this tutorial: 
<p float="center">
 <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/s1.png" width="30%" height="30%">
 <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/s2.png" width="30%" height="30%">
 <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/s3.png" width="30%" height="30%">
</p>

Let's start by starting a new project. 

<p float="center">
 <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/screen1.png" width="45%" height="45%">
 <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/screen2.png" width="45%" height="45%">
 <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/screen3.png" width="45%" height="45%">
  <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/logo.PNG" width=45%" height="45%">
</p>

The screenshot/step has some information we should get to know:

1. **Product name**: Let's call our app **Inspirator**. This is the name Xcode will use for your project in your file directory.  
2. **Team**: Leave it as *None* for now, later on you can add your Apple Developer team.
3. **Organization name**: You can use your name here or you can use *CodeTechniq* instead.  
4. **Organization Identifier** and **Bundle Identifier**: This is more meaningful if you own a domain name. Here, you should enter it in the reverse order. In our case, the identifier is: *com.codetechniq*
Bundle Indetifier is more consequencial and it is automatically generated from the *Organization Identifier* and *Product name*. This is used to uniquely identify apps in the App Store.
5. **Language**: Select Swift for this. 
6. **Core Data** and **Tests**: These are more advanced options that will be covered later. Core Data is used to store data and load data on and from your phone. 

## Xcode tour
### 1. Main Areas
 <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/main_xcode.png">
 
**Toolbar (Yellow)**: Run/stop project or select scheme. See project status. 
**Navigator (Green)**: Navigate files, folders and see errors
**Editor Area (Pink)**: Write code in swift files (and other types), if *storyboard* is selected, use to build UI components, launcg screen, etc.
**Utilities (Orange)**: See information about files and components in the Interface Builder. 
**Debug Area (Blue)**: for testing and debugging at runtime.

### 2. The toolbar
 <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/n.png">
It contains a lot of important information about the status of your project, so it's always good to keep an eye out for errors or warnings that show it the toolbar. Let's take a quick look at it from right to left: 

| Screenshot| Explanation | 
| ------------- |:-------------:|
|<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/sh.png" width="50%" height="50%"> |**Hiding/Showing areas**|
|  <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/stat.png"> | **Status Bar**|
| <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/run.png" width="50%" height="50%">| **Running/Stopping app** After the first time you run the app, you will be asked to enter your username and password. This will give permissions to the debugger. To stop the process, just click on the stop button. |
| <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/schemes.png"> | The Scheme dropdown menu allows us to manage multiple schemes. A scheme tells Xcode what to build and run when you press the Run button. You can also choose a simulator or device that you want your selected scheme to run on.|

##### Key concepts:
The **build process** is what happens whenever you press on the run button. It consists of a series of tasks that must be completed in order to run the code on the simulator or your phone. **Compiling** is one of these steps and through it, the Xcode compiler turns the code to machine code. During this process, the compiler may find errors in the code, if that happens, the build pricess fails and you can see the errors in your status bar. 

### 3. navigator 

Project navigator, as you can see, there are 9 tabs, but for now, it's okay to just know the main 3 of them: 

<p float="center">
 <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/nav.png" width="30%" height="30%"> 
 <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/find.png" width="30%" height="30%"> 
 <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/issue.png" width="30%" height="30%">
</p>
															    
**Project navigator** *(Pink)* Navigate between files in your project. 
**Find navigator** *(Blue)* Search for a file or words within a file.
**Issue navigator** *(Green)* Can investigate errors with more detail

## Storyboard: setting up the UI

Let's go ahead and open **Main.storyboard** to decide what our screen should look like. For now, all we want is a screen that shows the quote and a button that allows us to change it. It's always good to make a sketch of our design before we code the layout. Fortunately, this is a fairly simple app, so there is not need to do that yet.

The first major concepts to learn about are **View Controllers**. They are the major building blocks for iOS development. The *UIViewController* is a class that controls a set of views. Each view controller contains a root view on top of which we can add more views that we call *subviews*. Here's an image to understand this better:
<p  float="center">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/views.png" width="45%" height="45%">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/hier.png" width="45%" height="45%">
</p>

The storyboard itself has 4 main areas as well. We will discover them when we need them in this tutorial. So let's start this task by adding the **label** that will be initiated with **Would you like some inspiration?** and adding the **button** that says **inspire me**. 

### 1. Add button

Every element we add to our app already has documentation created by Apple to guide us. For instance, here's the documentation for **UIButton**: https://developer.apple.com/documentation/uikit/uibutton 
It's always good when you want to implement a functionality to go to the documentation and make sur eyou ar eusing the right functions and properties. 
In order to add the button, we need to click on the library and search for it. Here's how: 

<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/add_button.png">


So you can understand more clearly. Here's a video of how to add a button in interface builder:
[![Add button in Interface Builder](https://img.youtube.com/vi/yEoF0Is0oeI/hqdefault.jpg)](https://youtu.be/yEoF0Is0oeI)

Notice that in the video, we used **resizing** in the **size Inspector** and **Change the text** in **Attributes inspector**
<p float="center">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/resize-1.png" width="45%" height="45%">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/changetext-1.png" width="45%" height="45%">
</p>

### 2. Add label: 
Try it and if you get stuck, click down for a hint. 
Here's a video of this:

[![Add label in Interface Builder](https://img.youtube.com/vi/VdYrnNaxYTA/hqdefault.jpg)](https://youtu.be/VdYrnNaxYTA)

Similar to the button, we can use the **size inspector** for **resizing** and **attributes inspector** to change the text label. 
We also learned how to change the font and the alignment because we want to the text to be centered and over several lines. 
<p float="center">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/font.png">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/align.png" width="30%" height="30%">
</p>

One problem you'll have is that the label will be outside of the bounds of the screen. 
<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/outofbounds.png">

## Connecting to the code

The first step to connect what we just did in the *storyboard* with the code is to link the **View Controller** to a **ViewController class** that we can write. Let's make a new file for our new code: 

<p float="center">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/newvc-1.png">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/newvc-2.png">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/newvc-3.png">
</p>

Now, let's make the link. For this, we need to have our code and storyboard side by side. This is what we need the assistant editor for. It enables us to have two files side by side and it can be very helpful and for functionalities like adding buttons and labels, time saving. 

<p float="center">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/outlet-0.png" >
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/outlet-2.png">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/outlet-3.png">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/outlet-4.png">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/outlet-5.png">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/outlet-6.png">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/outlet-7.png">
	<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/outlet-8.png">
</p>

In the photos above, we completed 3 main tasks. Adding two **IBOutlets** that link a label and a button to the code and secondly, we added an **IBAction** that is linked to the button. This action is called when the button is clicked, and it executes the code between its brackets. In the final photo, we add a print statement in the IBAction. This print statement will be triggered when the button is clicked and will let us know if everything is functioning properly. Let's run the app and see what the result looks like!

## Run app 

If you run the app, this is what the result looks like. Essentially, we are print debugging this app to make sure that pressing the button calls the right function. 
To check, we need to open our **Debug Area**. How? See below: 
<p float="center">
<img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/printdebug.png">
</p>

[![Print debug](https://img.youtube.com/vi/V9Tad_JD2Iw/hqdefault.jpg)](https://youtu.be/VdYrnNaxYTA)

## Coding!

As a start, we would like to use a pre-selected set of quotes. We do this by declaring a new variable in **InspireViewController.swift** inside the class, as follows: 

##### a. Add quotes:

```var quotes = ["Your limitation—it’s only your imagination","Push yourself, because no one else is going to do it for you","Sometimes later becomes never. Do it now","Great things never come from comfort zones", "Dream it. Wish it. Do it.","Success doesn’t just find you. You have to go out and get it", "The harder you work for something, the greater you’ll feel when you achieve it", "Dream bigger. Do bigger.", "Don’t stop when you’re tired. Stop when you’re done.", "Wake up with determination. Go to bed with satisfaction.","Do something today that your future self will thank you for", "Little things make big days", "It’s going to be hard, but hard does not mean impossible","Don’t wait for opportunity. Create it.", "Sometimes we’re tested not to show our weaknesses, but to discover our strengths", "The key to success is to focus on goals, not obstacles","Dream it. Believe it. Build it."]```

Just to recap and make sure you didn't miss any steps, this is what the **InspireViewController.swift** looks like:

```
import UIKit

class InspireViewController: UIViewController {
    var quotes = ["Your limitation—it’s only your imagination","Push yourself, because no one else is going to do it for you","Sometimes later becomes never. Do it now","Great things never come from comfort zones", "Dream it. Wish it. Do it.","Success doesn’t just find you. You have to go out and get it", "The harder you work for something, the greater you’ll feel when you achieve it", "Dream bigger. Do bigger.", "Don’t stop when you’re tired. Stop when you’re done.", "Wake up with determination. Go to bed with satisfaction.","Do something today that your future self will thank you for", "Little things make big days", "It’s going to be hard, but hard does not mean impossible","Don’t wait for opportunity. Create it.", "Sometimes we’re tested not to show our weaknesses, but to discover our strengths", "The key to success is to focus on goals, not obstacles","Dream it. Believe it. Build it."]
    
    @IBOutlet weak var inspireButton: UIButton!
    @IBOutlet weak var quoteText: UILabel!
    @IBAction func inspireButtonClicked(_ sender: UIButton) {
        print("Inspire Button clicked!")
    }
    override func viewDidLoad() {
        super.viewDidLoad()

        // Do any additional setup after loading the view.
    }
}
```

##### b. Randomly select a quote

Let's add a function that will randomly select a quote for us and display it on the screen. To do this, we will just generate a random number between 0 and the length of the array, then access the entry corresponding to the random number generated. Here's how we do it:
```
@IBAction func inspireButtonClicked(_ sender: UIButton) {
    print("Inspire Button clicked!")
    let number = Int.random(in: 0 ..< quotes.count)
    quoteText.text = quotes[number]
}
```

## Final Touches:

Finally, let's add our logo to the project. You can find the logos in the folder *Images/Icon-set*. There are many photos because we want to add different sizes of the icon for different purposes. Go to the Xcode project and open **Assets.xcassets** then **AppIcon**. Drag and drop the images one by one to its corresponing spot. Here's what that looks like: 


 <img src="https://github.com/PhaelIshall/InspirationalQuotesGeneratorApp/blob/master/Images/logo1.png">
 
