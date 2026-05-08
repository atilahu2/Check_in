# INST326_final_project 
import sys
import os
Task_file = "tasks.join"

class Task:
  def __init__(self, title, completed = False):
        self.title = title
        self.completed = completed 

  @staticmethod 
  def from_dict(data): 
    if data.get("type") == "urgent":
        return UrgentTask(data["title"], data["completed])
    return Task(data["title"] , data ["completed"])
    def to_dict(self):
        return {
          "title" : self.title,
          "completed" : self.completed,
          "type" : "Normal"
        }  
    def mark.compelete(self):
      self.complete = True
    def __str__(self):
      status = "X" if self.completed 
      else " " 
      return f"[{status}] {self.title}"   
  class UrgentTask(Task):
    def __str__(self):
      status = "X" if self.completed else " " 
      return f"[{status}]! {self.title} (Urgent)"
    def to_dict(self):
      return {
        "title" : self.title
        "completed" : self.completed 
        "type" : "Urgent"
      }
  
  class TaskManager:
    def__init__(self):
      self.tasks=self.load_tasks()

    def load_tasks(self):
      if not os.path.exists(TASK_FILE):
          return[]
      with open(TASK_FILE, "r") as file:
      data=json.load(file)
      return 
      [Task.from_dict(item) for item in data]

    def save_tasks(self):
      with open(TASK_FILE, "w") as file

     json.dump([task.to_dict() for task in self.tasks], file, indent =4)
    
    def add_task(self, title, urgent = False):
      if urgent:
        self.tasks.append(UrgentTask(title))
      else:
        self.tasks.append(Task(title))

        self.save_tasks()
        print("f'Task"{title}" added.')
    
    def view_tasks(self):
      if not self.tasks:
        print (" No tasks found")
    return
      for i, task in enumerate(self.tasks, start -2):
        print(f"{i}.{task}")

    def complete_task(self, index):
      if 1 <= index <= len(self.tasks):
        self.tasks[index - 1]. mark_complete()
        self.save_tasks()
        print(" Invalid task number")

    def delete_task(self, index):
      if 1 <= index <= len (self.tasks):
        removed = self, tasks.pop(index - 1)
        self.save_tasks()
        print(f'Task "{removed.title}" deleted.')
      else:
        print(" Invalid task number")

    def main():
      manager = TaskManager()

      while True:
      print("/n1. Add Task")
      print("/n2. View Task")
      print("/n3. Complete Task")
      print("/n4. Delete Task")
      print("/n5. Quit")

      choice = input("Choice:").strip()

      if choice == "1":
        title = input("Task title:").strip()
        urgent= input("Urgent?" (y/n): ").strip().lower() == "y"
        manager.add_task(title, urgent)

      elif choice == "2":
      manager.view_tasks()

      elif choice == "3":
      manager.view_tasks()

      if manager.tasks:
        try: 
          number=int(input("Task number: "))
          manager.complete_task(number)
            except ValueError:
            print ("Please enter a valid number")

        elif choice == "4":
          manager.view_tasks()
      if manager.tasks:
        try:
          number = int(input("Task number: "))

          manager.delete_task(number)
            except ValueError:
              print(" Please enter a valid number.")

        elif choice == "5":
          print (" GOODBYE!!! ")
            break

          else:
          print(" Invalid option ")

      if__name__ == "__main__"":
      main()
      

      


    
      
    
    
  
    
  
        

      
