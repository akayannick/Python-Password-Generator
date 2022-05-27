# Python-Password-Generator
How to Create a Random Password Generator in Python.


![python password](https://user-images.githubusercontent.com/98027205/170694699-90f8943f-b3ef-480d-8519-c57d05a491e0.png)


## Security is one of the most crucial parts of our lives. The importance of security is increasing day by day as most things are going online. Passwords come into light as we talk about security.

In this github-project, we will create a password generator that helps us generate random and strong passwords quickly.

### Why do we need a password generator?

Because we can’t think of different patterns of passwords instantly.

But, it is not the same case with computers. Computers can generate random and strong passwords based on our customizations in seconds. There are many password generators available.

Can we create our own with the customizations we like?

Yes, we can definitely create one. And here we are going to show you how to do that.

Let’s create a password generator.

# Password Generator 💻

The best thing about creating our own password generator is that we can customize it as we like.

First, we will create a password generator that asks the length of the password and generates a random password containing digits, alphabets, and special characters.

Next, we will improve it by asking the number of each type of character, like the number of digits, alphabets, and special characters.

So, without further ado, let’s see the steps to create a password generator using Python.

## Steps

• Store all the characters as a list. We can use the string module of Python or type all of them. 

• Ask the user to enter the length of the password.

• Shuffle the characters using the ```random.shuffle``` method.

• Initialize an empty list to store the password.

• Write a loop that iterates ```length``` times. 
Pick a random character from all the characters using the ```random.choice``` method.
Append the random character to the password.

• Shuffle the resultant password list to make it more random.

• Convert the password list to string using the ```join``` method.

• Print the password.

Follow the above steps and try to write code. Don’t worry, even if you are not able to write the code. Check out the code below.

### Code
```py
import string
import random


## characters to generate password from
characters = list(string.ascii_letters + string.digits + "!@#$%^&*()")

def generate_random_password():
	## length of password from the user
	length = int(input("Enter password length: "))

	## shuffling the characters
	random.shuffle(characters)
	
	## picking random characters from the list
	password = []
	for i in range(length):
		password.append(random.choice(characters))

	## shuffling the resultant password
	random.shuffle(password)

	## converting the list to string
	## printing the list
	print("".join(password))



## invoking the function
generate_random_password()
```
 
The above code is self-explanatory. We have just followed the steps described to write code. So, you won’t find any problem in understanding the code if you read the steps.

Now, run the code and generate a password. An example output will be as follows.

```py
Enter password length: 10
d&amIzK%d)
```

Observe the password in the above output. Is there any digit? No. Because there is no guarantee that the program will include digits.

Next, we try to guarantee that the program will include digits and special characters by asking the user to enter the number of digits, alphabets, and special characters they want.

When the user enters the number of characters for each type, the program will include the respective number of character types into the password.

Let’s see the code that accepts the number of characters for each type and generates the password.

```py
import string
import random


## characters to generate password from
alphabets = list(string.ascii_letters)
digits = list(string.digits)
special_characters = list("!@#$%^&*()")
characters = list(string.ascii_letters + string.digits + "!@#$%^&*()")

def generate_random_password():
	## length of password from the user
	length = int(input("Enter password length: "))

	## number of character types
	alphabets_count = int(input("Enter alphabets count in password: "))
	digits_count = int(input("Enter digits count in password: "))
	special_characters_count = int(input("Enter special characters count in password: "))

	characters_count = alphabets_count + digits_count + special_characters_count

	## check the total length with characters sum count
	## print not valid if the sum is greater than length
	if characters_count > length:
		print("Characters total count is greater than the password length")
		return


	## initializing the password
	password = []
	
	## picking random alphabets
	for i in range(alphabets_count):
		password.append(random.choice(alphabets))


	## picking random digits
	for i in range(digits_count):
		password.append(random.choice(digits))


	## picking random alphabets
	for i in range(special_characters_count):
		password.append(random.choice(special_characters))


	## if the total characters count is less than the password length
	## add random characters to make it equal to the length
	if characters_count < length:
		random.shuffle(characters)
		for i in range(length - characters_count):
			password.append(random.choice(characters))


	## shuffling the resultant password
	random.shuffle(password)

	## converting the list to string
	## printing the list
	print("".join(password))



## invoking the function
generate_random_password()
```

So, what is the difference between the previous code and this code?

• We have written separate loops for each type of character to add them to the password.

• There are two conditional checks to validate the total characters count with password length.

We have added some extra code. But, the pattern is similar to the previous code. So, you won’t find any difficulty in understanding it.

Now, it’s time to execute and check the output. Look at the following test run.

```py
Enter password length: 10
Enter alphabets count in password: 3
Enter digits count in password: 2
Enter special characters count in password: 3
V2(&#XlQq1
```

If you see the password generated this time, it has the minimum number of characters that the user wants. And the program has included 2 more random characters to make the password length equal to user input.

Hurray! we have a complete strong password generator. 😎


# Happy Coding! 👩‍💻

## If you would like to join our team, Please contact us at [Discord](https://discord.gg/YpEuQYUJ7z)

~ aka._.yannick/Developer
