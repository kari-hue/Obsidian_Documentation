
<%* 
tR += "---" + "\n" 
const project = await tp.system.prompt("Please enter the project name")
const name = await tp.system.prompt("Please enter the task name")
let date = tp.date.now("DD.MM.YYYY") 
tR += "Date: " + date + "\n"
tR += "Project: " + [[project]] + "\n"
let title = "EDA -" +name 
tR += "Title: " + title + "\n"
await tp.file.rename(title)
tR += "---" 
%>


Template: [[Template - EDA]]
Project: [[Customer Segmentation- Project Overview]]
Works with : [[EDA]]

### Task


### Code snippets

### Result

### Inference

### Task List 









