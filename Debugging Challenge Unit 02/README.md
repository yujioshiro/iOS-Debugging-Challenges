# Unit 02 - Flix Part 2 - Debugging Challenge

Unit 02 introduced us to many new app building concepts and, with that, more places where bugs can occur. This week's challenge will contain more bugs that Xcode won't warn you about, so make sure you understand what each section of the assignment is doing so you have some idea of where a bug might originate.

As with all of these challenges, your goal is to get the app running in the same way the assignment app runs. Avoid changing the app name and icon (it is not a part of the challenge). And as always, be sure to utilize all of the resources available to you: the CodePath Slack server, CodePath discussion system, and Google.

Good luck and have fun!

## Hints
<details>
    <summary> Click to show hints!</summary>

* Carefully look through the code and fix all possible typos.
* Some bugs were addressed in the assignment videos. Rewatch the videos if you encounter any similar issues.
* Make sure you check all possible locations of a bug. What I mean by this is even if Xcode warns you about a certain line of code, it doesn't always mean the error is originating in that line (or even that file). Try to follow every possible path up to locate the bug.

</details>

## Solutions
<details>
  <summary>Click to show solutions!</summary>

  These are the solutions to Unit 02 with brief explanations about why the bug is present. Feel free to open up an issue if you have any questions about any of the solutions/explanations.

  1. The type of posterView is set incorrectly.
        * This error occurs because posterView was initialized as a UIView, which does not have the AlamofireImage methods available to it. While the error occurs in the MovieGridViewController file, you will need to go to the file where posterView was initialized.
        * After changing `@IBOutlet var posterView: UIView!` to `@IBOutlet var posterView: UIImageView!` in MovieGridCell, your app should build successfully.
  2. The posterView outlet is not connected correctly.
        * <img src="https://github.com/yujioshiro/iOS-Debugging-Challenges/blob/main/Solutions%20Assets/Unit%2002/posterView%20outlet.gif" alt="gif showing how to connect posterView outlet to UI Image View on storyboard" width="960">
  3. Superhero tab is black/empty.
        * This issue is a fairly simple fix, but may be easily overlooked. The baseUrl on Line 58 of the MovieGridViewController file is blank. Once you set that, the app should now show movies in the Superhero tab.
  4. Movies are not related to superheroes.
        * The request URL's "similar movie ID" is currently set to The Smurfs movie.
            * This can be tested by going to [https://www.themoviedb.org/movie/41513](https://www.themoviedb.org/movie/41513).
            * With that in mind, search for your favorite superhero movie on the database and copy the ID found in the URL and replace The Smurfs ID (41513) in the API request URL.
        * NOTE: This is a small issue that may have been easily overlooked. I consider this issue a bit unfair, so if you didn't notice it, don't worry at all! It is here to remind you that while everything may work, you may still miss small details when shipping code. (I noticed a couple typos in the Unit 01 solutions README a whole week after it was committed/pushed...)
  5. Movie Details does not segue correctly.
        * <img src="https://github.com/yujioshiro/iOS-Debugging-Challenges/blob/main/Solutions%20Assets/Unit%2002/Movie%20Details%20Segue.gif" alt="gif showing how to adjust segue from 'Show Details' kind to 'Show'" width="960">
        * This is another issue that may have been easily overlooked as it isn't exactly incorrect or a "bug" but, as above, it is important that we don't miss any details when building our apps.

</details>

**I believe this week's challenge can be improved immensely. If you have any ideas to improve the challenge for the week, feel free to fork and submit a pull request with explanation!*
