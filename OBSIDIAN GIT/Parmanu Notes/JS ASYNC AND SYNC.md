
asynchronous means that the code exec is simultaneous.
while synchronous is vice-versa
to import js libraries:
![[Pasted image 20250515193312.png]]

Function argument:
![[Pasted image 20250515193616.png]]

![[Pasted image 20250515201104.png]]
fs.readFileSync means that the func will also sync, hence it becomes synchronous.
whereas fs.readFile is asynchronous, which is btw faster.
![[Pasted image 20250515201917.png]]
CPU intensive tasks have more priority that I/O operations, as it requires cpu running for it.
![[Pasted image 20250515202742.png]]
Call Stack refers to CPU intensive tasks, web Api will refer to I/O ops, Callback Queue refers to completed Web Apis.
err is object type.
![[Pasted image 20250515233157.png]]
this is different from the var <object> {}
`const rect = new Rectangle(2,4)` implies the creation of new object `rect` from class <Rectangle>, due the <new> keyword.

Some of JS preconfigured <classes>.



