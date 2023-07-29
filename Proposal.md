# What makes your Team best-suited to execute this Mission?
Here are our team members and their best projects and contributions highligthing their area of expertise:
    




# Question: Please describe your proposed solution based on the above Solution Criteria (if applicable):

### Project Discovery Feature:
    - For implementing the desired searching, sorting, and filtering functionalities, we are planning to use open-source search engines such as Apache Solr or Elasticsearch in the backend. These search engines offer robust full-text search capabilities, efficient sorting, and flexible filtering options for varoius tags, making them ideal choices to handle project discovery in the RetroPGF 3 application.

    - In the frontend, React.js will be used to create drop down options, toggles etc as shown in the wireframe and seemless integration with the backend will be done.

### Viewing a Project's Profile Feature:
    - React.js will be used to build the exact profile viewing page as provided in the wireframe.
    - Dedicated API routes to fetch the data from the database about each project and populate the frontend page.
    - Ethereum Attestation Service (EAS) to query existing onchain information relating to entities, their RetroPGF 3 application, and social verifications
    - Relevant tags on every project profile making it easily discoverable through searching, filtering and sorting functionalities.

### Discovering and voting on Lists Feature:
    - Making dedicated REST-API routes for badgeholders to create lists which are discoverable and many other list related functionalities.

    - Here are the exact API routes for every list related functionality:
          - POST request -\api\list\createlist : this post request route will take the name, description, creator name and projects in the body to declare a list which will be added to thier ballot.
          - PUT request - \api\list\updatelist : this request will be used to further add more projects to the list or delete project by the creator.
          - POST request - \api\list\copylist : this request will add a list published by a badgeholder into the copier's ballot to be updated and used by badgeholder.
          - DELETE request - \api\list\deletelist : this request will delete an entire list or a copy of a list if the badgeholder is not satisfied with list.

    - Frontend: Building the exact frontend as shown in the wireframe for lists which will be highly responsive, smooth and user friendly.

## Architecure and implementation to allocate votes:
    - Database Schema: A no-sql schema is preffered choice according to us for this project, however we are still very comfortable and confident if any partiular schema or databse has already been selected. Here is an example schema which can be used to store all the voting information:
        Project Collection:
        ```
         {
            "_id": "project_id_1",
            "name": "Project 1",
            "description": "This is the description of Project 1.",
            "creator": "Creator's Name",
            "profilePicture": "url_to_profile_picture",
            "socialMediaLinks": {
              "twitter": "twitter_handle",
              "github": "github_username"
            },
            "contributions": ["contribution_1", "contribution_2", "contribution_3"],
            "impactDescription": "Description of the impact of Project 1.",
            "fundingHistory": [
              { "date": "2023-07-01", "amount": 1000 },
              { "date": "2023-07-15", "amount": 1500 },
              { "date": "2023-07-28", "amount": 2000 }
            ]
          }
          ```

          Voter Collection:
         ```{
               "_id": "voter_id_1", \\ can be a hashed to maintain complete anonymity.
               "name": "Voter 1",
               "address": "0xabcde12345",
               "ballot": [
                 {
                   "project": "project_id_1",
                   "vote": 5
                 },
                 {
                   "project": "project_id_2",
                   "vote": 3
                 },
                 {
                   "project": "project_id_3",
                   "vote": 2
                 }
               ]
             }
          ```
        - By using the above schema or a better revised schema or any schema provided to us, REST API routes will be created:
                - POST \api\voting\vote : will be used by the badgeholder to cast the vote.
                - PUT \api\voting\updatevote : will be used to update votes.
                - GET \api\voting\votinginfo: to fetch the current voting information of the badgeholder.
                - GET \api\voting\opused : will fetch information about OP used by the badgeholder to populate the OP allocated progress seek shown in the wireframe.
        - Whitelist functionality to be implemented in the backend so only whitelisted wallet address badgeholders could access these important routes or any other badgeholder route.        
        
        - Complete and total anonymity will be maintained by not revealing any voting information to anyone but the voter through any route.
        - Smooth frontend using REACT.js which will be higly responsive and exactly the same as provide in the wireframe.


## CI\CD pipeline for hosting 
- Implementation of a continous integration and delivery pipeline with any preffered cloud service providers like AWS, AZURE cloud etc.
- Optimal configuration and devops infrastructure using docker and kubernetes for seamless scaling and avalibility.


# Please outline your step-by-step plan to execute this Mission, including expected deadlines to complete each peice of work:

### Week 1: August 11th - August 18th

- Requirement Analysis and Finalization:
  - Discuss and gather detailed requirements from the organization and understand everything in even more depth.
  - Finalize the database schema based on the requirements.
  - Obtain access to the organization's private resources, including API keys for integration with Ethereum Attestation Service (EAS).
  - Plan and design the login and verification system using technologies like JWT for badgeholders and users.
- Frontend and Backend Setup:
  - Set up the frontend project using React.js in NEXT.js framework.
  - Initialize the backend project and configure the required dependencies.

### Week 2: August 19th - August 25th

- Building Login and Verification System:
  - Implement API routes for badgeholders and users to register and log in.
  - Implementing whitelist functionality in the backend for whitelisting wallet address of the badgeholders. 
  - Use JWT (JSON Web Tokens) for authentication and authorization of badgeholders and users.
  - Create frontend components for user registration, login, and verification.
- Frontend for Login and Registration:
  - create the user interface for user registration and login.
- start working on the search functionalities by using preffered search engine( Apache Solr, elasticsearch etc.)

### Week 3: August 26th - September 1st

- Backend for Discovery Page:
  - Work on the chosen open-source search engine (Apache Solr or Elasticsearch) in the backend to create the functionalities.
  - Implement search, sorting, and filtering functionalities for project discovery using the search engine.

- Frontend for Discovery Page:
  - Create the user interface for project discovery using NEXT.js.
  - Implement frontend components for searching, sorting, and filtering functionalities.
  - Integrate the frontend with the backend to fetch and display search results.
- Discovery page will be completed by 3rd week.


### Week 4: September 2nd - September 8th

- Backend for Viewing Project Profiles:
  - Implement API routes to fetch project details from the database based on the provided schema.
  - Integrate Ethereum Attestation Service (EAS) to query on-chain information and display relevant social verifications on project profiles.
- Frontend for Viewing Project Profiles:
  - Create the user interface for viewing project profiles using React.js.
  - Implement frontend components to display project details and social verifications.

### Week 5: September 9th - September 15th

- Backend for List Creation Page:
  - Implement API routes for badgeholders to create, update, copy, and delete lists, count OP functionality to update the real time count on Navbar as shown in the wireframe.
- Frontend for List Creation Page:
  - Design and create the user interface for creating and managing lists using NEXT.js.
  - Implement frontend components for list-related functionalities, including list creation and management.

### Week 6: September 16th - September 22nd

- Backend for Submitting Vote Components:
  - Create API routes for badgeholders to cast votes, update votes, fetch voting information, and OP used progress.
- Frontend for Submitting Vote Components:
  - Design and create the user interface for voting on projects and lists using NEXT.js.
  - Implement frontend components for casting and updating votes.

### Week 7: September 23rd - September 30th

- Integration and Testing:
  - Integrate all frontend and backend components to create a fully working application.
  - Perform thorough testing to identify and fix any bugs or issues.

- CI/CD Pipeline and Deployment:
  - Set up a continuous integration and delivery pipeline for automatic deployment of the application.

- Conduct user acceptance testing with the organization to validate the application's functionality.

### End of September and Start of October: Project Completion

- Final Review and Documentation:
  - Ensure the application meets all requirements specified in the RFP.
  - Conduct a final review with the organization to validate the successful execution of the mission.
  - Conduct user acceptance testing with the organization to validate the application's functionality.
  - Prepare documentation and user guides for the application.
 
- Launch and Operation:
   - Deploy the application to production and ensure it is operational and accessible to users.
   - making required changes if any using CI/CD pipeline and mainting the project till March 2024.

By following this week-by-week plan, both frontend and backend development will progress together, ensuring that all major components of the application are built simultaneously. The plan also includes specific milestones for each page and functionality, allowing for continuous integration and testing to deliver a complete and functional RetroPGF 3 Discovery & Voting application by the end of September. By following this timeline we will ahve enough time for proper tetsing and validation.

# Please define the critical milestone(s) that should be used to determine whether you’ve executed on this proposal:

The critical milestones that should be used to determine the successful execution of the proposal are as follows:

1. Completion of Project Discovery Feature (End of Week 3):
   - Backend implementation of the search engine (Apache Solr or Elasticsearch) for project discovery, including search, sorting, and filtering functionalities.
   - Frontend implementation of the project discovery page using React.js and integration with the backend to fetch and display search results.

2. Viewing Project Profiles Feature (End of Week 4):
   - Backend implementation to fetch project details from the database and integrate with Ethereum Attestation Service (EAS) for social verifications.
   - Frontend implementation of the project profile viewing page using React.js, displaying project details and social verifications.

3. Discovering and Voting on Lists Feature (End of Week 5):
   - Backend implementation of API routes for badgeholders to create, update, copy, and delete lists, including OP used count functionality.
   - Frontend implementation of the list creation page using React.js, allowing badgeholders to create and manage lists.

4. Submitting Vote Components (End of Week 6):
   - Backend implementation of API routes for badgeholders to cast and update votes, fetch voting information, and OP used progress.
   - Frontend implementation of the voting components using React.js, enabling badgeholders to cast and update votes.

5. Integration and Testing (End of Week 7):
   - Successful integration of all frontend and backend components to create a fully working application.
   - Thorough testing to identify and fix any bugs or issues, ensuring a stable application.

6. CI/CD Pipeline and Deployment (Start of October):
   - Setting up a continuous integration and delivery pipeline for automatic deployment of the application.
   - Successful deployment of the application to production, making it accessible to users.

7. Final Review and Documentation (Start of October):
   - Validation of the application's functionality through user acceptance testing with the organization.
   - Preparation of documentation and user guides for the application.

A review meeting will be held with end of each timeline to show our progress and assure that these milestones have been completed by us.

