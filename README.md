# fibonacci approach1
# Fibonacci series using a Python while loop
n = 10
num1 = 0
num2 = 1
next_number = num2 
count = 1

while count <= n:
	print(next_number, end=" ")
	count += 1
	num1, num2 = num2, next_number
	next_number = num1 + num2
print()


# Python Program for Fibonacci numbers using Recursion  
def Fibonacci(n):

	# Check if input is 0 then it will
	# print incorrect input
	if n < 0:
		print("Incorrect input")

	# Check if n is 0
	# then it will return 0
	elif n == 0:
		return 0

	# Check if n is 1,2
	# it will return 1
	elif n == 1 or n == 2:
		return 1

	else:
		return Fibonacci(n-1) + Fibonacci(n-2)


# Driver Program
print(Fibonacci(9))

# approach2
#  Fibonacci Sequence using Dynamic Programming
# Function for nth fibonacci 
# number
FibArray = [0, 1]

def fibonacci(n):

	# Check is n is less 
	# than 0
	if n < 0:
		print("Incorrect input")
		
	# Check is n is less 
	# than len(FibArray)
	elif n < len(FibArray):
		return FibArray[n]
	else:	 
		FibArray.append(fibonacci(n - 1) + fibonacci(n - 2))
		return FibArray[n]

# Driver Program
print(fibonacci(9))


# approach3
# Optimization of Fibonacci sequence
# Function for nth fibonacci number 
def fibonacci(n):
	a = 0
	b = 1
	
	# Check is n is less
	# than 0
	if n < 0:
		print("Incorrect input")
		
	# Check is n is equal
	# to 0
	elif n == 0:
		return 0
	
	# Check if n is equal to 1
	elif n == 1:
		return b
	else:
		for i in range(1, n):
			c = a + b
			a = b
			b = c
		return b

# Driver Program
print(fibonacci(9))


# Fibonacci Sequence using Backtracking approach4
def fibonacci(n, memo={}):
	if n <= 0:
		return 0
	elif n == 1:
		return 1
	elif n in memo:
		return memo[n]
	else:
		memo[n] = fibonacci(n-1) + fibonacci(n-2)
		return memo[n]

# Driver Program
print(fibonacci(9))



