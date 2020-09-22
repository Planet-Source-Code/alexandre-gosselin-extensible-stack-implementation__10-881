<div align="center">

## Extensible stack implementation


</div>

### Description

A stack is a LIFO (Last in First out) collection. It can store any kind of data and has the possibility to extend its maximum number of objects.

Comments would be greatly appreciated!
 
### More Info
 
Push(object)

Pop(void)

Peek(void)

Data stored in the stack

Pop() returns null when the stack is empty so beware.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Alexandre Gosselin](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/alexandre-gosselin.md)
**Level**          |Intermediate
**User Rating**    |3.0 (9 globes from 3 users)
**Compatibility**  |C\#
**Category**       |[Data Structures](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/data-structures__10-8.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/alexandre-gosselin-extensible-stack-implementation__10-881/archive/master.zip)





### Source Code

```
using System;
namespace MyLibrary.Collections
{
	public class MyStack
	{
		private long nIncrement;
		private long nElements;
		private object[] elements;
		public MyStack(long initialCapacity, long nIncrement)
		{
			this.nElements = 0;
			this.nIncrement = nIncrement;
			elements = new object[initialCapacity];
		}
		public void Push(object element)
		{
			// If needed, extends stack's capacity to store more element.
			if (nElements == elements.Length)
			{
				object[] temp = new object[nElements + nIncrement];
				for (int i=0; i<nElements; i++)
					temp[i] = elements[i];
				elements = temp;
			}
			// Pushes element at the top of the stack.
			elements[nElements] = element;
			nElements++;
		}
		public object Pop()
		{
			if (IsEmpty())
				return null;
			else
			{
				object element = elements[nElements - 1];
				nElements--;
				return element;
			}
		}
		public object Peek()
		{
			if (IsEmpty())
				return null;
			else
				return elements[nElements - 1];
		}
		public bool IsEmpty()
		{
			if (nElements == 0)
				return true;
			else
				return false;
		}
		public long Length
		{
			get
			{
				return nElements;
			}
		}
	}
}
```

