# sqlalchemy
from sqlalchemy.orm import declarative_base
from sqlalchemy import Column, String, DateTime, Integer, create_engine
from datetime import datetime
import os

BASE_DIR = os.path.dirname(os.path.realpath(__file__))

connection_string = "mySQL:///" + os.path.join(BASE_DIR, 'site.db')

Base = declarative_base()

engine = create_engine(connection_string, echo = True)

'''
class Employee
    id int
    Name str
    Department str
    BasicSalary int
    DA int
    HRA int
'''

class Employee(Base):
    __tablename__='Employees'
    id = Column(Integer(), primary_key = True)
    Name = Column(String(20), nullable = False) #unique = False
    Department = Column(String(20), nullable = False)
    BasicSalary = Column(Integer(), nullable = False)
    DA = Column(Integer(), nullable = False)
    HRA = Column(Integer(), nullable = False)

    def __repr__(self):
        return f"<Employee Name = {self.Name} Department = {self.Department}>"

newEmployee1 = Employee(id = 101, Name = 'Ramu', Department = 'Personnel', BasicSalary = 10000, DA = 1000, HRA = 2000)
newEmployee2 = Employee(id = 102, Name = 'Mikasa', Department = 'Marketing', BasicSalary = 35000, DA = 3500, HRA = 4000)
newEmployee3 = Employee(id = 103, Name = 'Ragoru', Department = 'Accounting', BasicSalary = 15000, DA = 1500, HRA = 2500)
newEmployee4 = Employee(id = 104, Name = 'Harry', Department = 'Management', BasicSalary = 75000, DA = 7500, HRA = 8500)
newEmployee5 = Employee(id = 105, Name = 'Mikasa', Department = 'Management', BasicSalary = 42500, DA = 3500, HRA = 4000)
newEmployee6 = Employee(id = 106, Name = 'Razor', Department = 'Management', BasicSalary = 30000, DA = 3500, HRA = 6000)
newEmployee7 = Employee(id = 107, Name = 'Zeal', Department = 'Personnel', BasicSalary = 25000, DA = 2500, HRA = 3500)
newEmployee8 = Employee(id = 108, Name = 'Razor', Department = 'Accounting', BasicSalary = 30000, DA = 3000, HRA = 4000)
newEmployee9 = Employee(id = 109, Name = 'Harry', Department = 'Accounting', BasicSalary = 75000, DA = 7500, HRA = 8500)
newEmployee10 = Employee(id = 110, Name = 'Mai', Department = 'Personnel', BasicSalary = 20000, DA = 2000, HRA = 3000)
newEmployee11 = Employee(id = 111, Name = 'Zeal', Department = 'Marketing', BasicSalary = 75000, DA = 7500, HRA = 8500)
newEmployee12 = Employee(id = 112, Name = 'Ragoru', Department = 'Management', BasicSalary = 35000, DA = 3500, HRA = 4500)
newEmployee13 = Employee(id = 113, Name = 'Mikasa', Department = 'Marketing', BasicSalary = 12000, DA = 1200, HRA = 2200)
newEmployee14 = Employee(id = 114, Name = 'Zeal', Department = 'Accounting', BasicSalary = 50000, DA = 15000, HRA = 10000)
newEmployee15 = Employee(id = 115, Name = 'Mai', Department = 'Marketing', BasicSalary = 30000, DA = 3000, HRA = 4000)

print(newEmployee1)
print(newEmployee2)
print(newEmployee3)
print(newEmployee4)
print(newEmployee5)
print(newEmployee6)
print(newEmployee7)
print(newEmployee8)
print(newEmployee9)
print(newEmployee10)
print(newEmployee11)
print(newEmployee12)
print(newEmployee13)
print(newEmployee14)
print(newEmployee15)
