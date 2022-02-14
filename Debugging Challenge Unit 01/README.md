# Unit 01 - Flix Part 1 - Debugging Challenge

Unit 01 did not have many "breakable" features implemented, but this challenege should be a good intro into what debugging in Xcode can look like. This challenge will have several bugs with varying levels of difficulty. Xcode should warn you about some of the bugs, but there may be some bugs that will require searching.

As with all of these challenges, your goal is to get the app running in the same way the assignment app runs. Avoid changing the app name and icon (it is not a part of the challenge). And as always, be sure to utilize all of the resources available to you: the CodePath Slack server, CodePath discussion system, and Google.

Good luck and have fun!

## Hints
<details>
    <summary> Click to show hints!</summary>

* Carefully look through the code and fix all possible typos
* Some bugs were addressed in the assignment videos. Rewatch the videos if you encounter any similar issues.
* Open up your console! Xcode should log some of the errors for you. Search some key words in Google and read through resulting documentation/forums.

</details>

## Solutions
<details>
  <summary>Click to show solutions!</summary>

  These are the solutions to Unit 01 with brief explanations about why the bug is present. Feel free to open up an issue if you have any questions about any of the solutions/explanations.

  1. There is a typo in MoviesViewController. We initialized `tableView`, but attempted to access the dataSource, delegate, and dequeueReusableCell using `TableView`.
        * Xcode does warn you about this error, but typos in code are very common so it's good to get in the habit of checking over your spelling accuracy when chasing bugs.
  2. The API key is incorrectly copied/pasted.
  3. The `viewDidLoad()` function in MoviesViewController should contain `self.tableView.reloadData()`.
        * This was mentioned in the [TableView Setup video](https://youtu.be/zjOe5J7gC6A?t=628).
  4. The synopsisLabel outlet in MovieCell is not connected to any labels in the storyboard.
        * <img src="https://github.com/yujioshiro/iOS-Debugging-Challenges/blob/main/Solutions%20Assets/Unit%2001/synopsisLabel%20Outlet.gif" alt="gif showing how to connect synopsisLabel outlet to label on storyboard" width="960">
  5. The identifier for the MovieCell is not set to 'MovieCell'.
  6. The designated entry point is not set.
        * While this bug/setting was not covered in Unit 01, a quick google search should have given you plenty of sites with the solution.
        * The console spits out `Failed to instantiate the default view controller for UIMainStoryboardFile 'Main' - perhaps the designated entry point is not set?`
            * While this [Stack OverFlow](https://stackoverflow.com/questions/58326717/failed-to-instantiate-the-default-view-controller-for-uimainstoryboardfile-per) is technically about another issue, it should give you a hint as to what to check in your project.
            * Searching "how to set entry point xcode" will result in this [Stack Overflow](https://stackoverflow.com/questions/27683590/how-to-add-an-entry-point-arrow-to-a-tab-bar-controller) thread, which goes over exactly how to set the Initial View Controller
        * Upon setting the Main Storyboard as your Initial View Controller, there should now be an arrow indicating the entry point.
        *  <img src="https://github.com/yujioshiro/iOS-Debugging-Challenges/blob/main/Solutions%20Assets/Unit%2001/Initial%20View%20Controller%20Checkbox.png" alt="Image showing how to fix entry point error" width="960">
</details>
