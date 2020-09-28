# MyStudy
 
## Web API Token Based Authentication using Microsoft OWIN
https://medium.com/@uppilivasanthi/web-api-token-based-authentication-using-microsoft-owin-77ab0645f156

# # Difference between IEnumerable and IEnumerator.
IEnumerable is an interface that defines one method GetEnumerator which returns an IEnumerator interface, this in turn allows readonly access to a collection. A collection that implements IEnumerable can be used with a foreach statement.

IEnumerable 

public IEnumerator GetEnumerator();

IEnumerator

public object Current;

public void Reset();

public bool MoveNext();

1. IEnumerable uses IEnumerator internally.
2. IEnumerable doesn’t know which item/object is executing.
3. IEnumerator knows the current position of item/object.
4. IEnumerable doesn't know the current position of item/object
5. IEnumerable has one method, GetEnumerator ()
// Difference between IEnumerable and IEnumerator.  
public class Program {  
    public static void Main(string[] args) {  
        IEnumerable_Example();  
    }  
    static void IEnumerable_Example() 
    {  
        List < string > Month = new List < string > ();  
        Month.Add("January");  
        Month.Add("February");  
        Month.Add("March");  
 
        IEnumerable < string > IEnumerable_ = (IEnumerable < string > ) Month;  
        Console.WriteLine("IEnumerable_Example() Executing");  
        Console.WriteLine("------------IEnumerable Returning items using foreach----------------");  
        foreach(string i in IEnumerable_) 
        {  
            Console.WriteLine(i);  
        }  
        IEnumerator_Example(IEnumerable_);  
    }  
    static public void IEnumerator_Example(IEnumerable enumerable) {  
        IEnumerator enumerator = enumerable.GetEnumerator();  
        Console.WriteLine("----------IEnumerator_Example() Executing------------");  
        while (enumerator.MoveNext()) {  
            Console.WriteLine("----" + enumerator.Current.ToString() + "----");  
        }  
        Console.ReadLine();  
    }  
}  

##Generic Collections
C# includes the following generic collection classes in the System.Collections.Generic namespace.

Generic Collections	Description
List<T>	Generic List<T> contains elements of specified type. It grows automatically as you add elements in it.
Dictionary<TKey,TValue>	Dictionary<TKey,TValue> contains key-value pairs.
SortedList<TKey,TValue>	SortedList stores key and value pairs. It automatically adds the elements in ascending order of key by default.
Queue<T>	Queue<T> stores the values in FIFO style (First In First Out). It keeps the order in which the values were added. It provides an Enqueue() method to add values and a Dequeue() method to retrieve values from the collection.
Stack<T>	Stack<T> stores the values as LIFO (Last In First Out). It provides a Push() method to add a value and Pop() & Peek() methods to retrieve values.
Hashset<T>	Hashset<T> contains non-duplicate elements. It eliminates duplicate elements.

##Non-generic Collections

ArrayList	ArrayList stores objects of any type like an array. However, there is no need to specify the size of the ArrayList like with an array as it grows automatically.
SortedList	SortedList stores key and value pairs. It automatically arranges elements in ascending order of key by default. C# includes both, generic and non-generic SortedList collection.
Stack	Stack stores the values in LIFO style (Last In First Out). It provides a Push() method to add a value and Pop() & Peek() methods to retrieve values. C# includes both, generic and non-generic Stack.
Queue	Queue stores the values in FIFO style (First In First Out). It keeps the order in which the values were added. It provides an Enqueue() method to add values and a Dequeue() method to retrieve values from the collection. C# includes generic and non-generic Queue.
Hashtable	Hashtable stores key and value pairs. It retrieves the values by comparing the hash value of the keys.
BitArray	BitArray manages a compact array of bit values, which are represented as Booleans, where true indicates that the bit is on (1) and false indicates the bit is off (0).
