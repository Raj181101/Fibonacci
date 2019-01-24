# Fibonacci
#To Check The Whether The Given String Is Dynamic Or Not Depending On Users Input
def Fibonacci(par):
    C= [string.count(x) for x in set(par)] #To Make The Elements To Be Unique And Thier Counts
    C.sort()
    flag = 1 #To change The Value
    if len(C) < 3:
        return 'Dynamic'
    for y in range(len(C)-1, 1, -1): #Looping Based On Top Value From Last Element Of List
        if C[y] != C[y-1] + C[y-2]: #Checking Conditions Regarding Equals Or Not
            flag = 0
            break
    if flag == 1:
        return 'Dynamic'
    else:
        return 'Not'
Result = "" 
try: #To Try The Error and To Catch The Error
  T = int(input("Enter The Testcases You Want:"))#Number Of Testcases
  if T>1 and T<10:
    for i in range(T):
      string = input("Enter The String:")#String With Lowercase As Input
      if string.islower() and len(string)<10**5:
        Result += Fibonacci(string)+'\n'         #Function Calling
      else:
        print("Enter Lowercase only!")
  else:
    print("Enter Range between 1 and 10 only!")
except:
  print("Please Enter Valid Input Only!") # To Solve The Error Problem
print(Result)
