# Android 5.4 Comprehensive Technical Assessment (CTA)

## Table of Contents
* [Project Specifications](#project-specifications)
* [Comprehensive Technical Assessment MVP Checklist Requirements](#comprehensive-technical-assessment-mvp-checklist-requirements)
* [Github / Project Setup](#github--project-setup)
* [Android Instructional Staff Github Handles](#android-instructional-staff-github-handles)
* [Screenshots](#screenshots)

## Project Specifications

The goal of this assessment is to evaluate the problem solving skills, UX judgement, and code
quality of Android Fellows.

Here [at this endpoint](https://raw.githubusercontent.com/joinpursuit/Pursuit-Core-Android-Unit6-CTA-Bank-Locator/master/location.json), we have a list of cities containing around 250 entries in JSON format. Each entry contains information like the following:

``` json
{
  "country":"UA",
  "name":"Hurzuf", 
  "_id":707860,
  "coord":{
    "lon":34.283333,
    "lat":44.549999
  }
}
```

Your task is to:
* Display a list of cities on a scrollable list in alphabetical order (city first, country after)
* `Denver, US` should appear before, `Sydney, Australia`
* `Anaheim, US` should appear before `Denver, US`
* Be able to filter the results by a given prefix string, over the city name
* Selecting a city will show a map centered on the coordinates associated with the city
* You should optimize for fast searches, however, loading time of the app is not a concern

We define a prefix string as: a substring that matches the initial characters of the target
string. For instance, assume the following entries:

* Alabama, US
* Albuquerque, US
* Anaheim, US
* Arizona, US
* Sydney, AU

If the given prefix is `A`, all cities **EXCEPT** Sydney should appear. Inversely, if the given prefix is
`s`, the **ONLY** result should be `Sydney, AU`. If the given prefix is `Al`, `Alabama, US` and
`Albuquerque, US` are the only results. If the prefix given is `Alb` then the only result is
`Albuquerque, US`.

Additional requirements/restrictions:

* The list will be provided to you as a plain text JSON format array via a JSON endpoint.
* The UI should be as responsive as possible while typing a filter.
* The list should be updated with every character added/removed to the filter.
* Database implementations are **FORBIDDEN**
* Provide two (2) unit tests, to confirm that your sorting algorithm is displaying the correct results given different inputs, including invalid inputs
* UI has to be implemented using one (1) activity with multiple fragments
* The code of the assessment has to be delivered along with the git repository (.git folder). We want to see the progress evolution

## Comprehensive Technical Assessment MVP Checklist Requirements:

MVP for this app is considered reached when the fellow...

- [ ] can create a single Activity with a Fragment Host container Layout within its UI
- [ ] can wrap Retrofit instance in a singleton
- [ ] can connect to JSON endpoint using Retrofit2 instance
- [ ] can deserialize JSON data using GSON and data Model classes
- [ ] can account for slow data loading response with a loading dialog / animation in the UI
- [ ] can account for a failed data response with a Toast or Snackbar message
- [ ] can sort the response data effectively using a class composed by the fellow 
- [ ] can send sorted data to a Fragment using a Static Factory Instance method
- [ ] can display said Fragment, and include a SearchView and RecyclerView in the Fragment's UI
- [ ] can display the City Name, and City Country Code of each object within each RecyclerView itemview - i.e. `New York, US`
- [ ] can filter data displayed in the RecyclerView based on the characters added or removed from the SearchView input based on City Name
- [ ] can make each itemview respond to click events
- [ ] can send lat/long data for each city clicked, back to the Activity from the Fragment using interface listener callback  methods
- [ ] can send that lat/lon data from the Activity to a new Fragment using a Static Factory Instance method
- [ ] can implement a MapFragment, using the Google Maps API ([get API Key here](https://console.cloud.google.com/home/dashboard))
- [ ] can display the lat/lon data passed to the Fragment as a pin marker, labeled with the City Name, and Country Code Abbreviation
- [ ] can display the pin within the center of the screen, pre-zoomed within the radius of the country's visible borders
- [ ] can return back to the previous Fragment using the back button
- [ ] can account for orientation changes within the app using either SavedInstanceState, or multiple layouts
- [ ] can add two JUnit tests to their project

## Github / Project Setup

* Create a private repo on Github
* Invite the Android instructional staff as collaborators to your repo
* Create an Android Studio project
* Create a `README.md` file in the root folder of your project
* Add a link to this repo on your `README.md`
* Initialize a git repository locally for your Android Studio Project
* Add your remote Github repository to your local repository
* Push to master (only once) as an initial Commit
* Create a "dev-yourname" branch, i.e. - `dev-josevila`, so you can make pull requests against "master" when needed: `git checkout -b dev-josevila`
* Push your dev branch to remote, i.e. - `git push --set-upstream origin dev-josevila`
* We will be monitoring your commits as a way to avoid inconsitencies and educational integrity with your work, please commit regularly (at least 3 - 5 commits per day at minimum)
* You can make your first pull request against "master" as early as **Friday 04/19/2019 at 12:00pm** to be reviewed by the instructional staff (only when MVP is met) - the latest day to make your first pull request is **Saturday 04/20/2019 at 12:00pm**
* Only after your PR (pull request) has been approved by an instructional staff member will it then be merged to the `master` branch
* You are required to be in class throughout this week while working on this assessment
* Your final pull request should be made on Wednesday 04/24/2019 (due date of the assessment)

## Android Instructional Staff Github Handles
* Jose Vila: @jdvila
* Rusi Li: @rusili
* Bryant Ramirez: @mbryantramirez

## Making a Pull Request
* Choose your dev branch and compare with the master branch
* Create the pull request
* Leave a message and tag @jdvila, @rusili, and @mbryantramirez on the pull request

## Screenshots

![loading](https://github.com/joinpursuit/Pursuit-Core-Android-Unit6-CTA-Bank-Locator/blob/master/images/load.png)
<br><br>
![sorted](https://github.com/joinpursuit/Pursuit-Core-Android-Unit6-CTA-Bank-Locator/blob/master/images/sort.png)
<br><br>
![search](https://github.com/joinpursuit/Pursuit-Core-Android-Unit6-CTA-Bank-Locator/blob/master/images/search.png)
<br><br>
![map](https://github.com/joinpursuit/Pursuit-Core-Android-Unit6-CTA-Bank-Locator/blob/master/images/map.png)
