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
