---
title: Stream Attribution
order: 2017-10
thumbnail: user_journey/user_journey_thumb@2x.png
client: Spotify
abstract: >-
  A tool for exploring the paths users take through Spotify's clients to find something to stream.
---

![A mockup of the visualization of user journeys]({{ "assets/img/user_journey/journeys.png" | relative_url }})

<aside class="disclaimer">These images are mockups and contain no actual data.</aside>

This is a tool for data scientists, product owners, and designers to explore how users on Spotify navigate the various clients to find something to stream. It provides both a high level summary of how many streams can be attributed to any page, and a detailed view of steps taken by users to reach a stream. The application helps users understand how our clients are used so that they can make better product decisions.

![A mockup of the summary for a single page in the client]({{ "assets/img/user_journey/summary.png" | relative_url}})

## Process

### Data First

Our process in the Data Mission at Spotify is a balance of data-first and user-centered. In this case, we had a new data set that opened up new possibilities for decision-making in our product organization. So rather than beginning with interviews, I began by exploring the data in Tableau and created a dashboard to see what kinds of potential I could find in the data. We then shared this prototype with some of our users to elicit feedback about how useful the data was in its current form and what was missing from the data that would make it more useful.

### Interviews

That first Tableau prototype gave us something concrete to discuss with users and helped us gauge the potential value of this data to our target users. For the next phase, I spent several days in Stockholm—where most of our client development teams are located—interviewing data scientists, product owners, and designers. At the same time, I was meeting with a data scientist who was adding more semantic layers to the data that we could use to help address the needs that he and I had (independently) identified among product owners and designers.

### Prototype &c.

Following my user research in Stockholm, I began prototyping visualizations of the data using D3 (we had reached the limit of what Tableau could accomplish) and working with another designer on our team to build a prototype of the application. We spent several weeks testing and iterating on the prototype as we hammered out the user experience. After that was done, I began designing version 1.0 of the application (pictured above) using Spotify's design system.
