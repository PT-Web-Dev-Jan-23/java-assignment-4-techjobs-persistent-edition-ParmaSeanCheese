# Java Graded Assignment #4 Rubric (TechJobs, Persistent Edition)

For [this assignment](https://education.launchcode.org/java-web-development/assignments/tech-jobs-persistent.html) students are tested for their understanding of SQL database management and the mechanics of object relational mapping. Students will demonstrate their knowledge of these topics by making updates again to the TechJobs application.
They will be asked to create the database connection, finish what has been started to persist several model classes, 
create a one-to-many and a many-to-many relationship between objects, and answer a few simple SQL questions.

Grading will be done via demonstrations. Students will be asked to give a walkthrough of their source code,
as well as the running application.

## Assignment Requirements

1. Connect a `Database` to a Spring Application
2. Persist `Employers` and `Skills`
3. Set up a `One-to-Many` Relationship
4. Set up a `Many-to-Many` Relationship

## Unit Tests

The starter code contains 6 unit test classes.

`TestTaskOne` verifies two things: 
   * Connection between database and data
   * Correct gradle dependencies have been added

`TestTaskTwo` has over 25 tests and covers all of Part 2.  If this class of tests fails, students need to carefully explore the test results for where an error occured.  

This test class verifies the following:
   * `AbstractEntity` - Does it exisit? How does it handle names and IDs?
   * Model Tests such as `Employer` and `Skill` - Do they contain the correct fields, correct accessors, correct validation annotations, constructors, and persistence.
   * The Data Layer - Do `EmployerRepository` and `SkillRepository` exisit?  Do theese repos implement CrudRepository? 
   * Controller Tests - Do EmployerController.index and SkillController.index route properly? Does it properly handle data inputs, routing, `findAll()` and `findById()` methods, and storing data?
   * SQL Tests - Can it select based on name? 

`TestTaskThree` verifies the following: 
* `Employer.jobs` has been properly defined and annotated
* `AbstractEntity` has been properly extended
* Many-to-one pattern created between `Job.employer` and `Employer`
* `HomeController` has an autowired `EmployerRepository` is able to call `employerRepository.findALL()`.
* SQL test to drop a table

`TestTaskFour` verifies the following:
* `Skill.jobs` exists as a type List and has a many-to-many relationship
* `Job.skills` has been refactored to a `List<Skills>`
* `Skills` has been properly refactored with correct accessors
* `HomeController` has a `SkillRepository`, and can handle a form 
* `ListController` has autowired repos, can set field data
* A SQL test that creates a join.

`TestCommentedTests` verifies that the correct number of tests have been uncommented. 

### Performance and Code Check:

Before you start coding, check out our [Working Demo App](https://techjobs-persistent.launchcodetechnicaltraining.org/).
The app occasionally restarts, so if you experience any issues, please wait a few minutes before refreshing the page.

Use the checks below to explore the working app.

1. Start the application and navigate to the *Add Job* view.
1. Create a new employer from the form and view the resulting object in the employer table.
1. Create at least two new skills from the form and view the objects in the skill table.
1. Create a new Job from the form, selecting at least two skills. 

   a. Once created, view the job table and verify that there is an ``employer_id`` column in it. 
     
   b. Confirm that a mapped table is present for ``job_skills`` and that at least two rows are now in it
      for the job just created.

## Submitting Your Work

To submit your work please follow the [Submission Instructions](https://education.launchcode.org/java-web-development/assignments/hello-world.html#submitting-your-work)
