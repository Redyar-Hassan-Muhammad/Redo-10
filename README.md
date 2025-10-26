print("=== Weekly Attendance Report ===")

students = ["Redo", "Leon", "Hano", "Lalo", "Kuki"]

attendance = [
    ["A", "A", "A", "A", "A"],
    ["A", "X", "A", "A", "X"],
    ["A", "A", "X", "A", "A"],
    ["X", "A", "A", "A", "A"],
    ["A", "A", "A", "X", "X"]
]

days = ["Mon", "Tue", "Wed", "Thu", "Fri"]

print("Days: ", end=" ")
for day in days:
    print(day, end=" ")
print()
print("-" * 50)

for i in range(len(students)):
    print(students[i] + ":", end="   ")
    
for j in range(len(attendance[i])):
        print(attendance[i][j], end=" ")
    
days_attended = 0
for mark in attendance[i]:
    if mark == "A":
            days_attended = days_attended + 1
    
percentage = (days_attended * 100) / 5
print("| " + str(days_attended) + "/5 days (" + str(percentage) + "%)")

print("\n=== Perfect Attendance ===")
for i in range(len(students)):
    days_attended = 0
    for mark in attendance[i]:
        if mark == "A":
            days_attended = days_attended + 1
    
if days_attended == 5:
print("  " + students[i] + ": Perfect attendance!")

print("\n=== Attendance Issues ===")
for i in range(len(students)):
    absent_days = []
    
for j in range(len(attendance[i])):
if attendance[i][j] == "X":
absent_days.append(days[j])
    
if len(absent_days) > 0:
print(" " + students[i] + ": Absent on ", end="")
    for k in range(len(absent_days)):
            print(absent_days[k], end="")
            if k < len(absent_days) - 1:
print(", ", end="")
print()

print("\n=== Class Statistics ===")
total_attended = 0
total_possible = len(students) * 5

for i in range(len(students)):
    for mark in attendance[i]:
        if mark == "A":
            total_attended = total_attended + 1

class_average = (total_attended * 100) / total_possible
print("Class Average Attendance: " + str(class_average) + "%")

print("\n=== Daily Attendance ===")
for day_index in range(len(days)):
    students_present = 0
    
for student_index in range(len(students)):
if attendance[student_index][day_index] == "A":
students_present = students_present + 1
    
    percentage = (students_present * 100) / len(students)
    print(days[day_index] + ": " + str(students_present) + "/" + str(len(students)) + " students (" + str(percentage) + "%)")
