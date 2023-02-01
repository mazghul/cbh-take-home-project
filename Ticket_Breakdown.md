# Ticket Breakdown
We are a staffing company whose primary purpose is to book Agents at Shifts posted by Facilities on our platform. We're working on a new feature which will generate reports for our client Facilities containing info on how many hours each Agent worked in a given quarter by summing up every Shift they worked. Currently, this is how the process works:

- Data is saved in the database in the Facilities, Agents, and Shifts tables
- A function `getShiftsByFacility` is called with the Facility's id, returning all Shifts worked that quarter, including some metadata about the Agent assigned to each
- A function `generateReport` is then called with the list of Shifts. It converts them into a PDF which can be submitted by the Facility for compliance.

## You've been asked to work on a ticket. It reads:

**Currently, the id of each Agent on the reports we generate is their internal database id. We'd like to add the ability for Facilities to save their own custom ids for each Agent they work with and use that id when generating reports for them.**


Based on the information given, break this ticket down into 2-5 individual tickets to perform. Provide as much detail for each ticket as you can, including acceptance criteria, time/effort estimates, and implementation details. Feel free to make informed guesses about any unknown details - you can't guess "wrong".


You will be graded on the level of detail in each ticket, the clarity of the execution plan within and between tickets, and the intelligibility of your language. You don't need to be a native English speaker, but please proof-read your work.

## Your Breakdown Here

## Create an EPIC and tag it to all tickets.

Task 1: 

### Add custom id field for Agents

Acceptance Criteria:
- A new field for custom id should be added to the Agents table in the database
- The custom id field should be able to be populated and saved by Facilities
- The custom id field should be retrievable when querying for Agent data
 
Implementation Details:

- Create a new column in the Agents table in the database to store the custom id using migration
- Update the model for the Agents table to include the custom id field.
- Update the Agents controller to include the custom id field in the responses for querying Agent data.

Estimated Time/Effort: 4 hours

Task 2:

### Create a function to save customId with Facility's id

Acceptance Criteria:
- There should be a function to add customId for the agents using Facility's id

Implementation Details:

- Create a function which takes in two params Facility's id and customId and update customId to the facility

Estimated Time/Effort: 2 hours

Task 3: 

### Update getShiftsByFacility function to return custom id

Acceptance Criteria:
- The getShiftsByFacility function should return the custom id of the Agent along with the other metadata

Implementation Details:

- Update the response format for the getShiftsByFacility function to include the custom id of the Agent.
- Test the getShiftsByFacility function to ensure the custom id is being returned correctly

Estimated Time/Effort: 1 hour

Task 4:

### Use custom id in generateReport function

Acceptance Criteria:
- The generateReport function should use the custom id of the Agent instead of their internal database id
- The custom id should be used in the PDF that is generated and submitted by the Facility

Implementation Details:

- Update the generateReport function to use the custom id of the Agent instead of their internal database id
- Update the PDF template to include the custom id of the Agent
- Test the generateReport function to ensure the custom id is being used correctly and the PDF is being generated correctly

Estimated Time/Effort: 4 hours

Task 5:

### Updating existing records.

Acceptance Criteria:
- Able to add customId for all the existing Agents

Implementation Details:

- Create a migration script which will update customId for all the agents with the given customId to facilityId mapping list.
- Take a backup of the database before running the script in production.

Estimated Time/Effort: 4 hours
