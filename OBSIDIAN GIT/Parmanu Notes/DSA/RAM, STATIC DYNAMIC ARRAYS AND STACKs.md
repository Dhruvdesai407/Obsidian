#### Arrays are always continuous !
==RAM: randomly access memory in constant time. O(1)==
Static arr not avail in .py .js . Static arr ==can't add new value and address== as it ==break continuity==, but they ==can allot a value== in given address for the Arr in const time.
==Can't delete an object value, but can remove value from address in O(1)==

| ==Operation==                                                                            | ==Big- O Time== |
| ---------------------------------------------------------------------------------------- | --------------- |
| r/w ith i-th element                                                                     | O(1)            |
| insert / remove end (assuming empty space at end or atleast have one element at the end) | O(1)            |
| insert middle                                                                            | O(n)            |
| remove middle                                                                            | O(n)            |
![[Pasted image 20250601132151.png]]


