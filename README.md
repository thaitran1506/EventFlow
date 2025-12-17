# EventFlow
This repository contains the source code for EventFlow, an Android mobile application developed as part of a comprehensive course project. The goal of this document is to outline the app's purpose, design philosophy, technical implementation, and the key learnings from its development cycle.1. 

1. Application Requirements and User NeedsEventFlow was designed to address a simple but common user need: to have a reliable and straightforward way to remember important events. In a world of crowded digital calendars and easy-to-miss push notifications, users need a more direct reminder system.The core requirements and goals of the app were:
   •Create and Manage Events: Allow users to create events with a name, date, time, and description.
   •Secure User Accounts: Ensure users have a personal, secure space to manage their events through a login system.
   •Provide Timely Reminders: The app's key feature is to send an SMS notification at the time of the event, ensuring the reminder is immediate and         highly visible.
   •Offer a Clean, Modern Interface: The application must be intuitive, fast, and easy to navigate.

2. UI/UX Design and FeaturesTo support the user needs, a user-centered UI was created with several key screens and features. My design approach prioritized clarity, intuitive navigation, and direct user feedback.
   •Key Screens:
     i.Login/Sign-up Screen: A secure and simple entry point for users.
     ii.Events List Screen: An at-a-glance view of all upcoming events, designed for quick reference.
     iii.Add Event Screen: A straightforward form for creating or editing an event.
     iv.SMS Permission Screen: A dedicated screen that respectfully explains why the SEND_SMS permission is critical for the app's core functionality,      building user trust.
   •User-Centered Design Philosophy: My designs kept the user in mind by focusing on reducing cognitive load. For example, the events list was changed     from a cluttered grid to a clean, single-column list, making it easier to read on any device. On the login screen, I implemented contextual error      messages using TextInputLayout. Instead of a generic "Invalid Input" toast message, the UI now tells the user exactly which field is incorrect         (e.g., "Username is required").
   •Why the Designs Were Successful: The UI designs were successful because they are predictable and communicative. By using standard Android patterns     like the Floating Action Button (FAB) for adding events and providing clear, inline validation, users don't have to guess what to do next. The         interface guides them, leading to a more efficient and less frustrating experience.

3. Coding Approach and Strategies
   My approach to coding was iterative and refactoring-focused. I started with a functional baseline and systematically improved it, one component at     a time, ensuring that the UI (XML) and the business logic (Java) remained in sync.
   •Techniques Used:
     ◦Model-View-Adapter Pattern: Used RecyclerView and EventAdapter to efficiently display a dynamic list of events, separating the data (Event             model) from the view logic.
     ◦Database Abstraction: A DatabaseHelper class was used to encapsulate all SQLite database operations, keeping SQL logic separate from the               application's activities.
     ◦Explicit Intent Navigation: Used Intent objects for clear, predictable navigation between the app's activities.
   •Future Application: These foundational techniques are essential for any Android developer. In the future, I would enhance this approach by             integrating modern architectural components like ViewModel to better handle lifecycle events and configuration changes, and ViewBinding to create      compile-time safe references to views, completely eliminating findViewById and its associated risks.

4. Functional Testing
   To ensure the code was functional, I primarily used manual, user-centric testing. This process is crucial because it validates the app not just from a technical perspective but from the user's point of view.
   •Process: After each significant change, I would run the app and test the affected user flow. For example, when the app began crashing after a UI update, I didn't just read the crash log. I retraced the user's steps (Login -> View Events). This led me to hypothesize that the crash was related to the RecyclerView's item layout.
   •What Testing Revealed: This process was vital. It revealed a critical bug where the EventAdapter.java file was trying to find a MaterialButton that had been changed to an ImageButton in the XML layout. This runtime crash highlighted the fragility of relying solely on findViewById and underscored the importance of thorough testing after every code modification, no matter how small.

   5. Innovation and Challenge Resolution
      The most significant challenge was modernizing the app's user experience without a complete rewrite. The app was functional, but it didn't feel polished.My innovation was in the systematic enhancement of the user feedback loop. The best example was on the Login screen. Instead of just fixing bugs, I asked how I could make the experience better. The solution was to replace disruptive Toast messages with integrated, contextual error messages within the TextInputLayout. This small change had a massive impact on the app's professional feel and usability. It was an innovative solution that solved the challenge of making the app feel more modern and responsive.
  
  6. Demonstration of Knowledge, Skills, and Experience
     I believe my knowledge and skills were best demonstrated in the final implementation of the Login screen (MainActivity.java and activity_main.xml).
     This single component showcases a wide range of essential Android development skills:
     •Advanced UI Design: Structuring a clean, responsive layout using a combination of ConstraintLayout, LinearLayout, and modern Material Design Components.
     •User-Centric Development: Implementing an intuitive and forgiving validation system that provides clear, inline error messages.
     •Java and Android SDK: Writing clean Java code to handle user input, interact with the database helper, and manage the activity lifecycle.
     •Problem Solving: Evolving the screen from a basic form to a sophisticated and robust entry point that reflects modern best practices.This component successfully combines UI design, application logic, and user experience principles, demonstrating a holistic understanding of the mobile app development process.
      
