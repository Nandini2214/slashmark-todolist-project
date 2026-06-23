# slashmark-todolist-project

# Simple To-Do List Application

tasks = []

while True:
    print("\n--- TO-DO LIST MENU ---")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Remove Task")
    print("4. Mark Task as Completed")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        task = input("Enter new task: ")
        tasks.append({"task": task, "done": False})
        print("Task added successfully!")

    elif choice == "2":
        if len(tasks) == 0:
            print("No tasks available.")
        else:
            print("\nYour Tasks:")
            for i, t in enumerate(tasks, start=1):
                status = "✓" if t["done"] else "✗"
                print(f"{i}. {t['task']} [{status}]")

    elif choice == "3":
        if len(tasks) == 0:
            print("No tasks to remove.")
        else:
            num = int(input("Enter task number to remove: "))
            if 1 <= num <= len(tasks):
                removed = tasks.pop(num - 1)
                print(f"Removed task: {removed['task']}")
            else:
                print("Invalid task number.")

    elif choice == "4":
        if len(tasks) == 0:
            print("No tasks available.")
        else:
            num = int(input("Enter task number to mark completed: "))
            if 1 <= num <= len(tasks):
                tasks[num - 1]["done"] = True
                print("Task marked as completed!")
            else:
                print("Invalid task number.")

    elif choice == "5":
        print("Exiting To-Do List App...")
        break

    else:
        print("Invalid choice! Please try again.")
