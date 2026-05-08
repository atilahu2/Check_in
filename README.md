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
        

      
