##Quick Recap - Principles of Object-orientation
* Abstraction
* Encapsulation
* Modularization
* Hierarchy


##Design Patterns - A Motivating Example


##Design Patterns - A Motivating Example
* Bootcamp course and a few stakeholders (Students and Instructors)
* Any change in the course must be notified to all the stakeholders
* Now, think about its implementation


##Design Patterns - A Motivating Example
![](media/observerMotivation.png)


##Implementation
```java
public class Course {
private Student student;
private Instructor instructor;
	public Course() {
		student = new Student();
		instructor = new Instructor();
	}
	public void update() {
		student.update();
		instructor.update();	
	}
}
```