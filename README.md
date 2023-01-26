## Python Assignment from Citadel Modules

#### Assignment 1: Write a python script which will be able to accept the data on command line as input and will be able to identify and print out the datatype of the given input.

#### Solution:
```  
inputval=input("Enter data")  

try:
        inputval = int(inputval)
        print("The Data type of ",inputval, " is : int" )
except ValueError:
        try:
            inputval = float(inputval)
            print("The Data type of ",inputval, " is : float" )
        except ValueError:
            print("The Data type of ",inputval, " is : string" )
```


#### Assignment 2: Write a python program to print out the Fibonacci series of digits between 1 to 100. Try to achieve this using all the types of loop available in python.

#### Solution:
##### using while Loop
```
a=0
b=1
c=0
print(a)

while b<=100:
    print(b)
    c=a+b
    a=b
    b=c
```    
##### Using for loop
```
a=0
b=1
c=0
print(a) 

for i in range(101):
  if b<=100:
    print(b)
    c=a+b
    a=b
    b=c
  else:
    break
```

#### Assignment 3: Traversing through below list of digits, filter out the numbers which are divisible by 5. list = [12, 15, 32, 42, 55, 75, 122, 132, 150, 180, 200]

#### Solution:
```
list1 = [12, 15, 32, 42, 55, 75, 122, 132, 150, 180, 200]
final_list=[x for x in list1 if x%5 == 0]
print(final_list)
```

#### Assignment 4: Write a python program which keeps reading content from command line until the content is 'quit', and then writes the content before quit to a file.

#### Solution:
```
import sys
x=''
for line in sys.stdin:
  if 'quit' not in line:    
      x= x + line
  else:
      x=x+line.replace("quit", "")
      break

f = open("mydata.txt", "w")
f.write(x)
f.close()
```

#### Assignment 5: Write a program in Python which will be able to accept any number of arguments in the same function and can process it.

#### Solution:
```
def myfunction(*argslist):
    sumvalue = 0
    for i in argslist:
        sumvalue = sumvalue+i
    print("Accepted Multiple Argument values and processed its sum as: ",sumvalue)
 

myfunction(4,6,1,0,7,3)
```

#### Assignment 6: Write a program which will be able to accept Student data with help of different functions, to eventually store all data in one dictionary, and finally print out all content of that dictionary variable.

#### Solution:
```
def getdetails(name,rollno,age,Class):
    studdict={}
    studdict["name"]=name
    studdict["rollno"]=rollno
    studdict["age"]=age
    studdict["Class"]=Class
    return studdict

def printdetails():
    j=1
    for each_stud in student_db:
        print("Details of Student ",j ," are:")
        print("Name: ",each_stud["name"],", RollNo: ",each_stud["rollno"],", Age: ", each_stud["age"],", Class: ",each_stud["Class"])
        j +=1

i=1    
student_db=[]
stud_count=input("How many students data you wanted to save ?")

while i<=int(stud_count):
    print("Please enter Student ",i," details !!")
    nm=input("Student name")
    roll=input("Student rollnumber")
    ag=input("Student  age")
    cls=input("Student class")
    student_db.append(getdetails(nm,roll,ag,cls))
    print("Student ",i," data saved successfully !!")
    i +=1

printdetails()
```
#### Assignment 7: Write a python program which contains a dictionary with specific data. The script should accept the key name from command line and output its value from the dict. When specific key is not present in dict, it should give a specific message rather than throwing error and abruptly stopping execution and ask for next input.

#### Solution:
```
mydict={"city1":"Hyd","city2": "Mumbai", "city3": "Delhi","city4":"Chennai"}

while True:
    key_input=input("Enter a key: ")
    try:
        print("The Value of this key is: ",mydict[key_input])
    except Exception as e:
        print("Key not found in dictionary. Try other key !!")
```        
#### Assignment 8: Perform the same task as in assignment 5, but with the help of class and its object.
#### i.e Write a program in Python which will be able to accept any number of arguments in the same function and can process it.

#### Solution:
```
class myclass:
    def myfunction(self,*argslist):
        self.sumvalue = 0
        for i in argslist:
            self.sumvalue = self.sumvalue+i
        print("Accepted Multiple Argument values and processed its sum as: ",self.sumvalue)
     
myobj=myclass()
myobj.myfunction(4,6,1,0,7,3,4)
```
