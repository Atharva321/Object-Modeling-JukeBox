# ME_OBJECT_MODELING
<h2>Object Modeling</h2>

<p>Overview There is a lot of research and development effort that goes into building enterprise software that serves the customers in achieving their business goals. There are certain techniques to be followed to build the software iteratively and adapt to the changing requirements of the end users. This is where good low-level design architecture helps.</p>

<p>During the course of this project,</p>

<ul>
	<li>Understood the implementation of the Movie booking problem implementation.</li>
	<li>Designed &amp; implemented the classes required for a contest framework.</li>
	<li>Implemented the business logic of running a simulated contest.</li>
	<li>Built a Jukebox application based on a problem statement from scratch.</li>
	<li>Clean Architecture</li>
</ul>

<h3>Introduction to Low Level Design</h3>

<p>Scope of Work</p>

<ul>
	<li>Get introduced to the components of Clean Architecture.</li>
	<li>Understand entities and identify them with the help of real-world examples.</li>
	<li>Gather requirements and translate them into use cases.</li>
	<li>Understand the need for a datastore.</li>
</ul>

<p>Skills used: Clean Architecture</p>

<h1>Components of Clean Architecture</h1>

<h2>Identify relationships between entities</h2>

<p>Scope of Work</p>

<p>Explore different types of class relationships and their purpose. Discover relationships for different scenarios and draw an object diagram. Understand the provided Object Relationship Diagram of Movie Booking Problem statement. Understand the CodingGame problem statement. Draw Use Case and Object Diagram for the given scenarios Skills used: Object-Oriented Design</p>

<h3>Implement Entities</h3>

<p>Scope of Work</p>

<p>Understand the entities of the provided implementation of Movie Booking Problem statement. For CodingGame Problem Statement Implement entities with the identified attributes and their behaviour. Implement the relationship between the entities Write good quality tests for entitles, which cover all the relevant behaviour. Skills used: Java, Unit Testing, Test Driven Development</p>

<h3>Implement Services and Repositories</h3>

<p>Scope of Work</p>

<p>Understood the services &amp; repositories layer of the provided implementation of Movie Booking Problem Statement. Implemented services &amp; repositories layer of CodingGame adhering to the SOLID principles. Followed Test Driven Development to ensure correctness and better code coverage. Skills used Java, Unit Testing, Test Driven Development, Design Patterns, SOLID Principles</p>

<h3>Implement Commands and finish up the Project</h3>

<p>Scope of Work</p>

<p>Understand the controller layer of the provided implementation of the Movie Booking Problem Statement. Implement all the required commands in the controller layer for the CodingGame problem statement using Test Driven Development. Skills used Java,Unit Testing, Test Driven Development, Design Patterns, SOLID Principles</p>

<h1>Implement Jukebox from Scratch Scope of Work</h1>

<p>Clearly understand the Problem Statement Requirements. Identify the Primary Use Cases / Behaviour of the system. Identify the Key Objects / Entities from the listed use cases. Identify the behaviours / supported operations for Identified objects. Identify Interactions between the entities (Class Relationships). Implement all the required layers embracing the clean architecture style. Implement all the required layers step by step in a Test-driven development style to ensure correctness and better code coverage.</p>

<p>Skills used: Java, Object-Oriented Design, Design Patterns, Test Driven Development, Unit Testing</p>

# Jukebox

Jukebox is a command line-based music player that allows user to create, manage playlists and play songs from playlists.

## Functional Requirements

* A user can create a playlist from a pool of available songs.
* A user can delete a playlist.
* A user can add / delete songs from the playlist.
* A user can start playing songs by choosing a playlist. On choosing a playlist, the first song in the playlist will start playing.
* A user can switch songs by using Next, Back command or by choosing another song from the playlist that has been chosen.
  1. On reaching the end, Next will switch to the first song in the current playlist.
  2. On reaching the start, Back will switch to the last song in the playlist.
* Only one song can be played at a time.
* A user can choose to play the song from another playlist if and only if that playlist is selected. Basically two operations have to be done to successfully play the song of their choice.
  1. Select the playlist ( which will play the first song when selected )
  2. Choose the song of your choice.
* An album is a collection of songs owned by the original artist / artist group .
Artist Group Example:- One Direction.
One Direction Group is the album owner and is considered as an artist.
* Each song can feature multiple artists but it will be owned by the artist whose album this song belongs to.
* Each song can only be a part of one album.

## Commands
The following commands are supported by the application:

* `LOAD-DATA {input_file}`: Load songs from a CSV file into the Song repository.
* `CREATE-USER {name}`: Create a new user in the system.
* `CREATE-PLAYLIST {user_id} {playlist_name} {song_ids}`: Create a new playlist with the given songs.
* `DELETE-PLAYLIST {user_id} {playlist_id}`: Delete a playlist with the specified ID.
* `MODIFY-PLAYLIST ADD-SONG {user_id} {playlist_id} {song_ids}`: Add songs to an existing playlist.
* `MODIFY-PLAYLIST DELETE-SONG {user_id} {playlist_id} {song_ids}`: Delete songs from an existing playlist.
* `PLAY-PLAYLIST {user_id} {playlist_id}`: Start playing the selected playlist.
* `PLAY-SONG {user_id} BACK`: Switch to the previous song in the active playlist.
* `PLAY-SONG {user_id} NEXT`: Switch to the next song in the active playlist.
* `PLAY-SONG {user_id} {song_id}`: Switch to the preferred song in the active playlist.

## Implementation
The application follows **SOLID Principles** and a modular layered **Clean Architecture** with the following key components:
Models - Plain Java objects for entities like Song, Playlist, User etc.

* **Repositories** - Data access objects that handle data persistence. Repository abstracts the Data Store and enables your business logic to define read and write operations at a logical level.

* **Services** - Business logic layer, encapsulate and implement all the approved use cases for the application.

* **Command Handlers** - Logic to parse input and execute relevant services

* **Command Runner** - Main entry point to read input and invoke relevant handlers
