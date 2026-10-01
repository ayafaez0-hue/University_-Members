using System;

namespace UniversityMembersApp
{

    public class Person
    {
        public string Name { get; set; }
        public string Email { get; set; }


        public Person(string name, string email)
        {
                          
           
            Name = name;
            Email = email;

            Console.WriteLine("[Constructor] Person initialized");
        }

        public void DisplayBasicInfo()
        {
            Console.WriteLine($"Name: {Name}, Email: {Email}");
        }
    }

    
    public class Student : Person
    {
        public string StudentId { get; set; }
        public double GPA { get; set; }

        
        public Student(string name, string email, string studentId, double gpa)
            : base(name, email)
        {
            Console.WriteLine("[Constructor] Student created.");
            StudentId = studentId;
            GPA = gpa;
        }

        public void DisplayStudentInfo()
        {
            DisplayBasicInfo(); 
            Console.WriteLine($"Student ID: {StudentId}, GPA: {GPA}");
        }
    }

    
    public class Employee : Person
    {
        public string EmployeeId { get; set; }
        public decimal Salary { get; set; }

        
        public Employee(string name, string email, string employeeId, decimal salary)
            : base(name, email)
        {
            Console.WriteLine("[Constructor] Employee created.");
            EmployeeId = employeeId;
            Salary = salary;
        }
    }

    
    public class Teacher : Employee
    {
        public string CourseName { get; set; }

        
        public Teacher(string name, string email, string employeeId, decimal salary, string courseName)
            : base(name, email, employeeId, salary)
        {
            Console.WriteLine("[Constructor] Teacher created.");
            CourseName = courseName;
        }

        
        public void Teach()
        {
            Console.WriteLine($"Teacher {Name} explains {CourseName}.");
        }
    }

    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("--- Creating Student Object ---");
            
            Student student = new Student("Ali", "ali@univ.edu", "ST1020", 3.85);
            student.DisplayBasicInfo();

            Console.WriteLine("\n--- Student Details ---");
            student.DisplayStudentInfo(); 

                       
                        
            
            Teacher teacher = new Teacher("Dr. Ahmed", "ahmed@univ.edu", "EMP501", 12000, "C# Programming");

            Console.WriteLine("\n--- Teacher Details ---");
            teacher.DisplayBasicInfo(); 
                
                            }
    }
}# University_-Members