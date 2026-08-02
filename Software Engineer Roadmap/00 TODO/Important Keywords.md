=========================
C# STRING CHEAT SHEET
=========================

Length                         // Number of characters             // Eg: int len = s.Length;

ToCharArray()                  // String -> char[]                 // Eg: char[] arr = s.ToCharArray();
new string(char[])             // char[] -> String                 // Eg: string s = new string(arr);

ToUpper()                      // Uppercase                        // Eg: s.ToUpper();
ToLower()                      // Lowercase                        // Eg: s.ToLower();

Contains()                     // Check substring                  // Eg: s.Contains("abc");
StartsWith()                   // Starts with                      // Eg: s.StartsWith("He");
EndsWith()                     // Ends with                        // Eg: s.EndsWith("lo");
IndexOf()                      // First occurrence                 // Eg: s.IndexOf('a');
LastIndexOf()                  // Last occurrence                  // Eg: s.LastIndexOf('a');

Equals()                       // Compare strings                  // Eg: s.Equals("Hello");
string.Compare()               // Lexicographical compare          // Eg: string.Compare(a, b);

Substring(start)               // From index to end                // Eg: s.Substring(2);
Substring(start, len)          // Part of string                   // Eg: s.Substring(2, 3);

Replace(old, new)              // Replace text                     // Eg: s.Replace("a", "b");

Split()                        // Split string                     // Eg: s.Split(',');
string.Join()                  // Join strings                     // Eg: string.Join("-", arr);

Trim()                         // Remove spaces                    // Eg: s.Trim();
TrimStart()                    // Remove left spaces               // Eg: s.TrimStart();
TrimEnd()                      // Remove right spaces              // Eg: s.TrimEnd();

Insert(index, value)           // Insert text                      // Eg: s.Insert(2, "ABC");
Remove(start)                  // Remove to end                    // Eg: s.Remove(2);
Remove(start, count)           // Remove characters                // Eg: s.Remove(2, 3);

string.IsNullOrEmpty()         // Null or empty                    // Eg: string.IsNullOrEmpty(s);
string.IsNullOrWhiteSpace()    // Null/Empty/Spaces                // Eg: string.IsNullOrWhiteSpace(s);

string.Format()                // Format string                    // Eg: string.Format("{0}", name);
$""                            // String interpolation             // Eg: $"Hello {name}";

=========================================================
ARRAY METHODS
=========================================================

Array.Sort()                   // Sort array                       // Eg: Array.Sort(arr);
Array.Reverse()                // Reverse array                    // Eg: Array.Reverse(arr);
Array.Copy()                   // Copy array                       // Eg: Array.Copy(src, dest, 5);
Array.IndexOf()                // Find index                       // Eg: Array.IndexOf(arr, 10);
Array.Clear()                  // Set default values               // Eg: Array.Clear(arr, 0, arr.Length);
Array.Resize()                 // Resize array                     // Eg: Array.Resize(ref arr, 10);

=========================================================
CHAR METHODS
=========================================================

char.IsDigit()                 // Check digit                      // Eg: char.IsDigit('5');
char.IsLetter()                // Check alphabet                   // Eg: char.IsLetter('A');
char.IsLetterOrDigit()         // Letter or digit                  // Eg: char.IsLetterOrDigit('9');
char.IsWhiteSpace()            // Check space                      // Eg: char.IsWhiteSpace(' ');
char.IsUpper()                 // Uppercase                        // Eg: char.IsUpper('A');
char.IsLower()                 // Lowercase                        // Eg: char.IsLower('a');
char.ToUpper()                 // Convert upper                    // Eg: char.ToUpper('a');
char.ToLower()                 // Convert lower                    // Eg: char.ToLower('A');

=========================================================
LINQ METHODS (using System.Linq)
=========================================================

Reverse()                      // Reverse sequence                 // Eg: s.Reverse();
Count()                        // Count elements                   // Eg: arr.Count();
Any()                          // Any exists                       // Eg: arr.Any();
All()                          // All satisfy                      // Eg: arr.All(x => x > 0);
Where()                        // Filter                           // Eg: arr.Where(x => x > 5);
Select()                       // Transform                        // Eg: arr.Select(x => x * 2);
OrderBy()                      // Ascending sort                   // Eg: arr.OrderBy(x => x);
OrderByDescending()            // Descending sort                  // Eg: arr.OrderByDescending(x => x);
Distinct()                     // Remove duplicates                // Eg: arr.Distinct();
First()                        // First element                    // Eg: arr.First();
FirstOrDefault()               // First or default                 // Eg: arr.FirstOrDefault();
Last()                         // Last element                     // Eg: arr.Last();
LastOrDefault()                // Last or default                  // Eg: arr.LastOrDefault();
Max()                          // Maximum                          // Eg: arr.Max();
Min()                          // Minimum                          // Eg: arr.Min();
Sum()                          // Sum                              // Eg: arr.Sum();
ToArray()                      // Convert to array                 // Eg: list.ToArray();
ToList()                       // Convert to list                  // Eg: arr.ToList();

=========================================================
COMMON NAMESPACES
=========================================================

using System;
using System.Linq;
using System.Text;
using System.Collections.Generic;




=========================================================
C# PRIMITIVE DATA TYPES
=========================================================

int                             // 32-bit integer                  // Eg: int age = 25;
long                            // 64-bit integer                  // Eg: long pop = 9000000000L;
short                           // 16-bit integer                  // Eg: short s = 10;
byte                            // 8-bit unsigned                  // Eg: byte b = 255;
float                           // 32-bit decimal                  // Eg: float f = 10.5f;
double                          // 64-bit decimal                  // Eg: double d = 10.5;
decimal                         // High precision                  // Eg: decimal m = 10.5m;
char                            // Single character                // Eg: char c = 'A';
bool                            // True/False                      // Eg: bool ok = true;
string                          // Text                            // Eg: string name = "Mani";

=========================================================
CONVERSION
=========================================================

Convert.ToInt32()               // To int                          // Eg: Convert.ToInt32("10");
Convert.ToDouble()              // To double                       // Eg: Convert.ToDouble("10.5");
Convert.ToDecimal()             // To decimal                      // Eg: Convert.ToDecimal("10.5");
int.Parse()                     // String -> int                   // Eg: int.Parse("10");
double.Parse()                  // String -> double                // Eg: double.Parse("10.5");
decimal.Parse()                 // String -> decimal               // Eg: decimal.Parse("10.5");

int.TryParse()                  // Safe conversion                 // Eg: int.TryParse(s, out int n);

=========================================================
MATH METHODS
=========================================================

Math.Abs()                      // Absolute value                  // Eg: Math.Abs(-5);
Math.Max()                      // Maximum                         // Eg: Math.Max(10,20);
Math.Min()                      // Minimum                         // Eg: Math.Min(10,20);
Math.Sqrt()                     // Square root                     // Eg: Math.Sqrt(25);
Math.Pow()                      // Power                           // Eg: Math.Pow(2,3);
Math.Round()                    // Round                           // Eg: Math.Round(10.56);
Math.Ceiling()                  // Round up                        // Eg: Math.Ceiling(10.2);
Math.Floor()                    // Round down                      // Eg: Math.Floor(10.9);

=========================================================
STACK`<T>`
=========================================================

Push()                          // Add to top                      // Eg: stack.Push(10);
Pop()                           // Remove top                      // Eg: stack.Pop();
Peek()                          // View top                        // Eg: stack.Peek();
Count                           // Size                            // Eg: stack.Count;
Contains()                      // Exists                          // Eg: stack.Contains(10);
Clear()                         // Remove all                      // Eg: stack.Clear();
ToArray()                       // Stack -> Array                  // Eg: stack.ToArray();

Declaration:
Stack`<int>` stack = new Stack`<int>`();

=========================================================
QUEUE`<T>`
=========================================================

Enqueue()                       // Add to rear                     // Eg: queue.Enqueue(10);
Dequeue()                       // Remove front                    // Eg: queue.Dequeue();
Peek()                          // View front                      // Eg: queue.Peek();
Count                           // Size                            // Eg: queue.Count;
Contains()                      // Exists                          // Eg: queue.Contains(10);
Clear()                         // Remove all                      // Eg: queue.Clear();
ToArray()                       // Queue -> Array                  // Eg: queue.ToArray();

Declaration:
Queue`<int>` queue = new Queue`<int>`();

=========================================================
LINKEDLIST`<T>`
=========================================================

AddFirst()                      // Add beginning                   // Eg: list.AddFirst(10);
AddLast()                       // Add end                         // Eg: list.AddLast(20);
AddBefore()                     // Before node                     // Eg: list.AddBefore(node,15);
AddAfter()                      // After node                      // Eg: list.AddAfter(node,15);

Remove()                        // Remove value                    // Eg: list.Remove(10);
RemoveFirst()                   // Remove first                    // Eg: list.RemoveFirst();
RemoveLast()                    // Remove last                     // Eg: list.RemoveLast();

Find()                          // Find node                       // Eg: list.Find(20);
Contains()                      // Exists                          // Eg: list.Contains(20);

First                           // First node                      // Eg: list.First.Value;
Last                            // Last node                       // Eg: list.Last.Value;

Count                           // Size                            // Eg: list.Count;
Clear()                         // Remove all                      // Eg: list.Clear();

Declaration:
LinkedList`<int>` list = new LinkedList`<int>`();

=========================================================
LIST`<T>`
=========================================================

Add()                           // Add item                        // Eg: list.Add(10);
AddRange()                      // Add multiple                    // Eg: list.AddRange(arr);
Insert()                        // Insert                          // Eg: list.Insert(1,20);

Remove()                        // Remove value                    // Eg: list.Remove(10);
RemoveAt()                      // Remove index                    // Eg: list.RemoveAt(0);
RemoveAll()                     // Remove condition                // Eg: list.RemoveAll(x=>x>5);

Contains()                      // Exists                          // Eg: list.Contains(10);
IndexOf()                       // Index                           // Eg: list.IndexOf(10);

Sort()                          // Sort                            // Eg: list.Sort();
Reverse()                       // Reverse                         // Eg: list.Reverse();

Count                           // Size                            // Eg: list.Count;
Clear()                         // Remove all                      // Eg: list.Clear();

=========================================================
MOST IMPORTANT FOR DSA
=========================================================

Stack:
Push()
Pop()
Peek()
Count

Queue:
Enqueue()
Dequeue()
Peek()
Count

LinkedList:
AddFirst()
AddLast()
RemoveFirst()
RemoveLast()
Find()
First
Last

List:
Add()
Remove()
Contains()
Sort()
Reverse()
IndexOf()
Count

Math:
Abs()
Max()
Min()
Sqrt()
Pow()

Conversion:
TryParse()
Parse()
Convert.ToInt32()