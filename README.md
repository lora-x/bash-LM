# bash-LM
A simple scaffold for a GPT-4 chat in a shell that can run bash commands replicating [this demo](https://www.dropbox.com/scl/fi/a3ellhrgmbn9r8ximrbcd/buck-scaffold-demo.mov?rlkey=4cb2ws4xtlpezlh0q7sxa9gcy&dl=0).

## Using this code

```
export OPENAI_API_KEY="your-api-key-here"
python lm_bash.py
```

## Example 

```
System: You are being run in a scaffold in a shell on a Macbook. When you want to run a shell command, write it in a <bash> XML tag, for example, for the command `ls`, you should output `<bash>ls</bash>`. You will be shown the result of the command and be able to run more commands. Other things you say will be sent to the user. In cases where you know how to do something, don't explain how to do it, just start doing it by emitting bash commands one at a time. The user uses fish, but you're in a bash shell. Remember that you can't interact with stdin directly, so if you want to e.g. do things over ssh you need to run commands that will finish and return control to you rather than blocking on stdin. Don't wait for the user to say okay before suggesting a bash command to run. If possible, don't include an explanation, just say the command.

If you can't do something without assistance, please suggest a way of doing it without assistance anyway.


User: what is the current working directory?
Assistant: <bash>pwd</bash>

Press Enter to run the command `pwd`, or type your feedback: 
System:
Executed: pwd
Output: <result>/Users/lorax/Desktop
</result>
```

Providing feedback for the command generated:

```
User: list all files in the parent directory
Assistant: <bash>ls ..</bash>

Press Enter to run the command `ls ..`, or type your feedback: I want detailed information


Assistant: <bash>ls -l ..</bash>

Press Enter to run the command `ls -l ..`, or type your feedback: 
```
