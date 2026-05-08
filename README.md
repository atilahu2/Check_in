# Check_in
import sys
import os
Task_file = "tasks.join"

class task:
  def __init__(self, title, completed = false):
      self.title = title
      self.completed = completed 
  @staticmethod 
    def from_dict(data): 
      return Task(data["title"] , data ["cxompleted"])
  def load_task ():
      if not os.path.exists(Task_file)
        return []
      with open( Task_file, "r") as file:
        data = j.son.load (file)
        return [Task.from_dict(item) for item in data]
        

      
