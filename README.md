# Georgia Southern - TDA / ACM Collaboration
## Team: You Deploy Myself; App - Weatherly: An Android Weather app with Offline Functionality

### TDA / ACM Collaboration

I talked to the Rahdyce (ACM Pres). I mentioned doing this project as part of the TDA / ACM collaboration. I think that the advantage
is that we would have "sprints" where we would **have** to work on the app. All of us know programming fundamentals. Therefore, all of us
are capable of building this app, and the biggest roadblock is our not investing time into its completion.

We're going to make this app as simple as possible. No dependency injection (it's not as intuitive). I'm happy to write the Boilerplate code for Retrofit and Room (I have worked with these before). 

[TDA / ACM Collaboration Discord Server Link](https://discord.gg/ZBbnnvs6)

### Overview

This app retrieves weather forecast data from an API using the [Retrofit Library](https://square.github.io/retrofit/). It caches it locally in a SQLite database powered by the [Room ORM](https://developer.android.com/training/data-storage/room);

## Android Development Basics

Android Development is most commonly done in the Android Studio IDE. This IDE is a fork of JetBrains IntelliJ IDEA.
It has everything you need to run an Android application, including emulators.

Emulators are very useful for running and testing Android applications. Samsung modifies the Android source code, so it's usually
a good idea to run it on some Samsung physical devices. Sometimes the user interface may load slightly differently.

### User Interfaces

There are two ways to code a user interface in Android development. The first is with XML. This is similar to HTML and CSS.
The other way is with Jetpack Compose. With Jetpack Compose, you code layouts using Kotlin. 

We're going to use XML to get this done as quickly as possible, but if you enjoy Android development, go through the Jetpack Compose course below.

[Philipp Lackner - Jetpack Compose Tutorial](https://www.youtube.com/watch?v=6_wK_Ud8--0)

### Architecture

[Philipp Lackner - MVVM in 100 Seconds](https://www.youtube.com/watch?v=-xTqfilaYow)

We're going to use Model View Viewmodel, with a Repository. I will plan this out more on Sunday.

>[!NOTE]
>It is not necessary to always have a repository. I'm not the best Android developer; I haven't specialized in it to be extremely knowledgeable, but my judgment tells me that
We should use an actual Repository, and maybe even have a separate repository for each Model, simply for separating "unique" objects (i.e. `ArtistsRepository`, `YearsByArtistRepository`, `ShowsByArtistRepository` - I haven't thought this out yet, but I think it's worth discussing). Each class, from the Activity to the Repository can get cluttered.

[Android Docs - Architecture](https://developer.android.com/topic/architecture)

### Activities

Views in Android are typically "Activities" or "Fragments". You need at least one activity, and you can have one or more fragments for
each activity. For simplicity, I think every view should be coded as an activity. If we learn the Activity lifecycle, we have a pretty functional understanding of how we could code an Android app using Activities.

[Philipp Lackner - Activity Lifecycle](https://www.youtube.com/watch?v=SJw3Nu_h8kk)

[Android Official Docs - Activity Lifecycle](https://developer.android.com/guide/components/activities/activity-lifecycle) is

### Dependency Injection (Hilt / Dagger)

We are not using this, but it is a good thing to learn if you want to do Android Development. 

[Dependancy Injection (High Level Overview)](https://www.youtube.com/watch?v=tYZd8hserms)

[Philipp Lackner - Dagger / Hilt](https://www.youtube.com/watch?v=bbMsuI2p1DQ)

### Testing

[Philipp Lackner - Android Testing](https://www.youtube.com/watch?v=nDCCwyS0_MQ)

### Retrofit API library 

Retrofit is the library commonly used for API calls, at least for REST API calls. 

[Philipp Lackner - Retrofit](https://www.youtube.com/watch?v=t6Sql3WMAnk)

### Room ORM

Room is the ORM to interact with SQLite. It integrates with LiveData, which is a pretty convenient way to make sure your view contains
the latest values. 

[Philipp Lackner - Room ORM](https://www.youtube.com/watch?v=bOd3wO0uFr8)

### Observable Classes

[Philipp Lackner - Observable Classes](https://www.youtube.com/watch?v=6Jc6-INantQ)

^ I have only worked with LiveData. We're going to use LiveData for the app, but the above video should give an overview of different Observable classes.

### Background Tasks

We will need to make API calls periodically and store them in the cache. I believe that WorkManger is the appropriate way to do this in the background.

## Practical

Below is a list of things we should do:

- This will be updated shortly.

I'

## Postman

[Postman Tutorial](https://www.youtube.com/watch?v=CLG0ha_a0q8) - Postman is commonly used when you need to make API calls. It's based on Chrome, and it allows you to enter the API information, then it loads the response (typically JSON) in the program. All of us should have a good understanding of the API service I use, so we should run it in Postman.

## TODO
- fill this out

