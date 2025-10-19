# Relisten Android Application

## TDA / ACM Collaboration

I talked to the Rahdyce (ACM Pres). I mentioned doing this project as part of the TDA / ACM collaboration. I think that the advantage
is that we would have "sprints" where we would **have** to work on the app. All of us know programming fundamentals. Therefore, all of us
are capable of building this app, and the biggest roadblock is our not investing time into its completion.

[TDA / ACM Collaboration Discord Server Link](https://discord.gg/ZBbnnvs6)

## Overview

This app is an Android client for [Relisten](https://relisten.net/). 
The Swagger link for their API docs is: [Relisten API Docs](https://api.relisten.net/api-docs/index.html). This app will be written in
Kotlin. Kotlin is very similar to Java. If you haven't worked with Kotlin before, a YouTube search for "Kotlin for Java Developers"
will get you up to speed.

## Android Development Basics

Android Development is most commonly done in the Android Studio IDE. This IDE is a fork of JetBrains IntelliJ IDEA.
It has everything you need to run an Android application, including emulators.

Emulators are very useful for running and testing Android applications. Samsung modifies the Android source code, so it's usually
a good idea to run it on some Samsung physical devices. Sometimes the user interface may load slightly differently.

### User Interfaces

There are two ways to code a user interface in Android development. The first is with XML. This is similar to HTML and CSS.
The other way is with Jetpack Compose. With Jetpack Compose, you code layouts using Kotlin. 

[Philipp Lackner - Jetpack Compose Tutorial](https://www.youtube.com/watch?v=6_wK_Ud8--0)

### Architecture

[Philipp Lackner - MVVM in 100 Seconds](https://www.youtube.com/watch?v=-xTqfilaYow)

To provide context on the above link, the Activity class will be the class that interacts with the view. Let's say when a client clicks on a button to open an Artist's page. You would add an "onClickListener" to the button (inside the ArtistsActivity class).
When that button is clicked, the view would trigger some code in the Activity (i.e., a method) to call the next Activity (the Artists screen). The artist screen's Activity
would load the `onResume()` method (where you should almost always put code that needs to run when an Activity is opened, for the first time or reopened subsequently), which would presumably call a method in the viewModel, which would presumably call a method in the repository, which would query the data from
the database, and also cache the latest API call to the database. I've posted a video on observable classes below - the only one I've worked with is live data. 

It is pretty common for an app to make a call to an API endpoint and to cache the data locally in the database (SQLite / Room). The app will query the
database for the data that it needs and store it in a variable with a class type of what they call "Live Data". If the data has been changed (an API call returns a different value than what the DB query returned), it will update in the view. In the Activity, you use an Observer pattern, which just
"observes" the variable, and if it changes (i.e., as mentioned earlier, an API call caches a different value to the DB), the DB will update that variable, and inside the observer pattern, your view will update with the latest value without you having to write any additional logic to do that.


>[!NOTE]
>It is not necessary to always have a repository. I'm not the best Android developer; I haven't specialized in anything, but my judgment tells me that
We should use an actual Repository, and maybe even have a separate repository for each Model, simply for separating "unrelated" objects (i.e. `ArtistsRepository`, `YearsByArtistRepository`, `ShowsByArtistRepository` - I haven't thought this out yet, but I think it's worth discussing)

[Android Docs - Architecture](https://developer.android.com/topic/architecture)

### Activities

Views in Android are typically "Activities" or "Fragments". You need at least one activity, and you can have one or more fragments for
each activity. For simplicity, I think every view should be coded as an activity. If we learn the Activity lifecycle, we have a pretty functional understanding of how we could code an Android app using Activities.

[Philipp Lackner - Activity Lifecycle](https://www.youtube.com/watch?v=SJw3Nu_h8kk)

[Android Official Docs - Activity Lifecycle](https://developer.android.com/guide/components/activities/activity-lifecycle) is

### Dependency Injection (Hilt / Dagger)

This is completely optional.

[Dependancy Injection (High Level Overview)](https://www.youtube.com/watch?v=tYZd8hserms)

[Philipp Lackner - Dagger / Hilt](https://www.youtube.com/watch?v=bbMsuI2p1DQ)

### Testing

[Philipp Lackner - Android Testing](https://www.youtube.com/watch?v=nDCCwyS0_MQ)

### Retrofit API library 

Retrofit is the library commonly used for API calls.

[Philipp Lackner - Retrofit](https://www.youtube.com/watch?v=t6Sql3WMAnk)

### Room ORM

Room is the ORM to interact with SQLite. It integrates with LiveData, which is a pretty convenient way to make sure your view contains
the latest values. I describe this a little below.

[Philipp Lackner - Room ORM](https://www.youtube.com/watch?v=bOd3wO0uFr8)

### Observable Classes

[Philipp Lackner - Observable Classes](https://www.youtube.com/watch?v=6Jc6-INantQ)

^ I have only worked with LiveData. The above video should help us pick an Observable Class that is best for our needs.

### Background Tasks

`WorkManager` is the "new" way to do background tasks. I don't know if we would specifically use this, unless we wanted to update the cache.

If memory serves me right, Android has foreground services and background services. I think that we would need a foreground service (and I think that a foreground service opens a notification).
This needs to be confirmed because I don't remember it. If we look at the `UAMP` app below, it should be a good resource.

## Practical

The below is a list of things we should do:

- Come up with the number of Activities based on the iOS Relisten app (i.e. ArtistsActivity). This will be done by simply looking at the iOS client's screens. I'm planning on doing this over the next week. 
- Come up with the number of repositories (this will be a class that will query the database and API, as discussed above, caching the latest API call to the database). We could really get away with one, but if we want to try and make things "Cleaner" and have multiple ones to coincide with models, we could do that too
- Decide UX tech - my vote is for Jetpack Compose, because I don't know it yet, and it is established by now and becoming pretty common. 
- Decide whether to use Dagger / Hilt, dependency injection. To keep things simpler, we could leave this out.
- See who wants to work on what - I'm planning on working on the views Jetpack Compose, if anyone wants to join me, that would be great
  - I'm planning on creating an Activity for each screen based on an agreement (once I go through the app and write those out). Once that is done, I will start coding the views, and probably put dummy data there for now.
- If some people want to handle the API call with `Retrofit`, that would be great 
- If some people want to handle the Model using the `Room ORM`, that would be great
- Decide which Observable Class to use based on Philipp Lackner's video on Observable Classes

Please let me know what each of you wants to do, and we can try and plan this out over the next week.

Obviously, we should run the Relisten iOS app. If you are on Android but you have a Mac with Apple processors, it will run on that. I am planning on taking screenshots
of the Relisten iOS app, and writing out potential Activities (As mentioned above)

## UAMP

[UAMP](https://github.com/android/uamp/blob/main/docs%2FFullGuide.md) is an older demo that illustrates how to create a music streaming app using
Kotlin. It hasn't received updates in a while, but it should still be a good reference.

## TODO
- provide screenshots and potential activities
- provide docs on how to create a pull request
- fork existing repo or create a new repo
- update TDA / ACM calendar with our team

