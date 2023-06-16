 File handling of JSON files in Python
[{"name": "John Doe","dob": "01/01/1990","height": "5'11","city": "New York","state": "New York"},    
 {"name": "Jane Doe", "dob": "02/01/1990","height": "5'6","city": "Los Angeles","state": "California"},    
 {"name": "Bob Smith", "dob": "03/01/1991","height": "6'0","city": "Chicago", "state": "Illinois"},    
 {"name": "Alice Johnson","dob": "04/01/1991","height": "5'5","city": "Houston","state": "Texas"},    
 {"name": "Charlie Brown","dob": "05/01/1992","height": "5'9","city": "Phoenix","state": "Arizona"}]


import json
# Employee Class
class Employee:
    def __init__(self, name, dob, height, city, state):
        self.name = name
        self.dob = dob
        self.height = height
        self.city = city
        self.state = state

    def __str__(self):
        return f"Name: {self.name}\nDOB: {self.dob}\nHeight: {self.height}\nCity: {self.city}\nState: {self.state}"

# Reading data from employee.json file and creating Employee objects
with open("employee.json", "r") as file:
    employees_data = json.load(file)

employees = []
for employee_data in employees_data:
    employee = Employee(employee_data["name"], employee_data["dob"], employee_data["height"], employee_data["city"], employee_data["state"])
    employees.append(employee)

# Printing the list of Employee objects
for employee in employees:
    print(employee)

# Writing dictionary data to states_and_capitals.json file
states_and_capitals = {
    "Andhra Pradesh": "Amaravati",
    "Arunachal Pradesh": "Itanagar",
    "Assam": "Dispur",
    "Bihar": "Patna",
    "Chhattisgarh": "Raipur",
    "Goa": "Panaji",
    "Gujarat": "Gandhinagar"
}

with open("states_and_capitals.json", "w") as file:
    json.dump(states_and_capitals, file)
