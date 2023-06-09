# Install
```
git clone https://github.com/KarAshutosh/simpleAccessAlerts.git
pip install -r requirements.txt
```

# Run
```
python v_1_accessMonitor.py
```

# About program
To monitor user activity and detect unauthorized access or suspicious activity on a Linux server using Python, we are using the pyinotify module to watch for changes to the system's log files, and the re module to search for patterns in the log files that indicate unauthorized or suspicious activity.

The code watches for changes to the auth.log file and the syslog file to capture user activity.

On detecting suspicious behaviour, an alert is sent via email

# FAQs 
**Why is handle_event() function not being called?**
The handle_event() function is not called explicitly in the code. Instead, it is passed as the default_proc_fun argument to the pyinotify.Notifier() function when the notifier is created. This sets up the handle_event() function to be called automatically whenever there is a file modification event on one of the watched log files. 
So even though you don't see a direct call to handle_event() in the code, it is still being executed by the notifier whenever a relevant event occurs.
