🔥 Scenario 1: Sudden High CPU Usage

Your server becomes very slow and users report lag.

👉 Questions:

Which command will you run first?
How will you identify the exact process causing the issue?
Once identified, what are your next steps?

💡 Hint: Think ps aux

---

🧠 Scenario 2: Memory Leak Suspicion

An application is running fine initially but gradually consumes all memory.

👉 Questions:

Which command helps you monitor memory usage per process?
How do you confirm it's the same process increasing over time?
What action would you take after identifying it?

---

⚠️ Scenario 3: Unknown Process Running

You notice a suspicious process running on your server.

👉 Questions:

Which command shows all processes including details?
How do you find the parent process of this suspicious process?
Why is parent–child relationship important in debugging?

💡 Hint: ps -ef

---

🖥️ Scenario 4: Wrong Server Confusion

You SSH into a machine but you're not sure if it's the correct server.

👉 Questions:

Which commands will you use to confirm the system identity?
How do you verify OS/kernel details?
Why is this step critical before making changes?

---

⏰ Scenario 5: Time Mismatch Issue

Your logs show incorrect timestamps causing confusion in debugging.

👉 Questions:

Which command helps verify system time?
What problems can incorrect time cause in production systems?
What would be your next step after identifying mismatch?

---

👥 Scenario 6: Suspicious Login Activity

A system issue occurred at midnight. You suspect unauthorized access.

👉 Questions:

Which command shows login history?
How do you identify suspicious login times?
What additional checks would you perform?

💡 Hint: last

---

🕵️ Scenario 7: Who Is Using the Server Right Now?

You want to know who is currently logged in and what they’re doing.

👉 Questions:

Which commands will you use?
What’s the difference between who and w?
When would you prefer one over the other?

---

⚡ Scenario 8: Multiple Users, High Load

Your server has multiple users logged in and system load is high.

👉 Questions:

How do you correlate users with processes?
Which command helps identify which user is consuming resources?
What would you do if one user is overloading the system?

---

🔄 Scenario 9: Process Tree Debugging

An application crashes, and you want to trace how it was started.

👉 Questions:

Which command helps visualize process hierarchy?
How do you identify parent and child processes?
Why is this useful in debugging?

---

🚑 Scenario 10: Emergency Debug in 60 Seconds

You have only 60 seconds to assess a failing server.

👉 Questions:

What is your step-by-step command sequence?
What are the top 3 things you check first?
How do you prioritize between CPU, memory, and users?

---
