# Assignment4-C-


04 Generics
Test your Knowledge

1. Describe the problem generics address.

Generics allows us to design classes and methods but defer the specification of types until the class or methods are declared and called.

Generic allows you to use a class or method that can work with any data type.  

Usually the type is specified by the <T>.  You can make a class, interface or method generic.

Generic Collection
  
They are multiple generic collections in C#. Most widely used are following
  
IEnumerable<T>
  
IQueryable<T>
  
List<T>
  
Dictionary<TKey,TValue>

Difference between Generics and Non Generic Collection
  
A Generic collection is a class that provides type safety without having to derive from a base collection type and implement type-specific members.
  
A Non-generic collection is a specialized class for data storage and retrieval that provides support for stacks, queues, lists and hash tables.
  
The Generic Collection classes are in the System. Collections. Generics namespace.
  
The Non -generic Collection classes are in the System. Collections namespace.
  
A Generic Collection is strongly typed.
  
A Non-Generic Collection is not strongly typed.
  
The Generic Collections store elements internally in arrays of their actual types.
  
The Non-generic collections store elements internally in object arrays so it can store any type of data.
 
2. How would you create a list of strings, using the generic List class?
  
string[] animals = {"cow", "carmel", "Elephant"};
  
List<String> animalList = new List<String> (3);


3. How many generic type parameters does the Dictionary class have?

System.Collections.Generic.IDictionary<TKey,TValue>;
 
Dictionary<string, string> openWith = new Dictionary<string, string>();

openWith.Add("txt", "notepad.exe");
openWith.Add("bmp", "paint.exe");
openWith.Add("dib", "paint.exe");
openWith.Add("rtf", "wordpad.exe");

  
4. True/False. When a generic class has multiple type parameters, they must all match.
  
False
  
5. What method is used to add items to a List object?

5.1 List<int> numbers = new List<int>(5) { 5, 10, 15, 20, 25};  
numbers.Add(30);  
numbers.Add(35);   
numbers.Add(40);  

  
5.2 int[] prime = new int[] { 1, 3, 5, 7, 11, 13};  
numbers.AddRange(prime);  
foreach (int num in numbers)  
{  
    Console.Write($"{num}, ");       
}  

5.3 List<string> names = new List<string>() {"Mahesh Chand", "Neel Beniwal", "Chris Love" };  
names.Add("Author One");  
names.Add("Author Two");   
names.Add("Author Three");  
  
names.AddRange(new string[] {"Raj Beniwal", "Allen O'neill" });  

foreach (string name in names)  
{  
    Console.Write($"{name}, ");  
}  
  
5.4 List<Author> authors = new List<Author>  {  
    new Author { Name = "Mahesh Chand", Book = "ADO.NET Programming", Price = 49.95 },  
    new Author { Name = "Neel Beniwal", Book = "Jump Ball", Price = 19.95 },  
    new Author { Name = "Chris Love", Book = "Practical PWA", Price = 29.95 }  
};  

authors.Add(new Author { Name = "Mahesh Chand", Book = "Graphics with GDI+", Price = 49.95 });  
authors.Add(new Author { Name = "Mahesh Chand", Book = "Mastering C#", Price = 54.95 });  
authors.Add(new Author { Name = "Mahesh Chand", Book = "Jumpstart Blockchain", Price = 44.95 });  

List<Author> duplicateAuthors = new List<Author>  {  
    new Author { Name = "Mahesh Chand", Book = "ADO.NET Programming", Price = 49.95 },  
    new Author { Name = "Neel Beniwal", Book = "Jump Ball", Price = 19.95 },  
    new Author { Name = "Chris Love", Book = "Practical PWA", Price = 29.95 }  
};  
authors.AddRange(duplicateAuthors);  
  
foreach (Author author in authors)  
{  
    Console.WriteLine($"Author: {author.Name}:{author.Book}:{author.Price}");  
}  

6. Name two methods that cause items to be removed from a List.
// removes an item at 2nd position in the List
AuthorList.RemoveAt(2);  
  
// removes 2 items starting at the 3rd position.  
AuthorList.RemoveRange(3, 2);  
  
7. How do you indicate that a class has a generic type parameter?
  
Generic classes are defined using a type parameter in an angle brackets after the class name.

  class DataStore<T>
{
    public T Data { get; set; }
}

  
  // Generic Class with Multiple Type Parameters
  class KeyValuePair<TKey, TValue>
{
    public TKey Key { get; set; }
    public TValue Value { get; set; }
}

 
  
8. True/False. Generic classes can only have one generic type parameter.

  False.
  
9. True/False. Generic type constraints limit what can be used for the generic type.
  
  False.
  
10. True/False. Constraints let you use the methods of the thing you are constraining to.
  
 True
  
Practice working with Generics
1. Create a custom Stack class MyStack<T> that can be used with any data type which has following methods
  
  1. int Count()
  
  2. T Pop()
  
  3. Void Push()
  
  class MyStack<T> {
  public int count();
  public T pop();
  Public void push();
  }

2. Create a Generic List data structure MyList<T> that can store any data type. Implement the following methods.
  
  1. void Add (T element)
  
  2. T Remove (int index)
  
  3. bool Contains (T element)
  
  4. void Clear ()
  
  5. void InsertAt (T element, int index)
  
  6. void DeleteAt (int index)
  
  7. T Find (int index)
  
  class MyList<T> {
  public void add<T>{};
  public T remover(int index){};
  public bool Contain<T>{};
  public void Clear(){};
  public void InsertAt<T>{};
  public void DeleteAt(int index){};
  public T Find(int index){};
  };
  
  
3. Implement a GenericRepository<T> class that implements IRepository<T> interface
that will have common /CRUD/ operations so that it can work with any data source
such as SQL Server, Oracle, In-Memory Data etc. Make sure you have a type constraint
on T were it should be of reference type and can be of type Entity which has one
property called Id. IRepository<T> should have following methods
  1. void Add(T item)
  2. void Remove(T item)
  3. Void Save()
  4. IEnumerable<T> GetAll()
  5. T GetById(int id)
Explore following topics
Generics in .NET
Generic classes and methods
Collections and Data Structures
Commonly Used Collection Types
  
namespace RepositoryUsingEFinMVC.GenericRepository
{
    public interface IGenericRepository<T> where T : class
    {
        IEnumerable<T> GetAll();
        T GetById(object id);
        void Insert(T obj);
        void Update(T obj);
        void Delete(object id);
        void Save();
    }
}
  
 namespace RepositoryUsingEFinMVC.GenericRepository
{
    public class GenericRepository<T> : IGenericRepository<T> where T : class
    {
        public EmployeeDBContext _context = null;
        public DbSet<T> table = null;

        public GenericRepository()
        {
            this._context = new EmployeeDBContext();
            table = _context.Set<T>();
        }

        public GenericRepository(EmployeeDBContext _context)
        {
            this._context = _context;
            table = _context.Set<T>();
        }

        public IEnumerable<T> GetAll()
        {
            return table.ToList();
        }

        public T GetById(object id)
        {
            return table.Find(id);
        }

        public void Insert(T obj)
        {
            table.Add(obj);
        }

        public void Update(T obj)
        {
            table.Attach(obj);
            _context.Entry(obj).State = EntityState.Modified;
        }

        public void Delete(object id)
        {
            T existing = table.Find(id);
            table.Remove(existing);
        }

        public void Save()
        {
            _context.SaveChanges();
        }
    }
}

using RepositoryUsingEFinMVC.DAL;
using RepositoryUsingEFinMVC.GenericRepository;
using System.Collections.Generic;
namespace RepositoryUsingEFinMVC.Repository
{
    public interface IEmployeeRepository : IGenericRepository<Employee>
    {
        IEnumerable<Employee> GetEmployeesByGender(string Gender);
        IEnumerable<Employee> GetEmployeesByDepartment(string Dept);
    }
}
  
  namespace RepositoryUsingEFinMVC.Repository
{
    public class EmployeeRepository : GenericRepository<Employee>, IEmployeeRepository
    {
        public IEnumerable<Employee> GetEmployeesByGender(string Gender)
        {
            return _context.Employees.Where(emp => emp.Gender == Gender).ToList();
        }

        public IEnumerable<Employee> GetEmployeesByDepartment(string Dept)
        {
            return _context.Employees.Where(emp => emp.Dept == Dept).ToList();
        }
    }
}
  
  
  
  using RepositoryUsingEFinMVC.Repository;
using System.Web.Mvc;
using RepositoryUsingEFinMVC.DAL;
using RepositoryUsingEFinMVC.GenericRepository;

namespace RepositoryUsingEFinMVC.Controllers
{
    public class EmployeeController : Controller
    {
        private IGenericRepository<Employee> repository = null;    
        private IEmployeeRepository employee_repository = null;

        public EmployeeController()
        {
            this.employee_repository = new EmployeeRepository();
            this.repository = new GenericRepository<Employee>();
        }

        public EmployeeController(EmployeeRepository repository)
        {
            this.employee_repository = repository;
        }
        public EmployeeController(IGenericRepository<Employee> repository)
        {
            this.repository = repository;
        }


        [HttpGet]
        public ActionResult Index()
        {
            //you can not access the below two mwthods using generic repository
            //var model = repository.GetEmployeesByDepartment("IT");
            var model = employee_repository.GetEmployeesByGender("Male");
            return View(model);
        }

        [HttpGet]
        public ActionResult AddEmployee()
        {
            return View();
        }

        [HttpPost]
        public ActionResult AddEmployee(Employee model)
        {
            if (ModelState.IsValid)
            {
                repository.Insert(model);
                repository.Save();
                return RedirectToAction("Index", "Employee");
            }
            return View();
        }

        [HttpGet]
        public ActionResult EditEmployee(int EmployeeId)
        {
            Employee model = repository.GetById(EmployeeId);
            return View(model);
        }

        [HttpPost]
        public ActionResult EditEmployee(Employee model)
        {
            if (ModelState.IsValid)
            {
                repository.Update(model);
                repository.Save();
                return RedirectToAction("Index", "Employee");
            }
            else
            {
                return View(model);
            }
        }

        [HttpGet]
        public ActionResult DeleteEmployee(int EmployeeId)
        {
            Employee model = repository.GetById(EmployeeId);
            return View(model);
        }

        [HttpPost]
        public ActionResult Delete(int EmployeeID)
        {
            repository.Delete(EmployeeID);
            repository.Save();
            return RedirectToAction("Index", "Employee");
        }
    }
}

  
  
  
  
 Delegate:
  
 A delegate is a type safe function pointer.
The signature of delegate must match the signature of function, the delegate points to.
  
  Anonymous Type
Encapsulate a set of read-only properties and their value into a single object
No need to explicitly define a type first.
Use of the new var keyword in conjunction with the object initialization syntax


At compile time, the C# compiler will autogenerate an uniquely named class
The class name is not visible from C#
Using implicit typing (var keyword) is mandatory
Anonymous types are reference types directly derived from System.Object
Anonymous method
Anonymous method is a method without a name. A delegate is used to create an anonymous method. 




An anonymous method can be created with the help of lambda operator (=>)

Lambda Operator =>
Lambda operator is used to create an anonymous method. It uses delegate to create an anonymous method. Left side to lambda operator is parameter/s and right side method body



Action, Predicate and Func
  
Action, Predicate and Func are predefined generic delegate.
  
Action delegate takes generic input parameter and does not return any value. Its return type is void
Predicate delegate takes generic input parameter and returns boolean value
Func delegate takes generic input parameters and returns generic value
