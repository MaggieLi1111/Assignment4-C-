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
