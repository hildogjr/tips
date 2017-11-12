# Programming

This text enroll good practices and procedures to a good programming applied to electric systems. Inspired in [Notepad++ GitHub contriguting](https://github.com/notepad-plus-plus/notepad-plus-plus/blob/master/CONTRIBUTING.md).
Written by Hildo Guillardi Júnior.
Licensed under GNU General Propose License 3.0.


## Pull Requests

Your pull requests are welcome; however, they may not be accepted for various reasons. If you want to make some GUI enhancement like renaming some graphic items or fixing typos, please create the issue instead of the pull requests. All Pull Requests, except for translations and user documentation, need to be attached to a issue on GitHub. For Pull Requests regarding enhancements and questions, the issue must first be approved by one of project's administrators before being merged into the project. An approved issue will have the label `Accepted`. For issues that have not been accepted, you may request to be assigned to that issue.

Opening a issue beforehand allows the administrators and the community to discuss bugs and enhancements before work begins, preventing wasted effort.


## Guidelines for pull requests

1. Respect coding style.
2. Make single commit per PR.
3. Make your modification compact - don't reformat source code in your request. It makes code review more difficult.
4. PR of reformatting (changing of ws/TAB, line endings or coding style) of source code won't be accepted. Use issue trackers for your request instead.

In short: The easier the code review is, the better the chance your pull request will get accepted.


## Coding style
![stay clean](https://notepad-plus-plus.org/assets/images/good-bad-practice.jpg)


### Identation

1. Identation is required in all code;

2. Use <tab> and not <space> to ident;

3. Identation have to be used when the line continues on the next;

```cpp
result = soma1 + soma2 * factor +
	soma3; // Prefer to broke in the + or -.
```

```matlab
result = soma1 + soma2 * factor + ...
	soma3; % Prefer to broke in the + or -.
```

4. Identation may be used to define blocks of code that is dealing if differents devices / tasks.

```
selectDevice1
	startCommunication
	sendCommand
	...
	finishCommunication
selectDevice2
	startCommunication
	sendCommand
	...
	finishCommunication
```


### Comments

1. ##### Use the comment to explain the function of the code not spell what the code is doing;

* ###### Good:
```
total = result1 + result2; // Aggregation of the past results of the calculation.
```

* ###### Bad:
```
total = result1 + result2; // Total is the sum of the results.
```

2. ##### Comments are like text, so follow the grammar sentence;

* Start with <space> <comment mark>
* Start writting the text as a real text: use upper letter, comma, ...
* Finish with <dot>

* ###### Good:
```cpp
callConfig; // Configuration of the system, peripheral and so.
```

* ###### Bad:
```cpp
callConfig;//configuration
```

3. ##### In C/C++ code prefer the C comment style.

* ###### Good:
```
// Two lines comment
// Use still C++ comment line style
```

* ###### Bad:
```
/*
Please don't piss me off with that
*/
```

The multiple line comment may be used to some development / result comment.


### Variables

1. ##### Use definitions dispete variables do constants. These have to be written upper case and _ separated words. To Math constants use the longer decimal notation possible even if it is not actually used this precision after compilation;

* ###### Good:
```cpp
#define M_SQTR_2 1.414213562
#define BUTTON_PRESS_TIMES 5
```

* ###### Bad:
```cpp
#define M_SQTR_2 1.41
#define BUTTON_PRESS_times 5
```

2. ##### Names of the variable and functions are lower case with a upper case letter to denote a new word faloow the [Camel Case style](https://en.wikipedia.org/wiki/Camel_case). Avoid the _ use and use understandable abbreviations to avoid long names;

* ###### Good:
```cpp
int hardwareConfig();
float evalPID(float error);
float va, vb, ic;
unsigned int errorCount = 0;
```

* ###### Bad:
```cpp
int Hardware_Configuration();
float eval_pid(float error);
unsigned int error_Count = 0;

```

3. ##### Use of _ is allowed to make clear sub type of one measure or variable;
* ###### Good:
```cpp
float va, va_pk; // First one is va in time and second in the peak value.
```

4. ##### Prefer to make explicit the type, unit (symbol between \[\], use use the name in the case of not a keyboard symbol: \[ohm\]) and use of one variable in the first use / declaration.

```matlab
va_rms = 0; % Phase A voltage RMS \[V\].
```


### Code

1. ##### Do not use Java-like braces;

* ###### Good:
```cpp
if ()
{
	// Do something
}
```

* ###### Bad:
```cpp
if () {
	// Do something
}
```

2. ##### Use tabs instead of white-spaces (we usually set our editors to 4 white-spaces for 1 tab, but the choice is up to you);


3. ##### Always leave one space before and after binary and ternary operators and to separate the sentences;

* ###### Good:
```cpp
if (a == 10 && b == 42)
```

* ###### Bad:
```cpp
if (a==10&&b==42)
```

4. ##### Only leave one space after semi-colons in "for" statements or function arguments.

* ###### Good:
```cpp
for (int i = 0; i != 10; ++i)
	call(3; i; CONSTANT);
```

* ###### Bad:
```cpp
for(int i=0;i<10;++i)
	call(3;i;CONSTANT);
```

5. <h5>Keywords are not function calls;<br>
Function names are not separated from the first parenthesis.</h5>

* ###### Good:
```cpp
foo();
myObject.foo(24);
```

* ###### Bad:
```cpp
foo ();
```

6. ##### Keywords are separated from the first parenthesis by one space;

* ###### Good:
```cpp
if (true)
while (true)
```

* ###### Bad:
```cpp
if(myCondition)
```

6. ##### Use the following indenting for "switch" statements:

```cpp
switch (test)
{
	case 1:
	{
		// Do something
		break;
	}
	default:
		// Do something else
} // No semi-colon here
```

7. ##### Avoid magic numbers, define constants and declare in the beginning of the code

* ###### Good:
```cpp
if (foo < I_CAN_PUSH_ON_THE_RED_BUTTON)
	startThermoNuclearWar();
```

* ###### Bad:
```cpp
if (foo < 5)
	startThermoNuclearWar();
```
