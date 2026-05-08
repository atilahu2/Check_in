# INST326_final_project 
import sys
import os
Task_file = "tasks.join"

class task:
  def __init__(self, title, completed = false):
      self.title = title
      self.completed = completed 
  @staticmethod 
    def from_dict(data): 
      return Task(data["title"] , data ["completed"])
  def load_task ():
      if not os.path.exists(Task_file)
        return []
      with open( Task_file, "r") as file:
        data = j.son.load (file)
        return [Task.from_dict(item) for item in data]
    def to_dict(self):
      status = "X" if self.completed else""
      return f"[{status}]{self.title}"
  class UrgentTask(task):
    def_init_(self,title, completed = Falsw):
      super()._init_(title, completed)
    def_str_(self):
      status = "X"if self.completed 
      else 
      return f"[{status}] !! {self.title} (Urgent)"
    def to_dict(self):
      d = super().to_dict()
      d["type"] = "Urgent"
      return d
        

      
