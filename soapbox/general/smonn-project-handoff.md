# Project handoff guide

📝 By [Simon][smonn]

Also known as: knowledge transfer guide

---

We strive to make sure that when we handoff software, it's smooth and dare we say it, pleasurable for a client team to take over.

These are some tips on things to go through with new engineers on projects. This would be to either onboard or handover projects as you transition out of them. This list is not exhaustive and you will probably have specific things to cover in your project based on circumstances.

Depending on the circumstances you may or may not have someone to share your knowledge with before you're off the project. This is why it's so important to document all your knowledge in the project's README file. Or at least have it link to other places where they can find the required information.

## Short version

This is in order of importance. README is considered mandatory, review meeting should ideally be done, and everything else is sugar on top.

1. Knowledge dump in project README
2. Review meeting with new engineer and/or client
3. Document known issues and areas of improvement
4. For large projects, optionally maintain an internal [Tettra][tettra] wiki page

## Long version

### 1. Knowledge dump in project README

Ensure the project's README covers everything they will need. Bonus points to keep it organized and tidy! It can be helpful for you to go through the setup steps on your own in an empty folder to make sure the steps are thorough. And once you're happy, have the new engineer go through it on their own to provide feedback. You can include things like:

- How to setup your local environment for development.
- How to deploy to and access various environments.
- Links to relevant resources. For example: more detailed documentation, design assets, project ticket board, etc.

  - Who to contact to help with various topics, such as devops, data ingestion, product owner
  - Add a "feel free contact me" with your Dept email address (if you're comfortable with it)

### 2. Review meeting with new engineer and/or client

Setup a review meeting well in advance of you transferring off. Invite the right people to it. Record the meeting and then upload it for the client or new engineer to keep.

#### For front-end projects:

- Demonstrate each view (if possible)
- Highlight API integration points
- Point out high level modules/components
- Dive deeper into code for more complex sections

#### For back-end projects:

- Show and explain the data model
- Show how to manually run various scripts (such as ETL jobs)
- Answer any questions that may come up, and document anything that can't directly be addressed in the README or the client's ticket system (i.e. Jira).

### 3. Document known issues and areas of improvement

Assemble a document with any outstanding known issues or tasks that you think should be addressed as soon as possible. While a backlog may contain this information to some extent, having a single document to refer to as an overview can be helpful and highlight what you think is important as the engineer.

### 4. For large projects, optionally maintain an internal Tettra wiki page

For larger clients/projects where multiple Dept engineers spend their time, it might be beneficial to add a private [Tettra][tettra] wiki page to document any specifics and link to people of interest (LinkedIn/GitHub/etc).

[smonn]: https://github.com/smonn
[tettra]: https://app.tettra.co/teams/rocketinsights
