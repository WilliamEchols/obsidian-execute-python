
# Python Code Executor for Obsidian
## obsidian-execute-python

A lightweight plugin for the execution of Python code snippets embedded in [Obsidian](https://obsidian.md/) notes with runtime inputs. More detailed examples are provided at the end.

## Features

- **Run Python Code Blocks**: Simply write your Python code in a markdown code block, and click the 'Start' button that appears in the preview mode. The code block will be executed and the output will be displayed in the same block.
- **Live Python Console**: Each Python code block functions as a live Python console. You can enter inputs in the input box and submit them by pressing the 'Submit Input' button or the Enter key. The input will be passed to the Python code and the result will be displayed. This process occurs during code execution, allowing conditional or loop inputs.
- **Control over Displayed Elements**: You can choose to hide the code snippets, the input box, and the exit code message.
- **Support for Different Python Versions**: You can specify the name of your Python executable (such as 'python' or 'python3') in the settings.

## How to Use

1. Install obsidian-execute-python from the Obsidian community plugins page.
2. Enable the plugin in the Obsidian settings.
3. Open or create a note and write a Python code block. A Python code block is any text enclosed in a pair of three back-ticks with the word 'python' after the first set, like this:
    
\```python
print("Hello, World!")
\```
    
4. Click 'Start' to run the Python code in the associated code block.
5. The output of your code will be displayed in the same block. If your code requires an input, enter it in the input box when prompted and press 'Submit Input' or the Enter key.
6. Code snippets can be rerun by pressing the 'Start' button again. To clear the output and the input field, click the 'Reset' button.
7. To modify the settings of the plugin, navigate to the settings tab of the plugin in Obsidian settings. The settings options are below.

## Settings

You can modify the following settings in the Obsidian settings tab:

- **Python Executable Name**: Specify the name of your Python executable. This is usually 'python' or 'python3'.
- **Show Python Code in Preview**: Toggle whether to show or hide Python code in the markdown preview.
- **Show Python Exit Code**: Toggle whether to display the exit code message after running Python code.
- **Show Input Box**: This can be set on a per-block basis using a "#noinput" comment anywhere in the code block.

## Note

- **Be careful of arbitrary code execution and do not execute any code you are not familiar with**
- The plugin creates a new Python process for each code block. Be careful with long-running or resource-intensive code as it could affect Obsidian's performance.
- Make sure the Python executable is in your system's PATH. The plugin uses the name of the Python executable specified in the settings to find and run Python.
- The '#noinput' directive can be included in your Python code block to hide the input box and the 'Submit Input' button for that specific code block. The '#noinput' directive will not be displayed in the markdown preview. For example:
    
\```python
#noinput
x = 1
print(x+1)
\```

## More Examples

### Printing Example w/ \#noinput

\```python
#noinput
print("Hello, World!")
print("Line 2")
\```

------------

### Basic Variables

\```python
#noinput
x = 2
print(x + 1)
print(x)
\```

------------

## Multiple Inputs w/ updates in-between

\```python
name = input("name: ")
print("\nentered name")
color = input("color: ")
print(f"\n{name} likes the color {color}")
\```

------------

## Loop with Input

\```python
num_over_10 = 0
while (num_over_10 <= 10):
	num_over_10 = int(input("enter num: \n"))
print(f"{num_over_10} > 10")
\```

------------

## Variables are block dependent (this will cause an error)

\```python
#noinput
print(x)
\```
