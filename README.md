DSP utility packages  
===
Common utilities developed by DSP inc.

* packages  
    + DSPlogging  
        A loggin decorator keeps logging functions' error messeages
	- features
	    1. Crete logger using different log file.
	    2. Identical log file shared by multiple `log` instances (in same module scope) won't create multiple file handler for multiple write.
        - usseage
            ```python
            from DSPlogging import log

            logName = logPath=os.path.basename(__file__)
            myLog = log(logPath=logName)
            myLog2 = log(logPath=logName)
	    	    
            @myLog.errlog(logName)
            def func1(x):
	        return x/0

            @myLog.errlog(logName)
            async def afunc1():
	        open('not exist', 'r')

	    # won't cause multiple handler problem
            @myLog2.errlog(logName)
            def func2(x):
	        return x/0
            ```
