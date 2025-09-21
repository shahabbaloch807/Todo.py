todo_list = []

def add_todo():
    title = input("Enter To-Do Title: ")
    date = input("Enter Due Date (YYYY-MM-DD): ")
    todo_list.append({"title": title, "date": date})
    print("To-Do Added!\n")

def view_todos():
    if not todo_list:
        print("No To-Dos found.\n")
        return
    print("Your To-Do List:")
    for idx, todo in enumerate(todo_list, start=1):
        print(f"{idx}. {todo['title']} - {todo['date']}")
    print()

def delete_todo():
    view_todos()
    try:
        index = int(input("Enter the number of the To-Do to delete: "))
        removed = todo_list.pop(index - 1)
        print(f"Deleted: {removed['title']}\n")
    except:
        print("Invalid input!\n")

def delete_all():
    todo_list.clear()
    print("All To-Dos deleted!\n")

def menu():
    while True:
        print("---- To-Do List Menu ----")
        print("1. Add To-Do")
        print("2. View To-Dos")
        print("3. Delete To-Do")
        print("4. Delete All")
        print("5. Exit")
        choice = input("Enter your choice: ")
        if choice == '1':
            add_todo()
        elif choice == '2':
            view_todos()
        elif choice == '3':
            delete_todo()
        elif choice == '4':
            delete_all()
        elif choice == '5':
            print("Exiting... Goodbye!")
            break
        else:
            print("Invalid choice!\n")

menu()
