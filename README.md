DSP utility packages  
===
Common utilities developed by DSP inc.

* packages  
    + DSPlogging  
        A loggin decorator keeps logging functions' error messeages
        - usseage
        ```python
        from DSPlogging import log

        logName = logPath=os.path.basename(__file__)
        myLog = log(logPath=logName)


        @myLog.errlog(logName)
        def func1(x):
	        return x/0

        @myLog.errlog(logName)
        async def afunc1():
	        open('not exist', 'r')
        ```
