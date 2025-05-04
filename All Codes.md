### Expense Calculation in Python 
```
expense_sergey = [100,200,300,400,500]
expense_sundar = [110,210,310,410,510]

def total_expense(expenses):
    total = 0
    for i in expenses:
        total +=i
    return total

sergeys_expense = total_expense(expense_sergey)
print(f"Sergeys Expense is : {sergeys_expense}")
sundars_expense = total_expense(expense_sundar)
print(f"Sundars Expense is: {sundars_expense}")
```

### Find cylender volume
```
def cylender_vol(radius, height = 7):
    print(f"Radius: {radius}")
    print(f"Height: {height}")
    volume = 3.14 * (radius ** 2) * height
    return volume

h = float(input("Enter the height: "))
r = float(input("Enter the radius: "))

volume = cylender_vol(r, h)
print(f"The volume is: {volume}")
```

### Find the Area of a Circle in Python:
```
from math import pi
def circle_area(r):
    area = pi*r**2
    return area
radious = float(input("Enter a Radious:"))
area_result = circle_area(radious)
print(f"The area of the circle is: {area_result}")
```

### Sum of multiple input numbers:
```
def n_sum(*args):
    summation = sum(args)
    return summation
values = list(map(int, input("Enter numbers with spaces:").split()))
summation = n_sum(*values)
print(f"The sum is: {summation}")
```

### Find the avg of n numbers:
```
def n_num(*args): # takes n number of values
    summation = sum(args) 
    return summation/len(args)

values = list(map(int, input("Enter numbers by space:").split()))
avg = n_num(*values)
print(f"The average of those numbers is: {avg}")
```

### Sum the first n positive integers:
```
def n_sum(*args):
    total = 0
    for i in args:
        if i > 0:
            total +=i
    return total

values = list(map(int, input("Enter space seperated numbers: ").split()))
summation = n_sum(*values)
print(f"The sum of first n positive integer is: {summation}")            
```

### How to get the execution time of the program:
```
import time
def timer (num):
    start_time = time.time()
    mul = 0
    for i in range(num):
        mul *= i
        big_num = mul*10000000
        end_time = time.time()
    return start_time - end_time

value = int(input("Enter a huge number: "))

ans = timer(value)
print(f"This program took around:  {ans}")
```

### Get the username in Python:
```
import getpass
print(getpass.getuser())
```

### Get the current datetime in Python:
```
import datetime
print(datetime.datetime.now())
```

### How to Reverse a string in Python:
```
def Rev_str (text):
    text = text[::-1]
    return text
text = str(input("Enter a text:"))
result = Rev_str(text)
print(result)
```

### How to create a list and tuple with comma separated numbers in Python that also filters garbage data:
```
def listuple(args):
    args = args.replace(" ", ",")
    lists = args.split(",")
    clean_exp = []
    for item in lists:
        item = item.strip()
        if item.isdigit():
            clean_exp.append(int(item))
    return clean_exp, tuple(clean_exp)

values = input("Enter numbers: ")
lst, tup = listuple(values)
print(f"This is the list : {lst}")
print(f"This is the tuple: {tup}")
```

### Creating an expense tracker in python:
```
def exptrac(expense):
    expense = expense.replace(" ", ",")
    expense = expense.split(",")
    clean_exp =[]
    for item in expense:
        item = item.strip()
        if item.isdigit():
            clean_exp.append(item)
            
    total = 0      
    for i in range(len(clean_exp)):
        exp = clean_exp[i]
        exp = int(exp)
        total += exp
        print(f"For month {i+1} expense is: {exp}")
    return total
expense = input("Enter expenses with commas:")
result = exptrac(expense)
print(result)
```

### Player score aggregator program:
```
score_list = {}
with open("E:\\Score.txt", "r") as f:
    for i in f:
        player , score = i.split(",")
        score = int(score.strip())
        if player in score_list:
            score_list[player].append(score)
        else:
            score_list[player] = [score]
        
for player,score in score_list.items():
    min_score = min(score)
    max_score = max(score)
    avg_score = sum(score)/len(score)
    total = sum(score)
    print(f"player: {player}, min score: {min_score}, max score: {max_score}, avg_score: {avg_score} & total: {total}")

top_player = None
highest_runs = 0
for player, score in score_list.items():
    total = sum(score)
    if total>highest_runs:
        highest_runs = total
        top_player = player
print(f"Top scores overall: Name: {top_player}, total runs: {highest_runs}")
```

### Same code Optimized
```
score_list = {}
with open ("E:\\Score.txt", "r") as f:
    for i in f:
        player, score = i.split(",")
        score = int(score.strip())
        if player in score_list:
            score_list[player].append(score)
        else:
            score_list[player]=[score]

top_player = None
highest_score = 0
for player, score in score_list.items():

    min_score = min(score)
    max_score = max(score)
    avg_score = sum(score)/len(score)
    top_score = sum(score)
    print(f"For PLayer: {player}, min score: {min_score}, max_score: {max_score}, avg score: {avg_score} & total score : {top_score}")

    if top_score>highest_score:
        highest_score = top_score
        top_player = player
print(f"Top Player: {top_player}, with top score: {highest_score}")
```

### Dictionary in python

```
appl_revenues = {
"USA": {
"iPhone": 20,
"iPad": 12,
"MacBook": 8
},
"China": {
"iPhone": 17,
"iPad": 9,
"MacBook": 6
},
"India": {
"iPhone": 9,
"iPad": 4,
"MacBook": 2
}
}

for country, product_data in appl_revenues.items():
    for product, revenue in product_data.items():
        print(f"{country}, {product} and Revenue: {revenue} in millions")

```

### Calander Function in Python
```
import calendar
july = calendar.month(2025, 7)
print(july)
```

### If the year leap year or not
```
leap = calendar.isleap(2025)
print(leap)
```

### exercise problem 
```
customers = {}
with open("E:\\customers.txt", "r") as f:
    for line in f:
        customer, amount = line.strip().split(",")
        customers[customer] = int(amount)

# Define reward processor
def process_customer_data(customers):
    updated_customers = {}
    for customer, amount in customers.items():
        if 100 <= amount <= 199:
            reward = "Bronze"
        elif 200 <= amount <= 499:
            reward = "Silver"
        elif amount >= 500:
            reward = "Gold"
        else:
            reward = None
        updated_customers[customer] = (amount, reward)
    return updated_customers

customers = process_customer_data(customers)
print(customers)
```
### Object oriented Programming (OOP)
```
import datetime

class Cricket_player:
    def __init__ (self, fname, lname, byear,team):
        self.first_name = fname
        self.last_name = lname
        self.birth_year = byear
        self.team = team
        self.scores = []
    
    def add_scores (self, scores):
        self.scores.append(scores)
    
    def avg_scores(self):
        return sum(self.scores)/len(self.scores)
    
    def get_age (self):
        now = datetime.datetime.now().year
        return now - self.birth_year
    
    def __str__(self):
        return (f"{self.first_name} {self.last_name} the cricket player from {self.team}") # print(virat) will triger this
    
    def __lt__(self, others):
        self_avg_score = self.avg_scores()
        others_avg_score = others.avg_scores()
        return self_avg_score < others_avg_score 
    
    def __eq__(self, others):
        self_age = self.get_age()
        others_age = others.get_age()
        return self_age == others_age

virat = Cricket_player("Virat", "Kohli", 1988, "India")
virat.add_scores(57)
virat.add_scores(78)
virat.add_scores(127)

print(virat.first_name)
print(virat.last_name)
print(virat.birth_year)
print(virat.team)
print(round(virat.avg_scores(),2))
print(f"Virat's age is: {virat.get_age()}")
print(virat) # convert virat into str and print the following from the class

Warner = Cricket_player("Devid", "Warner", 1989, "Australia")
print(Warner.first_name)
print(Warner.last_name)
print(Warner.birth_year)
Warner.add_scores(56)
Warner.add_scores(90)
Warner.add_scores(41)

print(Warner.avg_scores())
print(Warner.get_age())

##### Operator Overloading----------- __lt__ , __gt__ , __eq__ --------------------------------------------

print(virat.avg_scores() < Warner.avg_scores())
print(Warner<virat) # avg runs comparison
print(Warner>virat) # avg runs comparison
print(Warner == virat) # age comparison
```

